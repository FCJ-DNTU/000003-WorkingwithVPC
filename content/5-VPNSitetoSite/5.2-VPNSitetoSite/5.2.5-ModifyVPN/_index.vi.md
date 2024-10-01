---
title : "Tùy chỉnh AWS VPN Tunnel"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 5.2.5 </b> "
---

#### Tùy chỉnh AWS VPN Tunnel

1. Truy cập vào giao diện **VPC**

   - Chọn **Site-to-Site VPN connections**
   - Chọn **VPN** vừa tạo.
   - Chọn **Actions**
   - Chọn **Modify VPN tunnel options**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/5-Modify/Modify-1.png?featherlight=false&width=60pc)

2. Chọn **VPN Tunnel outside IP address**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/5-Modify/Modify-2.png?featherlight=false&width=60pc)

3. Chọn **Confirm UP tunnel modification** và các thông số còn lại mặc định.

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/5-Modify/Modify-3.png?featherlight=false&width=60pc)

4. Đối với **Tunnel activity log**, chọn **Enable**

   - Chọn **Amazon CloudWatch log group** (nếu chưa có bạn có thể tạo trong CloudWatch)
   - Đối với **Output format**, chọn **text**
   - Chọn **Save changes**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/5-Modify/Modify-4.png?featherlight=false&width=60pc)

5. Truy cập vào **CloudWatch**

   - Chọn **Log groups**
   - Chọn **Log streams**
   - Chọn một stream.

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/5-Modify/Modify-5.png?featherlight=false&width=60pc)

6. Vào xem **Log events**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/5-Modify/Modify-6.png?featherlight=false&width=60pc)

7. Bạn thực hiện tương tự với tunnel còn lại.

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/5-Modify/Modify-7.png?featherlight=false&width=60pc)
![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/5-Modify/Modify-8.png?featherlight=false&width=60pc)
![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/5-Modify/Modify-9.png?featherlight=false&width=60pc)

8. Phải đảm bảo cả 2 tunnel đã **UP**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/5-Modify/Modify-10.png?featherlight=false&width=60pc)

