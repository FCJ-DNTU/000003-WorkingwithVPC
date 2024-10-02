---
title : "Tạo Transit Gateway Attachment"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 5.3.4 </b> "
---

#### Tạo Transit Gateway Attachment

![VPN Configuration](/images/22/image.png?featherlight=false&width=90pc)

Mặc định khi tạo ra Transit gateway VPN connection ở giao diện **Transit gateway attachments** tự động tạo cho chúng ta một attachment vpn. Chúng ta tạo thêm một attachment cho VPC ASG

1. Truy cập vào **VPC**
    - Chọn **Transit Gateway Attachment**
    - Chọn **Create transit gateway attachment**

![VPN Configuration](/images/22/image%201.png?featherlight=false&width=90pc)

2. Trong giao diện **Create transit gateway attachment**
    - **Name tag**, nhập `VPC Attachment ASG VPN`
    - Transit gateway ID, chọn `Transit Gateway ASG`
    - Attachment type, chọn **`VPC`**

![VPN Configuration](/images/22/image%202.png?featherlight=false&width=90pc)

- Chọn **`Create transit gateway attachment`**

![VPN Configuration](/images/22/image%203.png?featherlight=false&width=90pc)

3. Đã tạo thành công **transit gateway attachment**

![VPN Configuration](/images/22/image%204.png?featherlight=false&width=90pc)