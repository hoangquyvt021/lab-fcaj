---
title : "Tạo Route 53 Outbound Endpoint"
date : 2024-01-24T00:00:00+07:00
weight : 1
chapter : false
pre : " <b> 5.1 </b> "
---

### Tạo Route 53 Outbound Endpoint

1. Đầu tiên, chúng ta sẽ tạo một **Outbound Endpoint** trong Route 53 để cho phép **Route 53 Resolver** chuyển tiếp các truy vấn **DNS** đối với tên miền được đặt trên hệ thống ngoài của Route 53. Khi bạn tạo một Outbound Endpoint trong Route 53, AWS sẽ tự động tạo một **Elastic Network Interface** (ENI) trong mỗi **Availability Zone** (AZ) mà bạn chỉ định.

![RDGW](/images/2-Pre/0006.png?featherlight=false&width=45pc)

2. Truy cập giao diện Route 53 thông qua khung tìm kiếm và chọn mục Route 53.
- Mở rộng menu bên trái, chọn **Outbound Endpoints** và nhấn vào **Create Outbound Endpoint**.

![RDGW](/images/5.1-CreateOE/1.png?featherlight=false&width=90pc)


3. Tại trang **Create Outbound Endpoint**, điền các thông tin sau:
   - **Endpoint name**: `R53-OutboundEndpoint`
   - **VPC in the Region**: HybridDNS-VPCStack- (Đây là VPC đã được tạo bởi CloudFormation trong phần trước)
   - **Security group for this endpoint**: d-###….#_controllers (Đây là security group được tạo bởi CloudFormation để bảo vệ kết nối tới **AWS Managed Microsoft Active Directory**)
![RDGW](/images/5.1-CreateOE/2.png?featherlight=false&width=90pc)



![RDGW](/images/5.1-CreateOE/3.png?featherlight=false&width=90pc)


- Ở mục **Endpoint Type**, chọn: **IPv4**

- Ở mục **Protocols for this endpoint**, chọn: **Do53**

- Ở mục **RNI Enhanced Metrics**, chọn:**Disable**

- Ở mục **Target Name Server Metrics**, chọn:**Disable**
![RDGW](/images/5.1-CreateOE/4.png?featherlight=false&width=90pc)

4. Tiến hành cấu hình **IP addresses**

- **IP address #1:**
  - Ở mục **Availability Zone**, chọn “**ap-southeast-1a**”
  - Ở mục **Subnet**, chọn “**Private subnet 1A**”
  - Ở mục **IP address**, chọn “Use an IP address that is selected automatically”
- **IP address #2:**
  - Ở mục **Availability Zone**, chọn “**ap-southeast-1c**”
  - Ở mục **Subnet**, chọn “**Private subnet 2A**”
  - Ở mục **IP address**, chọn “Use an IP address that is selected automatically”

![RDGW](/images/5.1-CreateOE/5.png?featherlight=false&width=90pc)
![RDGW](/images/5.1-CreateOE/6.png?featherlight=false&width=90pc)

5. Cuối cùng, nhấp vào **Create Outbound Endpoint**.

![RDGW](/images/5.1-CreateOE/7.png?featherlight=false&width=90pc)

6. Sau khoảng 5 phút, **Outbound Endpoint** sẽ được cấu hình thành công trong VPC của bạn.

![RDGW](/images/5.1-CreateOE/8.png?featherlight=false&width=90pc)

![RDGW](/images/5.1-CreateOE/9.png?featherlight=false&width=90pc)
