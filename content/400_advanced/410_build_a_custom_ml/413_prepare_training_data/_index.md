---
title: "Prepare training data"
date: 2020-03-03T10:15:55-07:00
draft: false
weight: 413
tags:
  - advanced
---
{{< figure src="/images/400_advanced/410_build_a_custom_ml/412_collect_training_data/datasetexample.jpg" title="A sample image, can you guess which category this would fall into? (hint: it’s not recycling)" >}}

A good practice for collecting images is to take pictures at different possible angles and lighting conditions to make the model more robust.

Once we have the images for each type of trash, we separate the images of different types of trash into their own folders.

``` 
|-images

        |-Compost 

        |-Landfill

        |-Recycle
```

Once we have the images we want to train our ML model on, we will upload it into Amazon S3.  First, create a [S3 bucket using the AWS Console](https://docs.aws.amazon.com/AmazonS3/latest/gsg/CreatingABucket.html). For AWS DeepLens projects the Amazon S3 bucket names must start with the prefix “**deeplens-**”.

To save you some time, we put together a dataset of images already labeled under the categories Recycling, Landfill and Compost. We will load these images in the next section.

