---
title : "Create Route 53 Resolver Rules"
date : 2024-01-24T00:00:00+07:00
weight : 2
chapter : false
pre : " <b> 5.2 </b> "
---

### Create Route 53 Resolver Rules

The next step is to create **Route 53 Resolver** Rules. A Route 53 Resolver rule allows you to define two actions: Forward or System.

- With Forward, you can configure Route 53 Resolver to forward DNS queries to an external DNS resolver (e.g., your on-premise DNS server).
- With System, Route 53 will query internally to resolve domain names (Private DNS zones, VPC DNS, and Public DNS).

1. Access **Route 53 console** through the search box and search for **Route 53**.
   - In the left sidebar, select **Rules** and select **Create rule**.

![RDGW](/images/5.2-CreateRoute53rule/1.png?featherlight=false&width=90pc)

2. Enter the following information:

   - In **Name**, enter:
     - `ForwardToOnPremAD`
   
   - In **Rule type**, select:
     - **Forward**
   
   - In **Domain name**, enter:
     - `onprem.example.com.` (This is the domain name of the directory you created in the previous section)
   
   - In **VPC that use this rule**, select:
     - **HybridDNS-VPCStack**
   
   - In **Outbound Endpoint**, select:
     - **R53-OutboundEndpoint**

![RDGW](/images/5.2-CreateRoute53rule/2.png?featherlight=false&width=90pc)

3. In Target IP addresses, enter the two **AWS Managed Microsoft Active Directory** IP addresses that were recorded. Note that you need to select Add target to add the second IP address.

   - Select **Submit**

![RDGW](/images/5.2-CreateRoute53rule/3.png?featherlight=false&width=90pc)
![RDGW](/images/5.2-CreateRoute53rule/4.png?featherlight=false&width=90pc)
4. Complete creating Route 53 Resolver


![RDGW](/images/5.2-CreateRoute53rule/5.png?featherlight=false&width=90pc)
5. At this point, you have configured **Route 53 Resolver** to forward queries for onprem.example.com to another **DNS** resolver (e.g., AWS Managed Microsoft AD). The domain name, onprem.example.com, simulates a **DNS** domain hosted by your on-premise **DNS** system.

![RDGW](/images/5.2-CreateRoute53rule/6.png?featherlight=false&width=90pc)

