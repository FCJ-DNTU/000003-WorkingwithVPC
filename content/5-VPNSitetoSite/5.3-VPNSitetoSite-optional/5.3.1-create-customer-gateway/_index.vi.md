---
title : "Tạo Virtual Private Gateway"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 5.3.1 </b> "
---

#### Tạo Customer Gateway

1. Truy cập vào **VPC**
    - Chọn **Customer Gateways**
    - Chọn **Create Customer Gateway**

![VPN Configuration](/images/19/image.png?featherlight=false&width=90pc)

2. Trong giao diện **Create Customer Gateway**
    - **Name tag**, nhập **`Customer Gateway`**
    - **IP address**, nhập **địa chỉ IP công cộng** của máy chủ **EC2 Customer Gateway**.
    - Chọn **Create Customer Gateway**

![VPN Configuration](/images/19/image%201.png?featherlight=false&width=90pc)

3. Đợi khoảng 5 phút sau, hoàn tất tạo **Customer Gateway**

![VPN Configuration](/images/19/image%202.png?featherlight=false&width=90pc)

{{% notice tip %}}
Lưu ý: theo như mô hình kiến trúc, Customer Gateway sẽ nằm ở VPC trên môi trường onpremise. Hiện tại chúng ta đang làm là khai báo với AWS rằng chúng ta sẽ có 1 Customer Gateway với địa chỉ IP public là địa chỉ public của EC2 instance : Customer Gateway nằm trong ASG VPN VPC
{{% /notice %}}