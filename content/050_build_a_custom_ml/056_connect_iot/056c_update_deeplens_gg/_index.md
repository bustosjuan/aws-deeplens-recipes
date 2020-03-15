---
title: "Update DeepLens Greengrass Group"
date: 2020-03-03T10:15:55-07:00
draft: false
weight: 59
---
## Step 3: Update DeepLens Greengrass Group

In this step, you add an AWS IoT devices to your existing DeepLens Greengrass group. This process includes registering the device and configuring certificates and keys to allow connectivty to AWS IoT Greengrass.
 
1.	In the AWS IoT console, choose Greengrass, and then choose Groups.

<screenshot>


2.	Choose the existing DeepLens group.

<screenshot>

3.	On the group configuration page, choose Devices, and then choose Add Device.

 <screenshot>

4.	On the Add a Device page, choose Create New Device.

 <screenshot>

5.	On the Create a Registry entry for a device page, register this device as RaspberryPi_SenseHAT, and then choose Next.

<screenshot>

6.	On the Set up security page, for 1-Click, choose Use Defaults. This option generates a device certificate with an attached AWS IoT policy and public and private key.

<screenshot>

7.	Create a folder on your computer. Download the certificate and keys for your device into the folder.

<screenshot> 

8.	Make a note of the common hash component in the file names for the RapsberryPi_SenseHAT device certificate and keys (in this example, a72ab238d3). You need it later. Choose Finish.
9.	Decompress the hash-setup.tar.gz file. For example, run the following command:

```bash
tar -xzf hash-setup.tar.gz
```

Note
On Windows, you can decompress .tar.gz files using a tool such as 7-Zip or WinZip.

10.	Review Server Authentication in the AWS IoT Developer Guide and choose the appropriate root CA certificate. We recommend that you use Amazon Trust Services (ATS) endpoints and ATS root CA certificates. Your root CA certificate type must match your endpoint. Use an ATS root CA certificate with an ATS endpoint (preferred) or a VeriSign root CA certificate with a legacy endpoint. Only some AWS Regions support legacy endpoints. For more information, see Endpoints Must Match the Certificate Type.

Save the root CA certificate as root-ca-cert.pem in the same folder as the RapsberryPi_SenseHAT device certificates and keys. All these files should be in one folder on your computer.  For ATS endpoints (preferred), download the appropriate ATS root CA certificate, such as Amazon Root CA 1.

Note
If you're using a web browser on the Mac and you see This certificate is already installed as a certificate authority, open a Terminal window and download the certificate into the folder that contains the  device certificates and keys. For example, if you're using an ATS endpoint, you can run the following command to download the Amazon Root CA 1 certificate.

```bash
cd path-to-folder-containing-device-certificates

curl -o ./root-ca-cert.pem https://www.amazontrust.com/repository/AmazonRootCA1.pem
```

Run cat root-ca-cert.pem to ensure that the file is not empty. If the file is empty, check the URL and try the curl command again.

```bash
cat root-ca-cert.pem

```