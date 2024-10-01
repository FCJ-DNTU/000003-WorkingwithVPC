---
title : "Tạo máy chủ EC2"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 4.1 </b> "
---

#### Tạo EC2 nằm trong Public subnet

1. Truy cập **AWS Management Console**

   - Tìm **EC2**
   - Chọn **EC2**

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img1.png?featherlight=false&width=60pc)


2. Trong giao diện **EC2**

   - Chọn **Instances**
   - Chọn **Launch instances**

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img2.png?featherlight=false&width=60pc)

3. **Name and tags** của instance, nhập **```EC2 Public```**

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img3.png?featherlight=false&width=60pc)

4. Thực hiện chọn **AMI**

   - Chọn **Quick Start**
   - Chọn **Amazon Linux 2**
   - Chọn **AMI**

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img4.png?featherlight=false&width=60pc)

5. Thực hiện chọn **Instance type** và Chọn **Create new key pair**

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img5.png?featherlight=false&width=60pc)

6. Trong giao diện **Cretae key pair**

   - **Key pair name**, nhập **```aws-keypair```** (tên tùy chọn, bạn có thể đặt bất kỳ).
   - **Key pair type**, chọn **RSA**
   - **Private key file format**, chọn **.pem**

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img6.png?featherlight=false&width=60pc)

7.  Thực hiện cấu hình **Network**

    - **VPC**, chọn **ASG**
    - **Subnet**, chọn **Public Subnet 1**
    - **Auto-assign public IP**, chọn **Enable**
    - **Firewall (Security Group)**, chọn **Select existing security group**
    - Chọn **Public subnet -SG**
    - Chọn **Launch instance**

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img7.png?featherlight=false&width=60pc)

8. Hoàn thành tạo instance

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img8.png?featherlight=false&width=60pc)

9. Đợi khoảng 5 phút **Status check** sẽ chuyển sang **2/2 checks passed**

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img9.png?featherlight=false&width=60pc)

#### Tạo EC2 nằm trong Private subnet

10. Trong giao diện **EC2**

    - Chọn **Instances**
    - Chọn **Launch instances**

11. **Name and tags**, nhập **```EC2 Private```**

     - Chọn **Quick Start**
     - Chọn **Amazon Linux 2**
     - Chọn **AMI**

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img10.png?featherlight=false&width=60pc)

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img11.png?featherlight=false&width=60pc)

12.    Thực hiện chọn **instance type**. **Key pair name**, chọn **```aws-keypair```**

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img12.png?featherlight=false&width=60pc)

13.   Thực hiện cấu hình **Network**

      - **VPC**, chọn **ASG** vpc
      - **Subnet**, chọn **Private subnet 2**
      - **Auto-assign public IP**, chọn **Disable**. Nếu không **Disable**, bạn cần kiểm tra lại phần cấu hình **tự động cấp phát public IP cho subnet.** 

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img13.png?featherlight=false&width=60pc)

14.    Hoàn thành tạo instance

         - Chọn **View all instance**

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img14.png?featherlight=false&width=60pc)

15.    Chọn **EC2 Private**

         - Chọn **Details**
         - Lưu trữ **Private IPv4 addresses**

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-15.png?featherlight=false&width=60pc)

