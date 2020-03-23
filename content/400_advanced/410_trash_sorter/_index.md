---
title: "Build a custom ML model to sort trash"
date: 2020-03-03T10:15:55-07:00
chapter: true
draft: false
weight: 410
tags:
  - advanced
---
## Deeplens Trash Classiffication Recipe

The Environmental Protection Agency estimates that 75% of waste is recyclable, yet only 34% makes it into the recycle bin. Often it can be confusing to know which bin to toss an item into—landfill, compost, or recycling.

To help you make the right choice, you can train an image classification machine learning (ML) model to distinguish between different types of trash. This post hows you how to use [AWS DeepLens](https://aws.amazon.com/deeplens/), a deep learning-enabled video camera, to predict if you can recycle or compost the item instead of throwing it into a landfill. Optionally, after AWS DeepLens makes its prediction, you can set up AWS DeepLens to send a message to a Raspberry Pi to show you which bin to throw the item in.

{{< youtube QF0QjRjBwFs >}}

![Reference Architecture](/images/400_advanced/410_build_a_custom_ml/architecturediagram.png)

#### In this recipe, we will show you how to:

1. Collect and prepare your own dataset to feed into an ML algorithm
1. Train a model with Amazon SageMaker, a fully managed service that provides the ability to build, train, and deploy machine learning (ML) models quickly
1. Run the model locally on AWS DeepLens to predict types of trash without sending any data to the cloud
1. Send messages over a local area connection to a Raspberry Pi using AWS Internet-of-Things (IoT) Greengrass

### Prerequisites

* AWS Account
* Amazon S3 bucket starting with **deeplens-**. See [how to create one](/100_getting_started/140_setup_data_storage_with_amazon_s3/).
* AWS DeepLens. [Buy one on Amazon](https://www.amazon.com/AWS-DeepLens-deep-learning-enabled-video-camera-developers/dp/B07JLSHR23).
* Raspberry Pi with [Sense HAT](https://astro-pi.org/wp-content/uploads/2018/09/T05.2_Meet-the-Sense-HAT.pdf). Get one [here](https://www.raspberrypi.org/products/sense-hat/).

