---
title : "Thiết lập Hybrid DNS với Route 53 Resolver"
date : 2024-01-24T00:00:00+07:00
weight : 1 
chapter : false
---

# Thiết lập Hybrid DNS với Route 53 Resolver

### Tổng quan

Đa số các khách hàng hiện nay đang sở hữu một hệ thống DNS on-premise. Khi bạn tạo các tài nguyên trên nền tảng AWS, AWS cung cấp dịch vụ DNS thông qua Amazon Route 53. Trong bài lab này, chúng ta sẽ trải nghiệm xây dựng hệ thống DNS hybrid để tích hợp hệ thống DNS on-premise hiện có với dịch vụ DNS của Amazon Route 53.

#### Route 53

**Route 53** cung cấp nhiều khả năng của DNS, bao gồm đăng ký miền DNS công cộng, tạo vùng DNS riêng, công cụ DNS hybrid và phân giải tên miền. Với tính năng phân giải tên miền, Route 53 Resolver có khả năng thực hiện tra cứu đệ quy đối với các hệ thống DNS công cộng.

Trong Route 53, dịch vụ Route 53 Resolver cung cấp ba công cụ để kích hoạt kiến trúc DNS hybrid giữa hệ thống DNS on-premise của bạn và AWS:

- **Outbound Endpoints**: Các truy vấn DNS từ Route 53 Resolver đến hệ thống DNS on-premise của bạn sẽ được gửi từ Outbound Endpoints.
- **Inbound Endpoints**: Inbound Endpoints đóng vai trò là điểm đích cho các truy vấn DNS từ hệ thống DNS on-premise của bạn đến các tên miền được lưu trữ trên AWS.
- **Route 53 Resolver Rules**: Với Route 53 Resolver Rules, bạn có thể cấu hình Route 53 để chuyển tiếp các truy vấn DNS cho các tên miền cụ thể của bạn tới hệ thống DNS on-premise.

![Route 53](/images/icon.png?featherlight=false&width=10pc)

