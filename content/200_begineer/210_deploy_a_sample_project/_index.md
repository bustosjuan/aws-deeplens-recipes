---
title: "Deploy a sample project"
weight: 21
chapter: true
draft: false
tags:
  - deployment
  - beginner
---
# Deploy a sample project

In this tutorial you'll learn how to deploy one of many available sample projects to your AWS DeepLens. Sample projects are ready-to-go model and code that lets you see what AWS DeepLens can do in 10 mins or less.

Here are some of the many sample projects available for AWS DeepLens.

|                                                              |                                                              |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![](https://m.media-amazon.com/images/G/01/aws/devices/deeplens/object-recognition.1c6eaecfa562584e637c5eb1dd1da70b8385b32b._CB485981410_.png) | ![](https://m.media-amazon.com/images/G/01/aws/devices/deeplens/facial-recognition.0e16d0530484f0471e8e0584e771514f5962f8f1._CB485969334_.jpg) |
| **OBJECT DETECTION** Detect the locations of 20 different types of objects. | **FACE DETECTION**<br /><br />Detect the locations of faces. |
| ![](https://m.media-amazon.com/images/G/01/aws/devices/deeplens/cat-and-dog.72b9895c61eb86f065e132a41f2decc83a0e4861._CB485972126_.jpg) | ![](https://m.media-amazon.com/images/G/01/aws/devices/deeplens/activity-recognition.29e14ec911a984654bca364ee91d796335976449._CB485966362_.jpg) |
| **CAT VS DOG**<br /><br />Recognize if the image contains a cat or dog. | **ACTIVITY RECOGNITION**<br /><br />Recognize more than 30 kinds of actions such as brushing teeth, applying lipstick, and playing guitar. |

## 1. Create a new project

![sample-project-start](/images/300_deploy_a_sample_project/lab1-sample-projects-1.png)

For *Project Type* select **Use a project template**

Then choose the **Object Detection** project template. Scroll down and click **Next**.

You are able to enter a project name and description. Scroll down and click **Create**.

![sample-project-create-final](/images/300_deploy_a_sample_project/lab1-sample-projects-2.png)

## 2. Deploy to device

In this step, you will deploy the Face detection project to your AWS DeepLens device.

Select the project you just created from the list by choosing the radio button

Select Deploy to device.

![sample-project-list](/images/300_deploy_a_sample_project/lab1-sample-projects.png)

On the Target device screen, choose your device from the list, and click **Review.**

![](/images/300_deploy_a_sample_project/lab1-sample-deploy-1.png)

Then click **Deploy**

![](/images/300_deploy_a_sample_project/lab1-sample-deploy-2.png)

You should be taken to your device's page and see the banner "Deploy Successful"

![](/images/300_deploy_a_sample_project/lab1-sample-deploy-3.png)





## 4. View Video Output

See the [documentation](https://docs.aws.amazon.com/deeplens/latest/dg/deeplens-viewing-output.html) for ways you can view the project stream.