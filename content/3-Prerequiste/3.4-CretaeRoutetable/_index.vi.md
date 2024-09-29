---
title : "Tạo Route Table"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 3.4 </b> "
---

#### Tạo Route Table định tuyến đi ra ngoài internet thông qua Internet Gateway.


1. Trong giao diện **VPC**

   - Chọn **Route Tables**
   - Chọn **Create route table**

![Create VPC](/images/3-Preparation-steps-update/4-Route-Table/RTB-1.png?featherlight=false&width=60pc)

2. Tiến hành cấu hình **Route table**

   - **Name**, nhập **```Route table-Public```**
   - **VPC**, chọn **ASG** VPC. VPC id sẽ được tự động điền vào.
   - Chọn **Cretae route table**

![Create VPC](/images/3-Preparation-steps-update/4-Route-Table/RTB-2.png?featherlight=false&width=60pc)

3. Hoàn thành tạo **Route table**

![Create VPC](/images/3-Preparation-steps-update/4-Route-Table/RTB-3.png?featherlight=false&width=60pc)

4. Thực hiện **Edit route**

   - Chọn **Actions**
   - Chọn **Edit routes**

![Create VPC](/images/3-Preparation-steps-update/4-Route-Table/RTB-4.png?featherlight=false&width=60pc)

5. Trong giao diện **Edit routes**

   - Chọn **Add route**
   - Điền phần **Destination CIDR** : **```0.0.0.0/0```** đại diện cho Internet.
   - Trong phần **Target**  chọn **Internet Gateway**, sau đó chọn **Internet Gateway** chúng ta đã tạo. **Internet Gateway ID** sẽ được tự động điền.
   - Chọn **Save changes**

![Create VPC](/images/3-Preparation-steps-update/4-Route-Table/RTB-5.png?featherlight=false&width=60pc)

6. Hoàn thành và kiểm tra lại **Routes**
   - Chọn **subnet associations**
   - Chọn **Edit subnet associations**

![Create VPC](/images/3-Preparation-steps-update/4-Route-Table/RTB-6.png?featherlight=false&width=60pc)

7. Trong bước **Edit subnet associations**

   - Mở rộng cột **Subnet ID** bằng cách kéo thanh ngăn sang phải.
   - Chọn đúng **2 subnet public** chúng ta đã tạo.
   - Chọn **Save associations**

![Create VPC](/images/3-Preparation-steps-update/4-Route-Table/RTB-7.png?featherlight=false&width=60pc)

8.  Hoàn thành và kiểm tra lại **Subnet associations**

![Create VPC](/images/3-Preparation-steps-update/4-Route-Table/RTB-8.png?featherlight=false&width=60pc)
