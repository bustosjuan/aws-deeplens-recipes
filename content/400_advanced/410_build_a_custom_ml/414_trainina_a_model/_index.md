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

If you’re new to Jupyter notebooks, you will notice that it contains mixture of text and code cells. To run a piece of code, select the cell and then press shift + enter. While the cell is running an *asterisk* will appear next to the cell. Once complete, an output number and new output cell will appear below the original cell.


