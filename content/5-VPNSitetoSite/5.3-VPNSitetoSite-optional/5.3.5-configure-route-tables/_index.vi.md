---
title : "Cấu hình Route Tables"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 5.3.5 </b> "
---

#### Cấu hình Route Tables transit gateway và VPC 

Tiếp theo chúng ta sẽ tạo một Route Static đến VPC `ASG VPN` 

1. Truy cập vào **VPC**
    - Chọn **Transit gateway route tables**
    - Chọn **Transit gateway route tables** đã được tạo ra mặc định đảm bảo rằng đang có hai attachment
    
    ![VPN Configuration](/images/23/image.png?featherlight=false&width=90pc)
    
    - Chuyển qua Tab Routes
    - Chọn Create static route
    
    ![VPN Configuration](/images/23/image%201.png?featherlight=false&width=90pc)

2. Trong giao diện **Create Create static route**
    - CIDR, nhập CIDR của ASG VPN: `10.11.0.0/16`
    - Type: `Active`
    - Choose attachment, chọn `VPN`
    - Nhấn **Create static route**

![VPN Configuration](/images/23/image%202.png?featherlight=false&width=90pc)

Đã tạo thành công 

![VPN Configuration](/images/23/image%203.png?featherlight=false&width=90pc)

Truy cập vào **Route tables** 

- Chọn Route table-Public
- Chọn tab Routes
- Chọn Edit routes

![VPN Configuration](/images/23/image%204.png?featherlight=false&width=90pc)

Tại giao diện **Edit routes**

- Chọn Route table-Public
- Chọn Add Route
- **Destination, điền `10.11.0.0/16`**
- **Target,** chọn Transit Gateway

![VPN Configuration](/images/23/image%205.png?featherlight=false&width=90pc)

Kết quả

![VPN Configuration](/images/23/image%206.png?featherlight=false&width=90pc)

Chúng ta thực hiện tương tự ở Route table - Private

![VPN Configuration](/images/23/image%207.png?featherlight=false&width=90pc)