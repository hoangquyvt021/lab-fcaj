---
title : "Preparation "
date : 2024-01-24T00:00:00+07:00
weight : 2
chapter : false
pre : " <b> 2. </b> "
---



### Overview

The first step is to build the network infrastructure in AWS. In this section, you will leverage **AWS Quick Start** to build a highly available (HA) and secure network infrastructure. Then, you will deploy an **AWS Managed Microsoft Active Directory** using the **AWS Directory Service** to simulate your on-premise DNS system. When you complete this section, you will successfully deploy the infrastructure architecture as follows:

![Set up](/images/2-Pre/0001.png?width=60pc)

#### *AWS Quick Starts*

**AWS Quick Starts** is a library containing pre-built architecture templates by **AWS Solution Architects and Partners**. AWS Quick Starts uses **AWS CloudFormation** as a building tool to create the architectures described in its templates.

#### *AWS CloudFormation*

**AWS CloudFormation** is AWS's **Infrastructure as Code (IaC)** service that allows you to create infrastructure based on templates (written in **YAML** or JSON). **Templates** are uploaded to the CloudFormation service and automatically create the infrastructure described in the template.

#### *AWS Directory Service*

**AWS Directory Service** is a tool that allows you to deploy an **Active Directory** directly on AWS Cloud to simplify management and provide end-user access to AWS services.

