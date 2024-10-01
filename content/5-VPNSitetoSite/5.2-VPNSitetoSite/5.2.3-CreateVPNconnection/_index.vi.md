---
title : "Tạo kết nối VPN"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 5.2.3 </b> "
---

#### Tạo kết nối VPN

1. Truy cập **VPC**

   - Chọn **Site-to-Site VPN Connections**
   - Chọn **Create VPN Connection**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/3-VPN/vpn-1.png?featherlight=false&width=60pc)

2. Trong giao diện **Create VPN Connection**

   - **Name tag**, nhập **```VPN Connection```**
   - **Target Gateway Type**: Chọn **Virtual Private Gateway**
   - **Virtual Private Gateway**: Chọn **VPN Gateway**
   - **Customer Gateway**: **Existing**
   - **Customer Gateway ID**: Chọn **Customer Gateway**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/3-VPN/vpn-2.png?featherlight=false&width=60pc)

3. Tiếp tục thực hiện cấu hình

   - **Routing Options**: **Static**
   - **Static IP Prefixes**: **10.11.0.0/16**. Đây là giải địa chỉ IP ở môi trường Onpremise giả lập.
   - Các cấu hình khác giữ nguyên mặc định.

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/3-VPN/vpn-3.png?featherlight=false&width=60pc)


4. Chọn **Create VPN Connection**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/3-VPN/vpn-4.png?featherlight=false&width=60pc)

5. Đợi khoảng 5 phút sau, hoàn tất tạo **VPN Connection**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/3-VPN/vpn-5.png?featherlight=false&width=60pc)

6. Cấu hình **propagation** cho các **route table**

   - Trong giao diện **VPC**, chọn **Route Tables**
   - Chọn **Route table - Public**
   - Chọn **Route Propagation**
   - Chọn **Edit route propagation**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/3-VPN/vpn-6.png?featherlight=false&width=60pc)

7. Trong giao diện **Edit route propagation**

   - Chọn **Enable**
   - Chọn **Save**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/3-VPN/vpn-7.png?featherlight=false&width=60pc)

8. Hoàn tất và kiểm tra lại **Route Propagation** đã chuyển sang **Yes**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/3-VPN/vpn-8.png?featherlight=false&width=60pc)

9. Tương tự Route Propagation đối với Private subnet.

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/3-VPN/vpn-9.png?featherlight=false&width=60pc)

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/3-VPN/vpn-10.png?featherlight=false&width=60pc)

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/3-VPN/vpn-11.png?featherlight=false&width=60pc)
