---
title : "Tạo Security Group"
date :  "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 3.5 </b> "
---

#### Tạo Security Group

#### Tạo Security Group cho máy chủ nằm trong Public subnet

1. Trong giao diện **VPC**

   - Chọn **Security Group**
   - Chọn **Cretae security group**

![Create VPC](/images/3-Preparation-steps-update/5-Security-Group/SG-1.png?featherlight=false&width=60pc)


2. Thực hiện cấu hình **Security group**

   - **Security Group name**, nhập **```Public subnet - SG```**
   - **Description**, nhập **Allow SSH and Ping for servers in public subnet.**
   - Chọn **ASG** VPC 

![Create VPC](/images/3-Preparation-steps-update/5-Security-Group/SG-2.png?featherlight=false&width=60pc)

3. Thực hiện cấu hình **Inbound rules**

   - Trong **Inbound rules**, click **Add rule**.

   - Chọn **Type**: **SSH** và **Source**: **My IP**. **My IP** đại diện cho 1 địa chỉ public IPv4 bạn đang sử dụng(sẽ thay đổi khi bạn đổi mạng)

   - Chọn  **Add rule** để thêm 1 rule mới.

   - Chọn **Type**: **All ICMP - IPv4** và **Source**: **Anywhere**. Cho phép ping từ bất kì địa chỉ IP nào.

![Create VPC](/images/3-Preparation-steps-update/5-Security-Group/SG-3.png?featherlight=false&width=60pc)

4. Kiểm tra **Outbound rules** và chọn **Cretae security group**

![Create VPC](/images/3-Preparation-steps-update/5-Security-Group/SG-4.png?featherlight=false&width=60pc)

5. Hoàn thành tạo security group cho máy chủ nằm trong Public subnet

![Create VPC](/images/3-Preparation-steps-update/5-Security-Group/SG-5.png?featherlight=false&width=60pc)

#### Tạo Security Group cho máy chủ nằm trong Private subnet

6. Trong giao diện **VPC**

   - Chọn **Security Groups**
   - Chọn **Create security group**

![Create VPC](/images/3-Preparation-steps-update/5-Security-Group/SG-6.png?featherlight=false&width=60pc)

7. Thực hiện cấu hình **Security group**

   - Trong phần **Security group name** điền **Private subnet - SG**

   - Trong phần **Description** điền **Allow SSH and Ping for servers in private subnet.**

   - chọn **VPC**, lựa chọn **VPC** có tên **ASG**.

![Create VPC](/images/3-Preparation-steps-update/5-Security-Group/SG-7.png?featherlight=false&width=60pc)

8. Thực hiện cấu hình **Inbound rules**

   - Trong Inbound rules, chọn  Add rule.

   - Chọn **Type**: **SSH** và để nguyên **Source**: **Custom**. Chọn  vào search box và chọn **Public subnet SG**.Lựa chọn này cho phép tất cả những máy chủ được gán **Public subnet SG** được **SSH** vào các máy chủ được gán **Private subnet SG**.

![Create VPC](/images/3-Preparation-steps-update/5-Security-Group/SG-8.png?featherlight=false&width=60pc)

9. Chọn **Add rule** để thêm 1 rule mới.

   - Chọn **Type**: **All ICMP IPv4** và **Source**: **Anywhere**. Cho phép ping từ bất kì địa chỉ IP nào.

![Create VPC](/images/3-Preparation-steps-update/5-Security-Group/SG-9.png?featherlight=false&width=60pc)

10.   Chọn **Create security group**


![Create VPC](/images/3-Preparation-steps-update/5-Security-Group/SG-10.png?featherlight=false&width=60pc)

11.  Như vậy chúng ta đã tạo được **2 Security Group** cho các máy chủ nằm trong **public subnet và private subnet.**

      - Tiếp theo chúng ta sẽ tiến hành tạo 2 máy chủ EC2.

![Create VPC](/images/3-Preparation-steps-update/5-Security-Group/SG-11.png?featherlight=false&width=60pc)
