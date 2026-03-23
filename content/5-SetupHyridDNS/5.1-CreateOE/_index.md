---
title : "Create Route 53 Outbound Endpoint"
date : 2024-01-24T00:00:00+07:00
weight : 1
chapter : false
pre : " <b> 5.1 </b> "
---

### Create Route 53 Outbound Endpoint

1. First, we will create an **Outbound Endpoint** in Route 53 to allow **Route 53 Resolver** to forward **DNS** queries for domain names hosted on systems outside of Route 53. When you create an Outbound Endpoint in Route 53, AWS will automatically create an **Elastic Network Interface** (ENI) in each **Availability Zone** (AZ) that you specify.

![RDGW](/images/2-Pre/0006.png?featherlight=false&width=45pc)

2. Access the Route 53 interface through the search box and select Route 53.
- Expand the left menu, select **Outbound Endpoints** and click **Create Outbound Endpoint**.

![RDGW](/images/5.1-CreateOE/1.png?featherlight=false&width=90pc)


3. On the **Create Outbound Endpoint** page, enter the following information:
   - **Endpoint name**: `R53-OutboundEndpoint`
   - **VPC in the Region**: HybridDNS-VPCStack- (This is the VPC created by CloudFormation in the previous section)
   - **Security group for this endpoint**: d-###….#_controllers (This is the security group created by CloudFormation to protect connections to **AWS Managed Microsoft Active Directory**)
![RDGW](/images/5.1-CreateOE/2.png?featherlight=false&width=90pc)



![RDGW](/images/5.1-CreateOE/3.png?featherlight=false&width=90pc)


- In **Endpoint Type**, select: **IPv4**

- In **Protocols for this endpoint**, select: **Do53**

- In **RNI Enhanced Metrics**, select:**Disable**

- In **Target Name Server Metrics**, select:**Disable**
![RDGW](/images/5.1-CreateOE/4.png?featherlight=false&width=90pc)

4. Configure **IP addresses**

- **IP address #1:**
  - In **Availability Zone**, select "**ap-southeast-1a**"
  - In **Subnet**, select "**Private subnet 1A**"
  - In **IP address**, select "Use an IP address that is selected automatically"
- **IP address #2:**
  - In **Availability Zone**, select "**ap-southeast-1c**"
  - In **Subnet**, select "**Private subnet 2A**"
  - In **IP address**, select "Use an IP address that is selected automatically"

![RDGW](/images/5.1-CreateOE/5.png?featherlight=false&width=90pc)
![RDGW](/images/5.1-CreateOE/6.png?featherlight=false&width=90pc)

5. Finally, click **Create Outbound Endpoint**.

![RDGW](/images/5.1-CreateOE/7.png?featherlight=false&width=90pc)

6. After about 5 minutes, the **Outbound Endpoint** will be successfully configured in your VPC.

![RDGW](/images/5.1-CreateOE/8.png?featherlight=false&width=90pc)

![RDGW](/images/5.1-CreateOE/9.png?featherlight=false&width=90pc)

