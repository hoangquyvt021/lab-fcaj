---
title : "Kết nối đến RDGW"
date : 2024-01-24T00:00:00+07:00
weight : 3
chapter : false
pre : " <b> 3. </b> "
---

### Kết nối đến RDGW

Bước tiếp theo là đăng nhập vào máy chủ **Remote Desktop Gateway (RDGW)** bằng giao thức **Remote Desktop Protocol (RDP)**. Nếu bạn đang sử dụng máy tính **Windows**, RDP đã có sẵn. Nếu bạn đang sử dụng máy Mac, bạn cần tải ứng dụng RDP tại [đây](https://docs.microsoft.com/en-us/windows-server/remote/remote-desktop-services/clients/remote-desktop-mac).

1. Đăng nhập vào **AWS Console** và truy cập **EC2 Management Console**.

   ![RDGW](/images/3-RDGW/1.png?width=90pc)

2. Trong giao diện **EC2**:

   - Trong menu bên trái, chọn **Instances**.
   - Chọn ô chọn ở máy chủ RDGW.
   - Chọn **Connect**.

   ![RDGW](/images/3-RDGW/2.png?width=90pc)

3. Trong giao diện **Connect to Instance**:

   - Chọn **RDP Client** và chọn "Tải tập tin Remote Desktop".
   - Chọn **Get Password**.

   ![RDGW](/images/3-RDGW/3.png?width=90pc)

4. Trong giao diện **Get Windows Password**:

   - Chọn **Browse** và tìm tập tin key pair bạn đã tải trước đó.
   - Chọn **Decrypt Password**.

   ![RDGW](/images/3-RDGW/4.png?width=90pc)

5. Khi mật khẩu được giải mã, sao chép và lưu lại.

   ![RDGW](/images/3-RDGW/5.png?width=90pc)

6. Mở tập tin RDP đã tải và sử dụng mật khẩu ở bước trước để đăng nhập vào máy chủ RDGW.

   - Chọn **Connect**.

   ![RDGW](/images/3-RDGW/6.png?featherlight=false&width=90pc)
   ![RDGW](/images/3-RDGW/7.png?featherlight=false&width=90pc)

7. Nhập mật khẩu và chọn **OK**.

   
   ![RDGW](/images/3-RDGW/8.png?featherlight=false&width=90pc)


8. Tiếp tục chọn **Yes**.

   ![RDGW](/images/3-RDGW/9.png?featherlight=false&width=90pc)

9. Đây là màn hình kết nối thành công vào máy chủ.

   ![RDGW](/images/3-RDGW/10.png?featherlight=false&width=90pc)




