---
title: "Train a model with Amazon SageMaker"
date: 2020-03-03T10:15:55-07:00
draft: false
weight: 414
tags:
  - advanced
---
### Prerequisites:
* Amazon S3 bucket starting with “deeplens-“
* For this section, please download the [custom-trash-detector.ipynb]() file.
* To create a custom image classification model, we need to use a graphics processing unit (GPU) enabled training job instance. GPUs are excellent at parallelizing the computations required to train a neural network for this project. In order to access a GPU-enabled training job instance, you must submit a request for a service limit increase to the [AWS Support Center](https://console.aws.amazon.com/support/home?#/case/create). You can follow the instructions [here]() to increase your limit. For this recipe we will use a single *ml.p2.xlarge* instance. 

We will be using Jupyter notebooks hosted by Amazon SageMaker as our development environment to train our models. The Jupyter Notebook is an open-source web application that allows you to create and share documents that contain live code, equations, visualizations and narrative text.

Follow steps [here](https://docs.aws.amazon.com/sagemaker/latest/dg/gs-setup-working-env.html) to launch your own Amazon Sagemaker notebook instance. Make sure:

1. Use a *t2.medium* instance type, which is included in the [Sagemaker free tier](https://aws.amazon.com/sagemaker/pricing/).
2. When creating a role, make sure to reference the S3 Bucket used by the project and that the bucket has the prefix **deeplens-**.

Your notebook instance will take a minute to be configured. Once you see the status change to **InService** on the **Notebook instances** page, choose **Open Jupyter** to launch your newly created Jupyter notebook instance.

Now upload the [custom-trash-detector.ipynb]() file you downloaded earlier.

![](/images/400_advanced/410_build_a_custom_ml/414_training_a_model/notebookupload.jpg)
Once the notebook has uploaded, click on its name to open it and follow it through to the end.

# Build a custom model with Amazon SageMaker

In this tutorial, you'll learn how to build a custom deep learning image classification model with Amazon Sagemaker.

## 1. Create the notebook instance

The main interface for Amazon Sagemaker work is through Jupyter notebooks. Jupyter is an interactive Python environment designed for rapid iteration. Amazon Sagemaker makes deploying and managing Jupyter notebooks easy.

From your Amazon Sagemaker console, select **Notebook instances** then **Create notebook instance**.

Enter a name for your notebook instance, leave everything else the default except for the volume size. Enter volume size of *50 GB* or more because we'll first download the data to our notebook instance before uploading the data to Amazon S3.

![lab4-sagemaker-create-notebook-1](/images/400_train_a_custom_model/lab4-sagemaker-create-notebook-1.png)

![lab4-sagemaker-create-notebook-2](/images/400_train_a_custom_model/lab4-sagemaker-create-notebook-2.png)



If you use Amazon SageMaker for the first time, please create an IAM role by choosing "Create a new role" from the selection list.

![l400-lab0-4](/images/400_train_a_custom_model/lab4-sagemaker-create-notebook-6.png)

On the pop-up menu, select **Any S3 bucket** to allow the notebook instance to any S3 buckets in your account. Then, click on "Create role" button on the bottom.

![l400-lab0-4](/images/400_train_a_custom_model/lab4-sagemaker-create-notebook-5.png)

Under the **Git repositories** section, choose **Clone a public Git repo** and enter the following for the repo URL:

https://github.com/aws-samples/aws-deeplens-reinvent-2019-workshops

![lab4-sagemaker-create-notebook-4](/images/400_train_a_custom_model/lab4-sagemaker-create-notebook-4.png)



## 2. Open the Jupyter notebook

Click on **Open Jupyter**.

![lab4-sagemaker-create-notebook-3](/images/400_train_a_custom_model/lab4-sagemaker-create-notebook-3.png)



You should see the page below

![lab4-sagemaker-notebook-1](/images/400_train_a_custom_model/lab4-sagemaker-notebook-1.png)



## 3. Run training notebook

Navigate to the [Lab2 notebook](src/Image-classification-bear.ipynb) (AIM229 > Lab2 > src > Image-classification-bear.ipynb)

The only part of the code that you should modify is the bucket name. Change it to an Amazon S3 bucket that you've created with that starts with "deeplens" in its name.

![lab4-sagemaker-notebook-5](/images/400_train_a_custom_model/lab4-sagemaker-notebook-5.png)

**Note**: Your AWS account might not have the Sagemaker limits available to kick off the training job on `ml.p2.xlarge` or `ml.p3.2xlarge` instances. If this is the case, you can use `ml.m4.xlarge` but know it will take a long time without a GPU instance. If you encounter this limitation, change the code below:

```python
s3_output_location = 's3://{}/{}/output'.format(bucket, prefix)
ic = sagemaker.estimator.Estimator(training_image,
                                         role,
                                         train_instance_count=1,
                                         train_instance_type='ml.p2.xlarge',
                                         train_volume_size = 50,
                                         train_max_run = 360000,
                                         input_mode= 'File',
                                         output_path=s3_output_location,
                                         sagemaker_session=sess)
```



From `ml.p2.xlarge` to ``ml.m4.xlarge`. We'll provide a pretrained model for you to deploy for the follow up labs.

Click on the **Run** button in the top toolbar to execute the code/text in that section. Continue clicking the run button for subsequent cells until you get to the bottom of the notebook. Alternatively, you can also use the keyboard shortcuts **Shift + Enter**.

As each section runs, it will spit out log output of what it's doing. Sometimes you'll see a **[ * ]** on the left hand side. This means that the code is still running. Once the code is done running, you'll see a number. This number represents the order in which the code was executed.

Run the notebook example through the end.
If you’re new to Jupyter notebooks, you will notice that it contains mixture of text and code cells. To run a piece of code, select the cell and then press shift + enter. While the cell is running an *asterisk* will appear next to the cell. Once complete, an output number and new output cell will appear below the original cell.


