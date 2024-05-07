# Creating a Virtual Private Cloud VPC in AWS

<p align="center">
<img src="https://github.com/Manny-D/Virtual-Private-Cloud-VPC/assets/99146530/b95ad2bf-ccb8-4822-a126-c29d9d5e55b5" />
</p>

## Description

A virtual private cloud (VPC) is a secure, isolated private cloud hosted within a public cloud. 

<br>

#### Key Features of AWS VPC:

- <b>Customization</b>: You define your virtual network environment, including selecting your own IP address ranges, creating subnets for specific purposes (like public-facing web servers or private databases), and configuring how traffic flows within your VPC.
- <b>Isolation</b>: Your VPC is logically separated from other user's VPCs, providing an extra layer of security for your resources.
- <b>Connectivity</b>: You control how your resources communicate with each other within the VPC and how they access the internet. VPC offers options like internet gateways and virtual private networks (VPNs) for secure connections.

#### Key Benefits of AWS VPC:

- <b>Enhanced Security</b>: Isolate critical resources within your VPC and control access with security groups and network access controls. This helps prevent unauthorized access to your data and applications.
- <b>Improved Manageability</b>: Simplify network management by creating subnets with specific purposes and controlling traffic flow. This makes it easier to manage complex deployments.
- <b>Flexibility</b>: Design your network environment to meet your specific needs. You can scale your VPC up or down as your requirements change.

<br>

In this project, we’ll walk through creating an AWS Account, creating a VPC and launching an Elastic Compute Cloud (EC2) instance within that VPC.

<br>

## Create an Amazon Web Services Account

If you already have an AWS Account, skip to the next part. If not, expand <b>Details</b> below to see more.
<details>
<summary>Details</summary>
 
<br>  

