---
title: "Add Subscriptions to Greengrass"
date: 2020-03-03T10:15:55-07:00
draft: false
weight: 60
---
### Step 4 

In this step, you enable the DeepLens to send MQTT messages to the RaspberryPi_SenseHAT device.

**1. On the group configuration page, choose Subscriptions, and then choose Add Subscription.**

![](/images/400_advanced/410_build_a_custom_ml/416_connect_iot/416d_add_gg_subscriptions/416d_step1_choose_subscription.png)

**2. Configure the subscription:**
    * Under Select a source, choose Lambdas, and then choose deeplens_trash_classification.
    * Under Select a target, choose Devices, and then choose RaspberryPi_SenseHAT.
    * Choose Next.

![](/images/400_advanced/410_build_a_custom_ml/416_connect_iot/416d_add_gg_subscriptions/416d_step2_add_subscription.png)


**3.	Under Topic filter, enter ***deeplens/trash/infer***, and then choose Next.**

![](/images/400_advanced/410_build_a_custom_ml/416_connect_iot/416d_add_gg_subscriptions/416d_step3_add_subscription_topic.png)

**4.	Choose Finish, then verify Subscriptions**

![](/images/400_advanced/410_build_a_custom_ml/416_connect_iot/416d_add_gg_subscriptions/416d_step4_add_subscription_finish.png)

![](/images/400_advanced/410_build_a_custom_ml/416_connect_iot/416d_add_gg_subscriptions/416d_step4b_add_subscription_verify.png)


**5.	Choose Actions and then Choose Deploy**

![](/images/400_advanced/410_build_a_custom_ml/416_connect_iot/416d_add_gg_subscriptions/416d_step5_add_subscription_deploy.png)

**Deployment in Progress**
![](/images/400_advanced/410_build_a_custom_ml/416_connect_iot/416d_add_gg_subscriptions/416d_step5_add_subscription_deploy_progress.png)


**Deployment Successful**
![](/images/400_advanced/410_build_a_custom_ml/416_connect_iot/416d_add_gg_subscriptions/416d_step5_add_subscription_sucess.png)



**This will update the AWS DeepLens Greengrass Core configuration to send the MQTT topic to the RaspberryPi_SenseHAT device that was added.**
