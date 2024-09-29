---
title : "Sử dụng Reachability Analyzer"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 4.4 </b> "
---

#### Sử dụng Reachability Analyzer

![Create VPC](/images/4-CreateEc2Server-update/4-Using-Reachability-Analyzer/Check-img1.png?featherlight=false&width=60pc)

1. Truy cập vào giao diện **VPC**

   - Chọn **Reachability Analyzer**
   - Chọn **Create and analyze path**

![Create VPC](/images/4-CreateEc2Server-update/4-Using-Reachability-Analyzer/Check-img2.png?featherlight=false&width=60pc)

2. Thực hiện **Path Configuration**

   - Name tag, nhập **```EC2 private with EC2 Public```**
   - Đối với **Source type**, chọn **Instance**
   - Chọn **source** là **EC2 Public**

![Create VPC](/images/4-CreateEc2Server-update/4-Using-Reachability-Analyzer/Check-img3.png?featherlight=false&width=60pc)

   - Đối với **Destination type**, chọn **Instance**
   - Đối với **Destination**, chọn **EC2 Private**

![Create VPC](/images/4-CreateEc2Server-update/4-Using-Reachability-Analyzer/Check-img4.png?featherlight=false&width=60pc)

   - Các thông số còn lại để mặc định. 
   - Chọn **Create and analyze path**

![Create VPC](/images/4-CreateEc2Server-update/4-Using-Reachability-Analyzer/Check-img5.png?featherlight=false&width=60pc)

3. Đợi 5 phút sau sẽ hiển trạng thái **Reachable**

![Create VPC](/images/4-CreateEc2Server-update/4-Using-Reachability-Analyzer/Check-img6.png?featherlight=false&width=60pc)

![Create VPC](/images/4-CreateEc2Server-update/4-Using-Reachability-Analyzer/Check-img7.png?featherlight=false&width=60pc)

4. Sau đó, xem path details.

![Create VPC](/images/4-CreateEc2Server-update/4-Using-Reachability-Analyzer/Check-img8.png?featherlight=false&width=60pc)

5. Xem reverse path details.

![Create VPC](/images/4-CreateEc2Server-update/4-Using-Reachability-Analyzer/Check-img9.png?featherlight=false&width=60pc)

