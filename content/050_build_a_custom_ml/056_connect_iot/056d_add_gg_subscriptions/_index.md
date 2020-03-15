---
title: "Add Subscriptions to Greengrass"
date: 2020-03-03T10:15:55-07:00
draft: false
weight: 60
---
### Step 4 

In this step, you enable the DeepLens to send MQTT messages to the RaspberryPi_SenseHAT device.

1.	On the group configuration page, choose Subscriptions, and then choose Add Subscription.
2.	Configure the subscription.
•	Under Select a source, choose Lambdas, and then choose deeplens_trash_classification.
•	Under Select a target, choose Devices, and then choose RaspberryPi_SenseHAT.
•	Choose Next.

 


3.	Under Topic filter, enter deeplens/trash/infer, and then choose Next.


 

4.	Choose Finish, then verify Subscriptions



5.	Choose Actions and then Choose Deploy

This will update the AWS DeepLens Greengrass Core configuration to send the MQTT topic to the RaspberryPi_SenseHAT device that was added.
