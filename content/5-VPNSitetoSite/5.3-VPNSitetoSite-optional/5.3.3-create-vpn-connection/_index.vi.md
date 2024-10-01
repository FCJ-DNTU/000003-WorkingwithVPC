---
title : "Tạo kết nối VPN"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 5.3.3 </b> "
---

### Tạo kết nối VPN

1. Truy cập **VPC**
    - Chọn **Site-to-Site VPN Connections**
    - Chọn **Create VPN Connection**
    
    ![VPN Configuration](/images/21/image.png?featherlight=false&width=90pc)
    
2. Trong giao diện **Create VPN Connection**
    - **Name tag**, nhập **`VPN Connection`**
    - **Target Gateway Type**: Chọn **Transit gateway**
    - **Transit gateway**: Chọn **Transit Gateway ASG**
    - **Customer Gateway**: **Existing**
    - **Customer Gateway ID**: Chọn **Customer Gateway**
    - **Routing Options**: **Static**
    - Các cấu hình khác giữ nguyên mặc định.

![VPN Configuration](/images/21/image%201.png?featherlight=false&width=90pc)

3. Chọn **Create VPN Connection**

![VPN Configuration](/images/21/image%202.png?featherlight=false&width=90pc)

4. Đợi khoảng 5 phút sau, hoàn tất tạo **VPN Connection**

![VPN Configuration](/images/21/image%203.png?featherlight=false&width=90pc)

5. Có thể thấy trạng thái của Tunnel đang là Down. Chúng ta sẽ cấu hình trong Customer Gateway Instance để trạng thái chuyển thành Up

![VPN Configuration](/images/21/image%204.png?featherlight=false&width=90pc)
