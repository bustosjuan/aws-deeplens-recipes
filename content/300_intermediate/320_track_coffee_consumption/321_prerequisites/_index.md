---
title: "Prerequisites"
date: 2020-03-03T10:15:55-07:00
draft: false
weight: 321
tags:
  - intermediate
---
## Step 1: Deploy a sample project

To deploy the project you first need to register the AWS DeepLens device, if you haven’t already. See Register Your AWS DeepLens Device for more information.

+ Go to the AWS DeepLens console and create a new project.

For the project type, make sure Use a project template is highlighted and select Face detection from the project templates.

![](/images/040_track_coffee_consumption/041_prerequisites/coffee-counter-3-2.gif)

From there you can specify the project name and add a description, leave everything else at the default, and choose __Create__.

+ After the project is created, we need to deploy it to the AWS DeepLens device. On the __Projects page__, select your project name, and then choose __Deploy to device__. On the target device page, select your registered AWS DeepLens device.

Choose __Review__.

![](/images/040_track_coffee_consumption/041_prerequisites/coffee-counter-4.gif)

After you have reviewed, finalize by choosing __Deploy__.

+ Navigate to the IAM console. Add permissions for [AmazonS3FullAccess](https://console.aws.amazon.com/iam/home?region=us-east-1#/policies/arn%3Aaws%3Aiam%3A%3Aaws%3Apolicy%2FAmazonS3FullAccess) to AWSDeepLensGreengrassGroupRole.

![](/images/040_track_coffee_consumption/041_prerequisites/coffee-counter-5.gif)

Next you need to make sure that the project was successfully deployed. Connect the AWS DeepLens device to a monitor, mouse, and keyboard. Sign in to the device using the password that you set when you registered the device.

Start your terminal and run the following command:

```bash
mplayer —demuxer lavf -lavfdopts format=mjpeg:probesize=32 /tmp/results.mjpeg
```
This command shows the project stream. You will now see each frame being run against the model as the inference Lambda function is processed.
