---
title: "Update DeepLens Lambda Function"
date: 2020-03-03T10:15:55-07:00
draft: false
weight: 58
---
### Step 2 

We need to update the Lambda function in the Trash Classification project so that a message is sent to a new MQTT topic so the Raspberry Pi.  

#### 1.	Navigate to AWS Lambda Functions and Select the deeplens_trash_classification function.

![](/images/400_advanced/410_build_a_custom_ml/416_connect_iot/416b_update_deeplens_lambda/416b_step1_choose_lambda.png)


#### 2.	Update the three sections of the Lambda Function to look like the code below.

```python
# The code below will be used in a challenge lab to integrate DeepLens with a Raspberry Pi
pi_topic = 'deeplens/trash/infer'
```

```python
            # Get a frame from the video stream
            #ret, frame = awscam.getLastFrame()
 
            # The code below will be used in a challenge lab to integrate DeepLens with a Raspberry Pi
            for x in range(20):
                ret, frame = awscam.getLastFrame()
```

```python

            # The code below will be used in a challenge lab to integrate DeepLens with a Raspberry Pi
            # Send the top k results to the Raspberry Pi via MQTT
            pi_output = {}
            pi_output['object'] = output_map[top_k[0]['label']]
            client.publish(topic=pi_topic, payload=json.dumps(pi_output))
```


#### 3.	Choose Save

![](/images/400_advanced/410_build_a_custom_ml/416_connect_iot/416b_update_deeplens_lambda/416b_step3_save_updated_lambda.png)

#### 4.	Choose Actions and Select Publish new version
#### 5.	Choose Publish

![](/images/400_advanced/410_build_a_custom_ml/416_connect_iot/416b_update_deeplens_lambda/416b_step4_publish_new_version.png)


#### 6.	In the AWS DeepLens Projects, Choose the Trash-Classification project

![](/images/400_advanced/410_build_a_custom_ml/416_connect_iot/416b_update_deeplens_lambda/416b_step6_project_choose.png)

#### 7.	Choose Edit

![](/images/400_advanced/410_build_a_custom_ml/416_connect_iot/416b_update_deeplens_lambda/416b_step6_project_edit.png)

#### 8.	Expand the Function section of Project content.

![](/images/400_advanced/410_build_a_custom_ml/416_connect_iot/416b_update_deeplens_lambda/416b_step8_dl_project_expand.png)

#### 9. Select the Version pulldown and choose the latest version of the Lambda Function

![](/images/400_advanced/410_build_a_custom_ml/416_connect_iot/416b_update_deeplens_lambda/416b_step9_dl_project_version_pulldown_select.png)

![](/images/400_advanced/410_build_a_custom_ml/416_connect_iot/416b_update_deeplens_lambda/416b_step9_dl_project_version_pulldown.png)


#### 10. Choose Save
![](/images/400_advanced/410_build_a_custom_ml/416_connect_iot/416b_update_deeplens_lambda/416b_step10_dl_project_save.png)


#### 11. Select the Trash-Classification Project and choose Deploy to device
![](/images/400_advanced/410_build_a_custom_ml/416_connect_iot/416b_update_deeplens_lambda/416b_step11_dl_choose_project.png)


#### 12. Choose the Target device to deploy the updated Project, Choose Review
![](/images/400_advanced/410_build_a_custom_ml/416_connect_iot/416b_update_deeplens_lambda/416b_step12_dl_project_choose_target.png)


#### 13. Choose Deploy
![](/images/400_advanced/410_build_a_custom_ml/416_connect_iot/416b_update_deeplens_lambda/416b_step13_dl_project_choose_deploy.png)


##### *** Wait for the Project to finish updating the DeepLens before continuing ***
![](/images/400_advanced/410_build_a_custom_ml/416_connect_iot/416b_update_deeplens_lambda/416b_step14_dl_project_deployed.png)


