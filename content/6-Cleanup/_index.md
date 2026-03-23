---
title : "Clean up resources"
date : 2024-01-24T00:00:00+07:00
weight : 6
chapter : false
pre : " <b> 6. </b> "
---

###  Clean up resources

#### Remove inbound endpoint

- Access **Route 53 Management Console**
- In the left sidebar, select **Inbound endpoints**
- Check the **Inbound endpoint** related to the lab
- Select **Delete**
- Type **delete** in the empty box and press **Delete**

![Cleanup](/images/6/1.png?featherlight=false&width=90pc)
- Select **Delete**
- Type **delete** in the empty box and press **Delete**
![Cleanup](/images/6/2.png?featherlight=false&width=90pc)

#### Remove Resolver Rule

- Access **Route 53 Management Console**
- In the left sidebar, select **Rules**
- Click on the **Rule** related to the lab to view its information
- In the VPCs section, check the **VPC** connected to the Rule and select **Disassociate**
- Type **disassociate** in the empty box and select **Disassociate**

![Cleanup](/images/6/3.png?featherlight=false&width=90pc)
![Cleanup](/images/6/4.png?featherlight=false&width=90pc)
![Cleanup](/images/6/5.png?featherlight=false&width=90pc)
- Wait 1-2 minutes to disconnect from that **VPC**.
- In the **Rule** information page, select **Delete**
- Type **delete** in the empty box and press **Delete**

![Cleanup](/images/6/6.png?featherlight=false&width=90pc)
![Cleanup](/images/6/7.png?featherlight=false&width=90pc)
#### Delete Outbound Endpoint

- Access **Route 53 Management Console**
- In the left sidebar, select **Outbound Endpoints**
- Check the **Outbound Endpoint** related to the lab
- Select **Delete**
- Type **delete** in the empty box and press **Delete**
![Cleanup](/images/6/8.png?featherlight=false&width=90pc)
- Select **Delete**
- Type **delete** in the empty box and press **Delete**
![Cleanup](/images/6/9.png?featherlight=false&width=90pc)
#### Delete AWS Managed Microsoft Active Directory

- Access **Directory Service Management Console**
- In the left sidebar, select **Directories**
- Check the **Directory** related to the lab
- Select **Actions** and select **Delete directory**
- Type **confirm** in the empty box and press **Delete**
![Cleanup](/images/6/10.png?featherlight=false&width=90pc)
- Select **Actions** and select **Delete directory**
- Type **confirm** in the empty box and press **Delete**
![Cleanup](/images/6/11.png?featherlight=false&width=90pc)
![Cleanup](/images/6/12.png?featherlight=false&width=90pc)

#### Delete CloudFormation Stack - when you delete a CloudFormation Stack, all resources created by that stack are deleted.

- In this case, the **HybridDNS stack** has created two **nested stacks**, and when you delete the **HybridDNS stack**, the two **nested stacks** are also deleted.
- Access **CloudFormation Management Console**
- In the left sidebar, select **Stacks**
- Check the **HybridDNS stack** and select **Delete**
- In **Delete stack** select **Delete**
- Wait a few minutes until **CloudFormation** removes all resources
![Cleanup](/images/6/13.png?featherlight=false&width=90pc)
- Check the **HybridDNS stack** and select **Delete**
- In **Delete stack** select **Delete**
![Cleanup](/images/6/14.png?featherlight=false&width=90pc)
