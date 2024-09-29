---
title : "Tạo NAT Gateway"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 4.3 </b> "
---

#### Tạo NAT Gateway

#### Tạo một địa chỉ Elastic IP

1. Truy cập **EC2**

   - Chọn **Elastic IPs**
   - Chọn **Allocate Elastic IP address**


![Create VPC](/images/4-CreateEc2Server-update/3-Create-NAT-Gateway/Nat-img1.png?featherlight=false&width=60pc)


2. Trong giao diện **Allocate Elastic IP address**

   - **Public IPv4 address pool**, chọn **Amazon's pool of IPv4 addresses**
   - Chọn **Allocate**

![Create VPC](/images/4-CreateEc2Server-update/3-Create-NAT-Gateway/Nat-img2.png?featherlight=false&width=60pc)

3. Chúng ta vừa tạo thành công một địa chỉ **Public IP Address**

![Create VPC](/images/4-CreateEc2Server-update/3-Create-NAT-Gateway/Nat-img3.png?featherlight=false&width=60pc)

4. Truy cập vào **VPC**

   - Chọn **NAT Gateways**
   - **Create NAT gateway**

![Create VPC](/images/4-CreateEc2Server-update/3-Create-NAT-Gateway/Nat-img4.png?featherlight=false&width=60pc)

5. Trong giao diện **NAT gateway**

   - **Name**, nhập **```NAT gateway```**
   - **Subnet**, chọn **Public subnet 2**
   - **Connectivity type**, chọn **Public**
   - **Elastic IP allocation ID**, chọn **Elastic IP** vừa tạo.

![Create VPC](/images/4-CreateEc2Server-update/3-Create-NAT-Gateway/Nat-img5.png?featherlight=false&width=60pc)

6. Chọn **Create NAT gateway**

![Create VPC](/images/4-CreateEc2Server-update/3-Create-NAT-Gateway/Nat-img6.png?featherlight=false&width=60pc)

7. Thành công tạo **NAT gateway**


![Create VPC](/images/4-CreateEc2Server-update/3-Create-NAT-Gateway/Nat-img7.png?featherlight=false&width=60pc)


#### Tạo Route table - Private và gán vào các private subnet.

8. Trong giao diện **VPC**

   - Chọn **Route Tables**
   - Chọn **Create route table**

![Create VPC](/images/4-CreateEc2Server-update/3-Create-NAT-Gateway/Nat-img8.png?featherlight=false&width=60pc)

9. Trong giao diện **Route table**

   - **Name**, nhập **```Route table - Private```**
   - **VPC**, chọn **ASG** vpc
   - Chọn **Cretae route table**

![Create VPC](/images/4-CreateEc2Server-update/3-Create-NAT-Gateway/Nat-img9.png?featherlight=false&width=60pc)

10.   Hoàn thành tạo **Route table - Private**



![Create VPC](/images/4-CreateEc2Server-update/3-Create-NAT-Gateway/Nat-img10.png?featherlight=false&width=60pc)

11. Trong giao diện **Route table - Private**

    - Chọn **Subnet Associations**
    - Chọn **Edit subnet associations**

![Create VPC](/images/4-CreateEc2Server-update/3-Create-NAT-Gateway/Nat-img11.png?featherlight=false&width=60pc)

12. Trong giao diện **Edit subnet associations**

     - Chọn 2 private subnet
     - Chọn **Save associations**

![Create VPC](/images/4-CreateEc2Server-update/3-Create-NAT-Gateway/Nat-img12.png?featherlight=false&width=60pc)

13. Trong giao diện **Route table - Private**


     - Chọn **Routes**
     - Chọn **Edit routes**

![Create VPC](/images/4-CreateEc2Server-update/3-Create-NAT-Gateway/Nat-img13.png?featherlight=false&width=60pc)

14. Trong giao diện **Edit routes**


     - Chọn **Add route**
     - Chọn **Destination**: **0.0.0.0/0**
     - **Target**: **NAT Gateway**
     - Chọn **Save changes**

![Create VPC](/images/4-CreateEc2Server-update/3-Create-NAT-Gateway/Nat-img14.png?featherlight=false&width=60pc)

15.  Kiểm tra lại **Routes**

![Create VPC](/images/4-CreateEc2Server-update/3-Create-NAT-Gateway/Nat-img15.png?featherlight=false&width=60pc)

16. Kiểm tra ping amazon.com thành công từ EC2 Private.

```
ping amazon.com -c5
```

![Create VPC](/images/4-CreateEc2Server-update/3-Create-NAT-Gateway/Nat-img16.png?featherlight=false&width=60pc)
