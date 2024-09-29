---
title : "Kiểm tra kết nối"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 4.2 </b> "
---

#### Kiểm tra kết nối


{{% notice note %}}
Có nhiều cách kết nối EC2, các bạn có thể tham khảo [kết nối EC2 bằng **PuTTY**](https://000004.awsstudygroup.com/vi/4-launchlinuxinstance/4.2-connectlinuxinstance/). Trong bài lab, chúng ta sử dụng [Visual Studio Code](https://code.visualstudio.com/download) để kết nối EC2
{{% /notice %}}

1. Thực hiện tải [Visual Studio Code](https://code.visualstudio.com/download) 

   ![Create VPC](/images/4-CreateEc2Server-update/2-Test-Connection/Connect-img1.png?featherlight=false&width=60pc)

2. Truy cập vào trang **EC2**

   - Chọn **Instances**
   - Chọn **EC2 Public**
   - Chọn **Connect**


   ![Create VPC](/images/4-CreateEc2Server-update/2-Test-Connection/Connect-img2.png?featherlight=false&width=60pc)

3. Trong phần **Connect**

   - Chọn **SSH Client**
   - Sao chép đoạn mã ở phần **Example**

   ![Create VPC](/images/4-CreateEc2Server-update/2-Test-Connection/Connect-img3.png?featherlight=false&width=60pc)

4. Trong giao diện **Visual Studio Code**

   - Tải **SSH**

   ![Create VPC](/images/4-CreateEc2Server-update/2-Test-Connection/Connect-img4.png?featherlight=false&width=60pc)

5. Trên thanh công cụ tìm kiếm của **Visual Studio Code**

   - Làm theo các hướng dẫn để có thể kết nối **SSH**

   ![Create VPC](/images/4-CreateEc2Server-update/2-Test-Connection/Connect-img5.png?featherlight=false&width=60pc)

   ![Create VPC](/images/4-CreateEc2Server-update/2-Test-Connection/Connect-img6.png?featherlight=false&width=60pc)

   ![Create VPC](/images/4-CreateEc2Server-update/2-Test-Connection/Connect-img7.png?featherlight=false&width=60pc)

6. Cấu hình **SSH**.
   - Dán đường dẫn đã sao chép ở trên **EC2 Public** vào đây
   - Sửa đường dẫn **key pair** sao cho dẫn đúng tới file nơi đã lưu trữ
   - Lưu file
  
   ![Create VPC](/images/4-CreateEc2Server-update/2-Test-Connection/Connect-img8.png?featherlight=false&width=60pc)

7. Kết nối **SSH**.
   - Chạy lại các lệnh ở thanh tìm kiếm giống trên
   - Tìm kiếm và chọn vào **IP public EC2** để kết nối
  
   ![Create VPC](/images/4-CreateEc2Server-update/2-Test-Connection/Connect-img9.png?featherlight=false&width=60pc)

   ![Create VPC](/images/4-CreateEc2Server-update/2-Test-Connection/Connect-img10.png?featherlight=false&width=60pc)


8. Kiểm tra kết nối tới internet của EC2 Public, ta thực hiện lệnh:

   ```
   ping amazon.com -c5
   ```

   ![Create VPC](/images/4-CreateEc2Server-update/2-Test-Connection/Connect-img11.png?featherlight=false&width=60pc)




#### Kết nối vào máy chủ EC2 Private và kiểm tra kết nối internet.

9. Truy cập vào **EC2**

   - Chọn **Instances**
   - Chọn **EC2 Private**
   - Chọn **Details**
   - Chọn **Private IPv4 addresses**
   - Sau đó kết nối SSH vào **EC2 Public**

   ![Create VPC](/images/4-CreateEc2Server-update/2-Test-Connection/Connect-img21.png?featherlight=false&width=60pc)

10. Thực hiện lệnh ping **<địa chỉ IP private của EC2 Private>** để kiểm tra kết nối từ máy chủ **EC2 Public** sang máy chủ **EC2 Private**. Chúng ta kiểm tra kết nối giữa 2 EC2 instance bằng câu lệnh:

```
ping <IP Private EC2 Private> -c5
```
   ![Create VPC](/images/4-CreateEc2Server-update/2-Test-Connection/Connect-img22.png?featherlight=false&width=60pc)

11.  **EC2 Private** sẽ không có **public IP address** vì chúng ta không gán cho máy chủ này public IP. Để có thể ssh vào **EC2 Private**, chúng ta sẽ thực hiện kết nối ssh từ EC2 Public thông qua địa chỉ **private IP address của EC2 Private**

     - Download công cụ **pscp** vào cùng thư mục chứa file **aws-keypair.ppk** để thực hiện copy file **aws-keypair.pem** từ máy của chúng ta vào **EC2 Public**.


{{% notice info %}}
Bạn tải [a RSA and DSA key generation utility](https://the.earth.li/~sgtatham/putty/latest/w64/puttygen.exe) là dạng **puttygen.exe**
{{% /notice %}}

{{% notice info %}}
Bạn tải [an SCP client, i.e. command-line secure file copy](https://the.earth.li/~sgtatham/putty/latest/w64/pscp.exe) là **dạng pscp.exe**
{{% /notice %}}

12.  Chúng ta sử dụng **puttygen.exe** để generation key

     - Chọn **Load**

   ![Create VPC](/images/4-CreateEc2Server-update/2-Test-Connection/Connect-img12.png?featherlight=false&width=60pc)

13.  Chọn **aws-keypair.pem**

     - Chọn **OK**
     - Chọn **Save private key** với tên **aws-keypair.ppk**

   ![Create VPC](/images/4-CreateEc2Server-update/2-Test-Connection/Connect-img13.png?featherlight=false&width=60pc)

14.  Hoàn thành generation key

   ![Create VPC](/images/4-CreateEc2Server-update/2-Test-Connection/Connect-img14.png?featherlight=false&width=60pc)

15. Khởi chạy **Command Prompt**. Chuyển đường dẫn tới thư mục bạn vừa download **pscp**. Chạy lệnh dưới đây để upload file **aws-keypair.pem** lên thư mục **/home/ec2-user/** của máy chủ EC2 Public.

    - Bạn sẽ cần thay thế thông số **public IP address của EC2 Public** trước khi chạy câu lệnh.

```
pscp -i aws-keypair.ppk aws-keypair.pem ec2-user@<EC2 PUBLIC public IP address>:/home/ec2-user/
```

   ![Create VPC](/images/4-CreateEc2Server-update/2-Test-Connection/Connect-img15.png?featherlight=false&width=60pc)

16.  Truy cập vào **EC2**

     - Chọn **Instances**
     - Chọn **EC2 Public**
     - Chọn **Details**
     - Xem **Public IPv4 address**

   ![Create VPC](/images/4-CreateEc2Server-update/2-Test-Connection/Connect-img16.png?featherlight=false&width=60pc)

17.   Quay trở lại giao diện kết nối EC2. Để đảm bảo bạn copy file **aws-keypair.pem** lên máy chủ **EC2 Public** ta thực hiện lệnh

```
ls
```

   ![Create VPC](/images/4-CreateEc2Server-update/2-Test-Connection/Connect-img17.png?featherlight=false&width=60pc)

18.  Cập nhật quyền cho file **aws-keypair.pem** bằng cách chạy lệnh **chmod 400 aws-keypair.pem**. AWS yêu cầu file key pair cần được hạn chế quyền truy cập trước khi được sử dụng để kết nối tới máy chủ EC2.

```
chmod 400 aws-keypair.pem
```
   ![Create VPC](/images/4-CreateEc2Server-update/2-Test-Connection/Connect-img18.png?featherlight=false&width=60pc)

19.  **SSH** tới máy chủ **EC2 Private**

```
ssh -i aws-keypair.pem ec2-user@<EC2 Private server's private IP address>
```

   ![Create VPC](/images/4-CreateEc2Server-update/2-Test-Connection/Connect-img19.png?featherlight=false&width=60pc)

20.  Thực hiện **ping test tới amazon.com**. Bạn có thể thấy, chúng ta không thể kết nối **internet từ EC2 Private**. Trong bước tiếp theo chúng ta sẽ tạo **NAT Gateway** để cho phép máy chủ **EC2 Private** kết nối internet theo chiều từ nội bộ đi ra. Giữ nguyên kết nối tới **EC2 Private** để chúng ta có thể kiểm tra kết nối tới **internet** sau khi hoàn tất tạo và cấu hình **NAT Gateway** nhé.

```
ping amazon.com
```

   ![Create VPC](/images/4-CreateEc2Server-update/2-Test-Connection/Connect-img20.png?featherlight=false&width=60pc)



