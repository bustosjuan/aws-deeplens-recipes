---
title: "Create AWS Lambda function to detect hard hats"
date: 2020-03-04T10:15:55-07:00
draft: false
weight: 32
---
### Create a cloud Lambda function

1. Go to Lambda in AWS Console at https://console.aws.amazon.com/lambda/
2. Click on Create function.
3. Under Create function, by default Author from scratch should be selected.
4. Under Author from scratch, provide the following details:

* Name: worker-safety-cloud
* Runtime: Python 3.7
* Role: Choose an existing role
* Existing role: RecognizeObjectLambdaRole
* Click Create function

1. Under Environment variables, add a variable:

* Key: iot_topic
* Value: worker-safety-demo-cloud

1. Copy the code from [cloud-lambda.py](/code/cloud-lambda.py) and paste it under the Function code for the Lambda function. 
2. Click Save.

1. Under Add triggers, select S3.
2. Under Configure triggers:

* Bucket: Select the S3 bucket you just created in earlier step.
* Event type: Leave default Object Created (All)
* Leave defaults for Prefix and Suffix and make sure Enable trigger checkbox is checked.
* Click Add.
* Click Save on the top right to save the changes to the Lambda function.

## Create an AWS DeepLens inference Lambda function

1. Go to AWS Lambda in AWS Console at https://console.aws.amazon.com/lambda/.
2. Click on Create function.
3. Under Create function, select Blueprints.
4. Under Blueprints, type greengrass and hit enter to filter blueprint templates.
5. Select greengrass-hello-world and click Configure.
6. Under Basic information, provide the following details:

* Name: name-worker-safety-deeplens (example: kashif-worker-safety-deeplens)
* Role: Choose and existing role
* Existing role: DeepLensInferenceLambdaRole
* Click Create function.

1. Copy the code from [deeplens-lambda.py](/code/deeplens-lambda.py) and paste it under the Function code for the Lambda function. 
2. Go to line 34 and modify the line below with the name of your S3 bucket created in the earlier step.

* bucket_name = "REPLACE-WITH-NAME-OF-YOUR-S3-BUCKET"

1. Click Save.
2. Click on Actions, and then "Publish new version".
3. For Version description enter: Detect a person and push frame to S3 bucket. and click Publish.
