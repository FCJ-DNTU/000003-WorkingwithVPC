---
title : "Cấu hình VPN bằng Strongswan với Transit Gateway (Optional)"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 5.3 </b> "
---

#### Kết nối VPN bằng Strongswan với Transit Gateway

Một mô hình phổ biến hiện nay là việc mạng nội bộ (on-premises) thiết lập kết nối VPN Site-to-Site với **AWS Transit Gateway**, đóng vai trò như bộ định tuyến trung tâm kết nối nhiều VPC.

![image.png]![VPN Configuration](/images/18/image1.png?featherlight=false&width=90pc)

Trong mô hình này, một **EC2 instance** với phần mềm VPN **strongSwan** được triển khai trong một VPC để mô phỏng mạng nội bộ của khách hàng. EC2 này đóng vai trò là **Customer Gateway** (đầu bên khách hàng) trong kết nối VPN Site-to-Site với AWS Transit Gateway ở phía AWS.

StrongSwan là phần mềm mã nguồn mở hỗ trợ VPN sử dụng giao thức **IPsec**. Nó thường được dùng để thiết lập kết nối VPN bảo mật giữa hai mạng. Trong mô hình này, strongSwan chạy trên EC2 và chịu trách nhiệm mã hóa, giải mã dữ liệu giữa mạng nội bộ và AWS, đảm bảo an toàn cho luồng dữ liệu.

Transit Gateway đóng vai trò làm bộ định tuyến trung tâm, kết nối nhiều VPC và mạng nội bộ qua một kết nối VPN duy nhất. Thay vì phải thiết lập VPN cho từng VPC, chỉ cần một kết nối từ mạng nội bộ đến Transit Gateway, hệ thống sẽ tự động định tuyến lưu lượng đến các VPC tương ứng, giúp đơn giản hóa việc quản lý và mở rộng.

#### Nội dung:

1. [Tạo Customer Gateway](5.3.1-create-customer-gateway/)
2. [Tạo Transit Gateway](5.3.2-create-transit-gateway/)
3. [Tạo kết nối VPN](5.3.3-create-vpn-connection/)
4. [Tạo Transit Gateway Attachment](5.3.4-create-transit-gateway-attachment/)
5. [Cấu hình Route Tables](5.3.5-configure-route-tables/)
6. [Cấu hình Customer Gateway](5.3.6-configure-customer-gateway/)