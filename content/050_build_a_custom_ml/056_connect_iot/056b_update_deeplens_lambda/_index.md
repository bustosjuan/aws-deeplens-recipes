---
title: "Update DeepLens Lambda Function"
date: 2020-03-03T10:15:55-07:00
draft: false
weight: 56
---
## Step 2: Update DeepLens Lamda Function

We need to update the Lambda function in the Trash Classification project so that a message is sent to a new MQTT topic so the Raspberry Pi.  

1.	Navigate to AWS Lambda Functions and Select the deeplens_trash_classification function.

2.	Update the BOLDED lines in the Lambda Function to look like the code below.

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


3.	Choose Save

4.	Choose Actions and Select Publish new version

5.	Choose Publish

6.	In the AWS DeepLens Projects, Choose the Trash-Classification project

7.	Choose Edit

8.	Expand the Function section of Project content.
Select the Version pulldown and choose the latest version of the Lambda Function
Choose Save

9.	Select the Trash-Classification Project and choose Deploy to device
Choose the Target device to deploy the updated Project, Choose Review
Choose Deploy

*** Wait for the Project to finish updating the DeepLens before continuing ***


