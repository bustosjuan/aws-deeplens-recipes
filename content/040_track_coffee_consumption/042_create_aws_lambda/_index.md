---
title: "Create AWS Lambda function to recognize faces and coffee mugs"
date: 2020-03-03T10:15:55-07:00
draft: false
weight: 42
---
After you deploy the sample project, you need to change the inference Lambda function running on the device to upload images to Amazon S3. For this use case, we also added some messages on the screen to make the process more intuitive.

1. Create an [Amazon S3](https://console.aws.amazon.com/s3/home) bucket where the images will be uploaded. Use the default settings when setting up the bucket and choose the same AWS Region as the rest of your infrastructure.

2. Go to the AWS Lambda console and open the deeplens-face-detection function. Remove the function code and replace it with the lambda_inference code [here](https://github.com/aws-samples/aws-deeplens-coffee-leaderboard/blob/master/deeplens_inference_function.py). (Replace the bucket_name variable with your bucket name.)
