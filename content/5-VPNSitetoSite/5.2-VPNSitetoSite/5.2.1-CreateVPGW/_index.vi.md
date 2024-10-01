---
title : "Tạo Virtual Private Gateway"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 5.2.1 </b> "
---

#### Tạo Virtual Private Gateway

1. Truy cập vào **VPC**

   - Chọn **Virtual Private Gateway**
   - Chọn **Create Virtual Private Gateway**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/1-VPG/VPG-1.png?featherlight=false&width=60pc)

2. Trong giao diện **Create Virtual Private Gateway**

   - **Name tag**, nhập **```VPN Gateway```**
   - Chọn **Amazon default ASN**
   - Chọn **Create virtual private gateway**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/1-VPG/VPG-2.png?featherlight=false&width=60pc)

3. Chúng ta cần thực hiện **Attach to VPC**

   - Chọn **Actions**
   - Chọn **Attach to VPC**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/1-VPG/VPG-3.png?featherlight=false&width=60pc)


4. Trong giao diện **Attach to VPC**

   - Chọn **VPC ASG.**
   - Chọn **Attach to VPC**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/1-VPG/VPG-4.png?featherlight=false&width=60pc)

5. Hoàn tất và xem **State** là **Attached**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/1-VPG/VPG-5.png?featherlight=false&width=60pc)
