---
title: "Giving students access to AWS accounts"
chapter: true
weight: 122
tags:
  - "getting started"
---

## Giving students access

#### Creating IAM users for your students

AWS Identity and Access Management (IAM) enables you to manage access to AWS services and resources securely. Using IAM, you can create and manage AWS users and groups, and use permissions to allow and deny their access to AWS resources. IAM is a feature of your AWS account offered at no additional charge. You will be charged only for use of other AWS services by your users.

To give each student access to an AWS account where they can experiment with AWS DeepLens, we will create an IAM user account for each student.

TODO: Cloud formation template here ?

Follow [how to create an IAM user guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_create.html#id_users_create_console) from the IAM documentation. Use the following guidelines when creating your IAM user:

On step 4: Select **AWS Management Console access**.

On step 6: **Permissions**

TODO: Show the least priviledge permissions for each student.

* AWS Lambda
* Amazon S3
* Fe

#### Register AWS DeepLens devices for your students



