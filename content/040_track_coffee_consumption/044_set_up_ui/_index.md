---
title: "Set up the UI dashboard"
date: 2020-03-03T10:15:55-07:00
draft: false
weight: 44
---
## Step 4: Deploy the app to AWS Elastic Beanstalk
Now it’s time to deploy the leaderboard application using AWS Elastic Beanstalk. Elastic Beanstalk automatically orchestrates the required resources needed to deploy the web application. All you have to do is upload the code.

1. Go to the IAM console, and on the [IAM roles](https://console.aws.amazon.com/iam/home#/roles) page, attach the AmazonS3FullAccess and DynamoDBFullAccess managed policies to the aws-elasticbeanstalk-ec2-role. This allows Amazon EC2 instances provisioned by Elastic Beanstalk to access Amazon S3 and Amazon DynamoDB.

2. Go to the AWS Elastic Beanstalk console, and create a new application. Create a new web server environment. Enter a domain name, select Python as a platform, and upload a ZIP file [from GitHub](https://github.com/aws-samples/aws-deeplens-coffee-leaderboard/tree/master/app) that includes the Flask application and requirements.txt file. Wait until Elastic Beanstalk provisions your environment.

![](/images/040_track_coffee_consumption/044_set_up_ui/coffee-counter-10.gif)

The URL of your application should be visible on the top of your screen. Click the URL to view your coffee leaderboard!

__Important:__ Deploying a project incurs costs for the various AWS services that are used.

## Conclusion

You are now able to track the number of coffees each individual person drinks. While this project focuses on a simple coffee leaderboard, the backbone of this architecture can be used for any application.

This project showcases the power of the AWS DeepLens device in introducing developers to machine learning and IoT. Using a combination of AWS services, we were able to build this app in a short amount of time, and so can you!

### About the Authors

{{< figure src="/images/040_track_coffee_consumption/044_set_up_ui/jc-100.jpg" class="floatleft" caption="João Coelho is a Solutions Architect at Amazon Web Services in London. He helps customers leverage the AWS platform to build scalable and resilient architectures on the cloud and is especially interested in serverless technologies. Outside of work, he enjoys playing tennis and traveling." >}}

{{< figure src="/images/040_track_coffee_consumption/044_set_up_ui/lt-100.jpg" class="floatleft" caption="Laurynas Tumosa is a Technical Researcher at AWS in London. He enjoys building on the platform using AWS Machine Learning Services. He is passionate about making AI technologies accessible for everyone. Outside of work, Laurynas enjoys finding new interesting podcasts, playing guitar, and reading." >}}

{{< figure src="/images/040_track_coffee_consumption/044_set_up_ui/ld-100.jpg" class="floatleft" caption="Lalit Dayalani is a Solution Architect at Amazon Web Services based in London. He helps AWS customers to provide guidance and technical assistance helping them understand and improve the value of their solutions on AWS. In his spare time, he loves spending time with family, going on hikes and spends way too much time indulging in too much television." >}}
