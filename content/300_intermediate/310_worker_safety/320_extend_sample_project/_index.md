---
title: "Deploy an object detection project"
date: 2020-03-04T10:15:55-07:00
draft: false
weight: 320
---
### 1. Deploy a sample project

Go to the AWS DeepLens console and create a new project.

For the project type, make sure Use a project template is highlighted and select **Face detection** from the project templates.

![](/images/040_track_coffee_consumption/041_prerequisites/coffee-counter-3-2.gif)

For the project name, start with "**worker-safety-**", leave everything else at the default, and choose __Create__.

After the project is created, we need to deploy it to the AWS DeepLens device. On the __Projects page__, select your project name, and then choose __Deploy to device__. On the target device page, select your registered AWS DeepLens device.

Choose __Review__.

After you have reviewed, finalize by choosing __Deploy__.

### 2. Extend the sample project

Next we'll replace the sample project Lambda function with our own to upload cropped images of the faces detected to the cloud so we can detect if the faces have hard hats on. 

#### Create an AWS DeepLens inference Lambda function

<BAD>

1. **Go to AWS Lambda in AWS Console at https://console.aws.amazon.com/lambda/.**
2. **Click on Create function.**
3. **Under Create function, select Blueprints.**
4. **Under Blueprints, type greengrass and hit enter to filter blueprint templates.**
5. **Select greengrass-hello-world and click Configure.**
6. **Under Basic information, provide the following details:**

* **Name: name-worker-safety-deeplens (example: kashif-worker-safety-deeplens)**
* **Role: Choose and existing role**
* **Existing role: DeepLensInferenceLambdaRole**
* **Click Create function.**

1. **Copy the code from [deeplens-lambda.py](/code/deeplens-lambda.py) and paste it under the Function code for the Lambda function.** 
2. **Go to line 34 and modify the line below with the name of your S3 bucket created in the earlier step.**

**`bucket_name = "REPLACE-WITH-NAME-OF-YOUR-S3-BUCKET"`**

1. **Click Save.**
2. **Click on Actions, and then "Publish new version".**
3. **For Version description enter: Detect a person and push frame to S3 bucket. and click Publish.**

### Create an AWS DeepLens project

1. Using your browser, open the AWS DeepLens console at https://console.aws.amazon.com/deeplens/.
2. Choose Projects, then choose Create new project.
3. On the Choose project type screen

* Choose Create a new blank project, and click Next.

1. On the Specify project details screen

    * Under Project information section:
        * Project name: your-user-name-worker-safety (example: kashif-worker-safety)
    * Under Project content:
        * Click on Add model, click on radio button for deeplens-object-detection and click Add model.
        * Click on Add function, click on radio button for your lambda function (example: kashif-worker-safety-deeplens) lambda function and click Add function.
* Click Create. This returns you to the Projects screen.

### Deploy the project to AWS DeepLens 

1. From the AWS DeepLens console, on the Projects screen, choose the radio button to the left of your project name, then choose Deploy to device.
2. On the Target device screen, from the list of AWS DeepLens devices, choose the radio button to the left of the device where you want to deploy this project.
3. Choose Review. This will take you to the Review and deploy screen.
    If a project is already deployed to the device, you will see a warning message "There is an existing project on this device. Do you want to replace it? If you Deploy, AWS DeepLens will remove the current project before deploying the new project." Go ahead and choose Deploy.
4. On the Review and deploy screen, review your project and click Deploy to deploy the project to your AWS DeepLens. This will take you to the device screen, which shows the progress of your project deployment. Once your deployment is successful, proceed to the next step.