If you do not already have an AWS account, navigate to the following page to create one [https://aws.amazon.com/free](https://aws.amazon.com/free) and click on either Complete Signup or Create a Free Account.

![AWS Sign Up](https://github.com/Manny-D/Virtual-Private-Cloud-VPC/assets/99146530/60c3c592-9e8a-44d5-a7c8-74284d8cdc30)

When on the <b>Contact Information</b> page, select <b>Personal</b> for the Account type.
 
![Account Type](https://github.com/Manny-D/Virtual-Private-Cloud-VPC/assets/99146530/feaadbb9-de42-4ebb-b6c0-6901c0337891)

<b>Note</b>: you will be prompted to enter in credit card info. This is for identity verification and the card will only be charged if you exceed the Free Tier limits.

![CC](https://github.com/Manny-D/Virtual-Private-Cloud-VPC/assets/99146530/d31dd4ae-82db-4079-bdd0-c69649451c52)

Next you will be prompted to confirm your identity via a SMS code, then will be taken to the <b>Select a support plan</b> page, leave it at <b>Basic support - Free</b> and click <b>Complete sign up</b>.

![Free Tier](https://github.com/Manny-D/Virtual-Private-Cloud-VPC/assets/99146530/81256aff-4cfc-4697-8334-2cef1eef592c)

Sign up completed! Click on <b>Go to the AWS Management Console</b>.

![Sign up congrats](https://github.com/Manny-D/Virtual-Private-Cloud-VPC/assets/99146530/d60ae22b-4e1d-4235-9b3d-f30a36ec67aa)

Login to the AWS Management Console using the (default) <b>Root user</b> option. 

![Root user](https://github.com/Manny-D/Virtual-Private-Cloud-VPC/assets/99146530/f25d606b-96dd-42d9-85b3-a845951d3244)
</details>

<br>

##  Create a Virtual Private Cloud

From the AWS Management Console, in the search bar, type <b>vpc</b> and click on <b>VPC</b>. 

![Search VPC](https://github.com/Manny-D/Virtual-Private-Cloud-VPC/assets/99146530/6f196379-f8b0-4b52-899e-1c253dc24e15)

Click <b>Create VPC</b> to start the creation wizard.

![Create VPC](https://github.com/Manny-D/Virtual-Private-Cloud-VPC/assets/99146530/8a12a68a-b856-45b3-a639-a808c90e9a33)

On the <b>Create VPC</b> page under <b>VPC settings</b>, do the following:

![Create VPC 2a](https://github.com/Manny-D/Virtual-Private-Cloud-VPC/assets/99146530/0dfef9f1-1872-477a-a858-394d1227451e)

- <b>Resources to create</b>: (leave the default setting of <b>VPC and more</b>)
- <b>Name tag auto-generation</b>: (leave the default text, <b>project</b>)
- <b>IPv4 CIDR</b>: enter <b>10.0.0.0/24</b>
- <b>Number of Availability Zones (AZs)</b>: change to <b>1</b>
- Leave the other options at their defaults
- Scroll down and click <b>Create VPC</b>

Once successfully created, click on <b>View VPC</b> and your VPC <b>Details</b> page will load:

![Your VPCs (a)](https://github.com/Manny-D/Virtual-Private-Cloud-VPC/assets/99146530/808f3cb5-0a80-4e4e-b234-f13850d72fc9)

Now that we've successfully created a VPC, we'll now create an EC2 instance in it. 

<br>

## Create an Elastic Cloud Compute instance

In the search bar, type <b>ec2</b> and click on <b>EC2</b>.

![Search EC2](https://github.com/Manny-D/Virtual-Private-Cloud-VPC/assets/99146530/067326a9-fe4a-450b-902d-c72f1b8b6560)

From the EC2 Dashboard, click on <b>Launch instance</b>.

![Launch Instance](https://github.com/Manny-D/Virtual-Private-Cloud-VPC/assets/99146530/f1d05095-a5b4-4735-bedc-c3ae098dfed4)

### Launch an instance wizard
Under <b>Name and tags</b>, enter a <b>Name</b> something you'll remember - eg. <b>MyWebServer</b>

![Name and tags](https://github.com/Manny-D/Virtual-Private-Cloud-VPC/assets/99146530/c7b4284c-2b18-4c65-ac60-13d35b9f8c33)

Under <b>Application and OS Images (Amazon Machine Image)</b>, leave it at the default of <b>Amazon Linux 2023 AMI</b> 

![App and OS](https://github.com/Manny-D/Virtual-Private-Cloud-VPC/assets/99146530/598a3b54-4c0a-4d49-9427-ce9f65468a99)

Under <b>Instance type</b>, leave it at the default of <b>t2.micro</b>

![Instance type](https://github.com/Manny-D/Virtual-Private-Cloud-VPC/assets/99146530/c915c310-54e4-4c6f-82de-a4387f5a0073)

Under <b>Key pair (login)</b>, click on <b>Create new key pair</b> 

![Key pair](https://github.com/Manny-D/Virtual-Private-Cloud-VPC/assets/99146530/83fe3e3f-8788-4d33-a220-9c38f0752e66)

In the <b>Create key pair</b> popup, do the following: 
- <b>Name</b>: (enter in something you'll remember - eg. <b>master1</b>)
- <b>Key pair type</b>: (leave the default setting <b>(RSA)</b>)
- <b>Private key file format</b>: (leave the default setting <b>(.pem)</b>)
- Click <b>Create key pair</b>
- <b>Note</b>: the file will be automatically downloaded via the browser your using

Under <b>Network settings</b>, first click <b>Edit</b> towards the right, then: 

![NS Edit](https://github.com/Manny-D/Virtual-Private-Cloud-VPC/assets/99146530/fa55543d-9582-48b0-9883-0cd1a966a1a2)

- Under <b>VPC - required</b> click on the drop down to change the (default) one to the VPC created earlier

![NS VPC](https://github.com/Manny-D/Virtual-Private-Cloud-VPC/assets/99146530/cb70e526-a685-4d7b-8d8e-ddd0e1ff46fa)

- <b>Subnet</b>: (will auto-populate the private one created during the VPC step)
     - <b>Note</b>: a public IP will not be assigned once provisioning is completed unless <b>Auto-assign public IP</b> is set to <b>Enable</b>. For this project, we are leaving it set to <b>Disable</b>. 
- Leave the defaults for all the other settings.

![Network Settings](https://github.com/Manny-D/Virtual-Private-Cloud-VPC/assets/99146530/b93a5e50-7f76-45b6-9316-8ee6e10e1769)

Click <b>Launch instance</b> and a similar page should load. 

![View all instances](https://github.com/Manny-D/Virtual-Private-Cloud-VPC/assets/99146530/6405186e-cea1-49c3-8956-e6732a267138)

Click on <b>View all instances</b> to see a it in the EC2 instances list.

![Instances](https://github.com/Manny-D/Virtual-Private-Cloud-VPC/assets/99146530/86ea166d-2b78-4937-9332-e95fc5316b64)

Click on the <b>Instance ID</b> to see it in more detail.

![Instance Summary](https://github.com/Manny-D/Virtual-Private-Cloud-VPC/assets/99146530/ea2705c8-1c93-41db-a202-35ce5d388f2e)

<br>

## Conclusion

This project successfully established a secure foundation for deploying resources in the AWS cloud. We created a Virtual Private Cloud (VPC) with customized settings and launched an EC2 instance within it. This configuration provides isolation and enhanced security for our cloud environment, along with the flexibility to scale and manage resources effectively.
