---
title : "Introduction"
date : 2024-01-24T00:00:00+07:00
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

### Overview

Most of our current customers own an on-premise **DNS** system. When you initialize resources on the AWS platform, AWS provides DNS services through **Amazon Route 53**. In this lab, we will experience building a hybrid DNS system to allow you to integrate your existing on-premise DNS system with Amazon Route 53's DNS service.

#### Route 53

**Route 53** provides several DNS capabilities such as: public DNS domain registration, ability to create private DNS zones, hybrid DNS tools and domain name resolution. With domain name resolution capability, Route 53 Resolver can perform recursive lookups against public DNS systems.

In Route 53, the Route 53 Resolver service provides three tools to enable hybrid DNS architecture between your on-premise DNS system and AWS. These three tools are:

- **Outbound Endpoints**: DNS queries from Route 53 Resolver to your on-premise DNS system will be sent from Outbound Endpoints.
- **Inbound Endpoints**: Inbound endpoints serve as targets for DNS queries from your on-premise DNS system to domain names hosted on AWS.
- **Route 53 Resolver** Rules: With Route 53 Resolver Rules, you can configure Route 53 to forward DNS queries for your specific domain names to your on-premise DNS system.

![Route 53](/images/icon.png?width=10pc)
