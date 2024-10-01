---
title : "Tạo VPC cho VPN"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 5.1.1 </b> "
---

#### Tạo môi trường VPN

1. Truy cập giao diện **VPC**

   - Chọn **Yours VPC**
   - Chọn **Create VPC**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/1-VPC/VPC-1.png?featherlight=false&width=60pc)

2. Trong giao diện **Cretae VPC**

   - **Resource**, chọn **VPC only**
   - **Name**, nhập **```ASG VPN```**
   - **IPv4 CIDR block**, nhập **```10.11.0.0/16```**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/1-VPC/VPC-2.png?featherlight=false&width=60pc)

3. Chọn **Create VPC**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/1-VPC/VPC-3.png?featherlight=false&width=60pc)

4. Tạo VPC thành công

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/1-VPC/VPC-4.png?featherlight=false&width=60pc)

5. Truy cập giao diện **VPC**

   - Chọn **Subnets**
   - Chọn **Create subnet**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/1-VPC/VPC-5.png?featherlight=false&width=60pc)

6. Trong giao diện **Create subnet**

   - Chọn **ASG VPN** vpc

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/1-VPC/VPC-6.png?featherlight=false&width=60pc)


7. Trong giao diện **Subnet settings**

   - **Subnet name**, nhập **```VPN Public```**
   - Lựa chọn **Availability Zone**: **ap-southeast-1a**
   - Chọn **IPv4 CIDR block** là **10.11.1.0/24** theo kiến trúc mô tả

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/1-VPC/VPC-7.png?featherlight=false&width=60pc)

8. Tạo thành công **VPN Public**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/1-VPC/VPC-8.png?featherlight=false&width=60pc)

9. Trong giao diện **VPC**

   - Chọn **Subnets**
   - Chọn **VPN Public**
   - Chọn **Actions**
   - Chọn **Edit subnet settings**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/1-VPC/VPC-9.png?featherlight=false&width=60pc)

10. Thực hiện **Auto-assign IP settings**

    - Chọn **Enable auot-assign public IPv4 address**
    - Chọn **Save**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/1-VPC/VPC-10.png?featherlight=false&width=60pc)

11. Cấp phát IP thành công

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/1-VPC/VPC-11.png?featherlight=false&width=60pc)

12. Trong giao diện **VPC**

    - Chọn **Internet Gateway**
    - Chọn **Create internet gateway**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/1-VPC/VPC-12.png?featherlight=false&width=60pc)

13. Trong giao diện **Create internet gateway**

    - **Name tag**, nhập **```Internet Gateway VPN```**
    - Chọn **Create internet gateway**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/1-VPC/VPC-13.png?featherlight=false&width=60pc)

14. Sau khi tạo **Internet Gateway VPN** thành công và **State** là **Detached**. Tiếp theo chúng ta cần Attach Internet Gateway vào VPC ASG VPN.

    - Chọn **Actions**
    - Chọn **Attach to VPC**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/1-VPC/VPC-14.png?featherlight=false&width=60pc)

15. Chọn **VPC ASG VPN**, VPC ID sẽ được tự động điền.

    - Chọn **Attach Internet Gateway**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/1-VPC/VPC-15.png?featherlight=false&width=60pc)

16. **Attach** thành công khi **State** là **Attached**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/1-VPC/VPC-16.png?featherlight=false&width=60pc)

17. Tiếp theo chúng ta cần tạo Route Table định tuyến đi ra ngoài internet thông qua Internet Gateway. Trong giao diện **VPC**

    - Chọn **Route Tables**
    - Chọn **Create route table**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/1-VPC/VPC-17.png?featherlight=false&width=60pc)

18. Trong giao diện **Cretae route table**

    - **Name**, nhập **```Route table VPN - Public```**
    - Chọn **VPC** có tên **ASG VPN** , **VPC id** sẽ được tự động điền vào.
    - Chọn **Create route table**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/1-VPC/VPC-18.png?featherlight=false&width=60pc)

19.  Tạo route table thành công. Trong giao diện **Route table VPN - Public**
    
        - Chọn **Route**
        - Chọn **Edit route**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/1-VPC/VPC-19.png?featherlight=false&width=60pc)

20.   Trong giao diện **Edit routes**

        - Chọn **Add route**
        - Điền phần **Destination CIDR** : **0.0.0.0/0** đại diện cho Internet.
        - Trong phần **Target** chọn **Internet Gateway**, sau đó chọn **Internet Gateway VPN** chúng ta đã tạo. **Internet Gateway ID** sẽ được tự động điền.
        - Chọn **Save changes**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/1-VPC/VPC-20.png?featherlight=false&width=60pc)

21.  Trong giao diện **Route table VPN - Public**

        - Chọn **Subnet associations**
        - Chọn **Edit subnet associations**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/1-VPC/VPC-21.png?featherlight=false&width=60pc)


22.  Trong giao diện **Edit subnet associations**

        - Mở rộng cột Subnet ID bằng cách kéo thanh ngăn sang phải.
        - Chọn **subnet VPN Public**.
        - Chọn **Save associations**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/1-VPC/VPC-22.png?featherlight=false&width=60pc)

23.   Hoàn thành và kiểm tra lại **Routes**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/1-VPC/VPC-23.png?featherlight=false&width=60pc)
