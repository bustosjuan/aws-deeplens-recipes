---
title: "Connect DeepLens with a Raspberry Pi"
date: 2020-03-03T10:15:55-07:00
draft: false
weight: 61
---
## Step 5: Configure Raspberry Pi

1.	Run the following commands to install the AWS IoT Device SDK for Python on the Raspberry Pi:

cd ~
git clone https://github.com/aws/aws-iot-device-sdk-python.git
cd aws-iot-device-sdk-python
sudo python setup.py install

2.	Create basicDiscovery.py from the code below in the folder you downloaded the IoT device certificates.

3.	Make sure that your computer and the AWS IoT Greengrass core device are connected to the internet using the same network.


4.	On the AWS IoT Greengrass core device, run the following command to find its IP address.

hostname -I

5.	On your computer, run the following command using the IP address of the core. You can use Ctrl + C to stop the ping command.

ping IP-address

Output similar to the following indicates successful communication between the computer and the AWS IoT Greengrass core device (0% packet loss):

 

6.	Determine your AWS IoT endpoint.

•	In the AWS IoT console, in the navigation pane, choose Settings.

•	Under Settings, make a note of the value of Endpoint. You use this value to replace the AWS_IOT_ENDPOINT placeholder in the commands in the following steps.


 

7.	On your computer, open a command-line (terminal or command prompt) window.  This will be used to connect to the RaspberryPi_SenseHAT device.
 
8.	Upon execution, basicDiscovery.py attempts to collect information on the location of the AWS IoT Greengrass core at its endpoints. This information is stored after the device has discovered and successfully connected to the core. This allows future messaging and operations to be executed locally (without the need for an internet connection).

Note
You can run the following command from the folder that contains the basicDiscovery.py file for detailed script usage information:

python basicDiscovery.py –help

9.	cd path-to-certs-folder

python basicDiscovery.py --endpoint AWS_IOT_ENDPOINT --rootCA root-ca-cert.pem --cert hash.cert.pem --key hash.private.key --thingName RaspberryPi_SenseHAT --topic 'deeplens/trash/infer' --mode subscribe



Congratulations! You are now ready to join the pursuit of sustainability by using the AWS DeepLens Trash Classification project to give you that extra confidence on choosing the correct bin to toss your item.

