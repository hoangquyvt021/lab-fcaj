---
title : "Create Route 53 Inbound Endpoints"
date : 2024-01-24T00:00:00+07:00
weight : 3
chapter : false
pre : " <b> 5.3 </b> "
---

### Create Route 53 Inbound Endpoints

To allow your on-premise **DNS** system to query **Route 53 Resolver** for any **DNS** zones (*e.g., Private Zones*) hosted on Route 53, you need to create a Route 53 Inbound Endpoint. Inbound Endpoint is a bridge for other services to query Route 53 for domain name resolution. When you create an Inbound Endpoint, AWS will create an elastic network interface (ENI) in each availability zone (AZ) you specify to receive incoming **DNS** queries.

![Route 53 Inbound Endpoints](/images/2-Pre/0007.png?featherlight=true&width=45pc)

1. Access Route 53 console through the search box and search for Route 53.
   - Expand the left sidebar, select **Inbound endpoints** and select **Create inbound endpoint**.

![Route 53 Inbound Endpoints](/images/5.3-CreateIE/1.png?featherlight=false&width=90pc)

2. On the Create inbound endpoint page, enter the following information:
   - In **Endpoint name**: `R53-InboundEndpoint`
   - **VPC in the Region**: HybridDNS-VPCStack-. (This is the VPC created by CloudFormation in the previous section)
   - **Security group for this endpoint**: d-###….#_controllers. (This is the security group that CloudFormation created to protect connections to AWS Managed Microsoft Active Directory)

![Route 53 Inbound Endpoints](/images/5.3-CreateIE/2.png?width=90pc)
- In **Endpoint Type**, select: **IPv4**

- In **Protocols for this endpoint**, select: **Do53**


![Route 53 Inbound Endpoints](/images/5.3-CreateIE/3.png?width=90pc)
3. Configure **IP Addresses**

- In **IP address #1:**
  - In **Availability Zone**, select "**ap-southeast-1a**"
  - In **Subnet**, select "**Private subnet 1A**"
  - In **IP address**, select "Use an IP address that is selected automatically"
- In **IP address #2:**
  - In **Availability Zone**, select "**ap-southeast-1c**"
  - In **Subnet**, select "**Private subnet 2A**"
  - In **IP address**, select "Use an IP address that is selected automatically"

![Route 53 Inbound Endpoints](/images/5.3-CreateIE/4.png?featherlight=false&width=90pc)


4. Select **Create inbound endpoint**

![Route 53 Inbound Endpoints](/images/5.3-CreateIE/5.png?featherlight=false&width=90pc)

5. Complete creating **Inbound Endpoint**


![Route 53 Inbound Endpoints](/images/5.3-CreateIE/6.png?featherlight=false&width=90pc)

6. When the Inbound Endpoints are created, click on the inbound endpoint to view the endpoint details. You will see the IP addresses that have been assigned to the inbound endpoints. AWS injects an elastic network interface (ENI) into your subnet and assigns this IP address to the ENI.

![Route 53 Inbound Endpoints](/images/5.3-CreateIE/7.png?featherlight=false&width=90pc)

