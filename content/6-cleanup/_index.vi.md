---
title : "Dọn dẹp tài nguyên"
date :  "`r Sys.Date()`" 
weight : 6
chapter : false
pre : " <b> 6. </b> "
---
#### Dọn dẹp tài nguyên

Chúng ta sẽ tiến hành xóa các tài nguyên theo thứ tự sau

### Terminate các EC2 Instance.
1. Terminate EC2 instance.
- Truy cập Amazon EC2 console tại địa chỉ [EC2](https://console.aws.amazon.com/ec2/).
- Trên thanh điều hướng bên trái, chọn Intances
- Chọn tất cả EC2 Instance liên quan tới bài lab.
- Chọn **Instance state**
- Chọn **Terminate instance**

![Create VPC](/images/6-Clear-update/Clear-1.png?featherlight=false&width=60pc)

2. Xác nhận terminate.

![Create VPC](/images/6-Clear-update/Clear-2.png?featherlight=false&width=60pc)

#### Xóa NAT Gateway, Elastic IP Address 

- Xóa NAT Gateway và Elastic IP Address. AWS sẽ thu tiền cho các EIP lãng phí nên bạn cần kiểm tra kỹ để tránh bị trừ chi phí ngoài ý muốn.
- Truy cập trang Amazon VPC console tại địa chỉ [VPC](https://console.aws.amazon.com/vpc/)
- Trên thanh điều hướng bên trái , click NAT Gateway.
- Chọn NAT Gateway.
- Click Action.
- Click Delete NAT Gateway.

![Create VPC](/images/6-Clear-update/Clear-3.png?featherlight=false&width=60pc)

- Gõ delete.
- Click Delete để xác nhận xóa NAT Gateway

![Create VPC](/images/6-Clear-update/Clear-4.png?featherlight=false&width=60pc)

![Create VPC](/images/6-Clear-update/Clear-5.png?featherlight=false&width=60pc)

#### Xóa xóa Elastic IP Address.
- Tiếp tục xóa Elastic IP Address.
- Truy cập trang Amazon VPC console tại địa chỉ https://console.aws.amazon.com/vpc/
- Trên thanh điều hướng bên trái , click Elastic IP.
- Chọn Elastic IP Address chúng ta đã tạo.
- Click Action.
- Click Release Elastic IP Address
- Click Release.

![Create VPC](/images/6-Clear-update/Clear-6.png?featherlight=false&width=60pc)

![Create VPC](/images/6-Clear-update/Clear-7.png?featherlight=false&width=60pc)

#### Xóa EC2 Instance concect endpoint
- Truy cập vào giao dịch Endpoint
- Chọn Action, chọn Delete VPC endpoints
- Nhập delete
![Create VPC](/images/16/00020.png?featherlight=false&width=90pc)

#### Tiếp tục làm tương tự và xóa theo thứ tự sau nhé:
- VPN Site to Site connection.

![Create VPC](/images/6-Clear-update/Clear-8.png?featherlight=false&width=60pc)

![Create VPC](/images/6-Clear-update/Clear-9.png?featherlight=false&width=60pc)

- Virtual Private Gateway.
  
![Create VPC](/images/6-Clear-update/Clear-10.png?featherlight=false&width=60pc)

![Create VPC](/images/6-Clear-update/Clear-11.png?featherlight=false&width=60pc)

![Create VPC](/images/6-Clear-update/Clear-12.png?featherlight=false&width=60pc)

![Create VPC](/images/6-Clear-update/Clear-13.png?featherlight=false&width=60pc)

- Customer Gateway.

![Create VPC](/images/6-Clear-update/Clear-14.png?featherlight=false&width=60pc)

![Create VPC](/images/6-Clear-update/Clear-15.png?featherlight=false&width=60pc)

- VPC ASG VPN

![Create VPC](/images/6-Clear-update/Clear-16.png?featherlight=false&width=60pc)

![Create VPC](/images/6-Clear-update/Clear-17.png?featherlight=false&width=60pc)

- VPC ASG.

![Create VPC](/images/6-Clear-update/Clear-18.png?featherlight=false&width=60pc)

![Create VPC](/images/6-Clear-update/Clear-19.png?featherlight=false&width=60pc)
