---
title : "Khởi tạo CloudFormation Template"
date : 2024-01-24T00:00:00+07:00
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

### Khởi tạo CloudFormation Template

Trong bước này, bạn sẽ xây dựng cơ sở hạ tầng mạng trong AWS. Trong phần này, bạn sẽ tận dụng template từ **AWS Quick Start** để xây dựng một hạ tầng mạng có tính sẵn sàng cao (HA) và bảo mật bằng **AWS CloudFormation**. Dưới đây là kiến trúc sẽ được xây dựng từ template.

![Launch CloudFormation](/images/2-Pre/0002.png?width=45pc)

#### Bước 1: Tải template từ GitHub
![Launch CloudFormation](/images/2.2-LaunchCloudFormation/1.png?width=90pc)
Trước khi tạo stack, bạn cần tải template CloudFormation từ GitHub repository:

1. Truy cập repository GitHub: `https://github.com/quywork62/000010-HybridDNS-Route53-Template.git`
2. Tải file template về máy hoặc clone repository:
   ```bash
   git clone https://github.com/quywork62/000010-HybridDNS-Route53-Template.git
   ```

#### Bước 2: Đăng nhập vào AWS Management Console

- Tìm và chọn **CloudFormation** trong AWS Management Console.

![Launch CloudFormation](/images/2.2-LaunchCloudFormation/2.png?width=90pc)

#### Bước 3: Tạo stack CloudFormation

1. Trong giao diện **CloudFormation**, chọn **Create stack**.

![Launch CloudFormation](/images/2.2-LaunchCloudFormation/3.png?width=90pc)

2. Trong giao diện **Create stack**:

   - **Prepare Template**: Template đã sẵn sàng.
   - **Template Source**: Chọn **Upload a template file**
   - Chọn **Choose file** và tải lên file template đã tải từ GitHub
   - Chọn **Next**.

![Launch CloudFormation](/images/2.2-LaunchCloudFormation/4.png?width=90pc)
![Launch CloudFormation](/images/2.2-LaunchCloudFormation/5.png?width=90pc)
 - Chọn **Next**.
 ![Launch CloudFormation](/images/2.2-LaunchCloudFormation/6.png?width=90pc)

4. Thực hiện cấu hình stack:

   - Ở **Stack name**, nhập **```HybridDNS```**.
   - Ở **Availability Zones**, chọn **ap-southeast-1a và ap-southeast-1c**.

![Launch CloudFormation](/images/2.2-LaunchCloudFormation/7.png?width=90pc)

5. Thực hiện cấu hình Network:

   - Ở **VPC CIDR, Private Subnet 1 & 2 CIDR, và Public Subnet 1 & 2 CIDR**, giữ các giá trị mặc định.
   - Ở **Allowed Remote Desktop Gateway External Access CIDR**, nhập **`0.0.0.0/0`**.

![Launch CloudFormation](/images/2.2-LaunchCloudFormation/8.png?width=70pc)

{{% notice warning %}}
Thiết lập này cho phép bất kỳ địa chỉ IP nào cũng có thể truy cập vào cổng RDP của EC2 instance sắp được tạo. Đây không phải là cấu hình an toàn và không nên được sử dụng trong môi trường production. Chúng ta sẽ điều chỉnh quyền truy cập sau khi quá trình triển khai template CloudFormation hoàn tất.
{{% /notice %}}

6. Trong bước **Amazon EC2 configuration**:

   - Trong **Key Pair Name**, chọn Key Pair đã tạo trước đó (**hybrid-DNS**).
   - Ở **Remote Desktop Gateway Instance Type**, giữ giá trị mặc định (t3.2xlarge).
   - Ở **Number of RDGW Hosts**, giữ giá trị mặc định (1).
   - Ở **Admin User Name**, giữ giá trị mặc định (StackAdmin).
   - **Admin Password**, thiết lập mật khẩu dễ nhớ cho bạn.

![Launch CloudFormation](/images/2.2-LaunchCloudFormation/9.png?width=70pc)

{{% notice tip %}}
Diagram trên hiển thị hai RDGW host (một host mỗi Availability Zone). Trong mục đích thực hành, chúng ta bắt đầu với một RDGW host để giảm thời gian khởi tạo của CloudFormation. Tuy nhiên, như trong diagram, bạn có thể thấy RDGW host được triển khai trong một Auto Scaling Group. Sau khi quá trình triển khai CloudFormation stack hoàn tất, bạn có thể thử cấu hình Auto Scaling group. Auto Scaling group là một dịch vụ quan trọng cung cấp tính sẵn sàng và mở rộng cho ứng dụng của bạn.
{{% /notice %}}

7. Ở các lựa chọn khác, giữ giá trị mặc định và chọn **Next**.

![Launch CloudFormation](/images/2.2-LaunchCloudFormation/10.png?width=91pc)

8. Giữ cấu hình mặc định.

![Launch CloudFormation](/images/2.2-LaunchCloudFormation/11.png?width=90pc)

9. Kiểm tra lại thiết lập của stack trong màn hình Review HybridDNS. Chọn vào hai ô checkbox và chọn **Next**.

![Launch CloudFormation](/images/2.2-LaunchCloudFormation/12.png?width=90pc)

10. Xem lại và tạo Stack

Ở bước này, bạn sẽ kiểm tra lại toàn bộ cấu hình của CloudFormation stack trước khi tạo.
![Launch CloudFormation](/images/2.2-LaunchCloudFormation/13.png?width=90pc)
- Sau khi đã kiểm tra toàn bộ thông tin:
- Nhấn **Submit** để bắt đầu tạo stack.
![Launch CloudFormation](/images/2.2-LaunchCloudFormation/14.png?width=90pc)


11. Template mất khoảng 15 phút để hoàn thành. Trong thời gian này, chúng ta sẽ xem xét những thành phần mà template CloudFormation sẽ tạo. Sau khi quá trình khởi tạo stack hoàn tất, trạng thái của stack sẽ chuyển thành **CREATE_COMPLETE**.
![Launch CloudFormation](/images/2.2-LaunchCloudFormation/15.png?width=91pc)
![Launch CloudFormation](/images/2.2-LaunchCloudFormation/16.png?width=91pc)



