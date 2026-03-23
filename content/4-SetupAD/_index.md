---
title : "Microsoft AD Deployment"
date : 2024-01-24T00:00:00+07:00
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

### Deploy Microsoft AD

To simulate **DNS** on-premise, we will use the **AWS Directory Service** to deploy **AWS Managed Microsoft Active Directory** in two private subnets created by CloudFormation as shown below:

![RDGW](/images/2-Pre/0004.png?width=45pc)

1. Log in to **AWS Console** and access the Directory Service console through the search box and search for Directory Services.

   - Make sure you have selected the correct **Region**. Check the top left corner of the **AWS Console** and select the Region you need (Here we are selecting ap-southeast-1)

   ![RDGW](/images/4-AD/1.png?width=90pc)

2. If this is your first time accessing **Directory Services** in this region, you will be directed to the initial welcome screen. Expand the left sidebar and select **Directories**.

   - Select **Set up directory**.

   ![RDGW](/images/4-AD/2.png?featherlight=false&width=90pc)

3. Select **Directory types**, choose **AWS Managed Microsoft AD**.

   Select **Getting started with AWS Managed Microsoft AD**, choose **Create new AWS managed AD domain**.

   ![RDGW](/images/4-AD/3.png?featherlight=false&width=90pc)

4. On the **Enter Directory Information** page, enter the following information:

   - For **Edition**: select **Standard Edition**.

   - For **Directory DNS name**: `onprem.example.com` (this **DNS** name must be unique among your directories).

   - For **Directory NetBIOS name**: `onprem` (this **NetBIOS** name must be unique among your directories).

   ![RDGW](/images/4-AD/4.png?featherlight=false&width=90pc)

5. Continue configuration:

   - For **Directory Description**: `This is to simulate the on-prem AD`.

   - For **Admin Password**: Use a password you can remember. Please note the password complexity requirements stated on the screen.

   - For **Confirm password**: Enter the password again.

   - Select **Next**.

   ![RDGW](/images/4-AD/5.png?featherlight=false&width=90pc)
   ![RDGW](/images/4-AD/6.png?featherlight=false&width=90pc)

6. In **Choose VPC and subnets**, select **VPC Hybrid-DNS-VPCStack** that we created earlier and two private subnets **Private subnet 1A** and **Private subnet 2A**. Then, select **Next**.

   ![RDGW](/images/4-AD/7.png?featherlight=false&width=90pc)

7. On the **Review & create** screen, review the settings and select **Create Directory**.

   ![RDGW](/images/4-AD/8.png?featherlight=false&width=90pc)
   ![RDGW](/images/4-AD/9.png?featherlight=false&width=90pc)
   

8. The directory will take about 20 minutes to create. During this time, AWS will provision two **Windows** servers and promote them to **Active Directory** domain controllers for the AD forest you specified. This AD forest will be a new AD forest. The process will be complete when you see the status change to Active.

   ![RDGW](/images/4-AD/10.png?featherlight=false&width=90pc)
   ![RDGW](/images/4-AD/11.png?featherlight=false&width=90pc)

9. When the directory has been created, you can view details by clicking on the **Directory ID**. The two **DNS** IP addresses listed are the IP addresses of **elastic network interfaces** (ENI) that have been placed in your availability zone to communicate with **AWS Managed Microsoft AD Domain Controllers**.

   ![RDGW](/images/4-AD/12.png?featherlight=false&width=90pc)

