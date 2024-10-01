---
title : "Cấu hình Customer Gateway"
date :  "`r Sys.Date()`" 
weight : 6
chapter : false
pre : " <b> 5.3.6 </b> "
---

#### Cấu hình Customer Gateway

1. Truy cập vào **VPC**
    - Chọn **Site-to-Site VPN Connection**
    - Chọn **VPN Connection** đã tạo
    - Chọn **Download Configuration**
    
    ![VPN Configuration](/images/24/image%201.png?featherlight=false&width=90pc)
    
2. Trong hộp thoại **Download Configuration**, lựa chọn **appliance** phù hợp với bạn: Trong bài thực hành này, chúng ta sẽ sử dụng **Strongswan**.
    - **Vendor**: Chọn **Strongswan**
    - **Platform:** Unbuntu 16.04
    - **Software: Strongswan 5.5.1+**
    - **IKE version: ikev1**
    - Chọn **Download**.

![VPN Configuration](/images/24/image%202.png?featherlight=false&width=90pc)

3. Lưu thông tin file cấu hình vào thư mục chúng ta sử dụng lưu trữ key pair và công cụ cho bài lab.
    - Sau đó dựa vào cấu hình được cung cấp, bạn thay đổi các thông tin phù hợp và cấu hình cho thiết bị của mình.

![VPN Configuration](https://000003.awsstudygroup.com/images/13/0003.png?featherlight=false&width=90pc)

- Kết nối ssh vào **EC2 Customer Gateway**.

![VPN Configuration](/images/24/image%203.png?featherlight=false&width=90pc)

4. Cấu hình file **/etc/sysctl.conf**

```
vi /etc/sysctl.conf
```

![VPN Configuration](/images/24/image%204.png?featherlight=false&width=90pc)

- Chuyển xuống vị trí cuối cùng trong file cấu hình. Ấn phím **i** để tiến hành chỉnh sửa file.
- Thêm cấu đoạn sau vào cuối tập tin cấu hình.

```
net.ipv4.ip_forward = 1
net.ipv4.conf.all.accept_redirects = 0
net.ipv4.conf.all.send_redirects = 0
```

- Ấn phím **ESC** và tổ hợp **:wq!** để lưu file cấu hình.

![VPN Configuration](/images/24/image%205.png?featherlight=false&width=90pc)

5. Sau đó để áp dụng cấu hình này, chạy lệnh:

```
sysctl -p
```

![VPN Configuration](/images/24/image%206.png?featherlight=false&width=90pc)

6. Cài đặt **Strongswan**

```
sudo su
amazon-linux-extras install epel -y
yum install strongswan -y
```

![VPN Configuration](/images/24/image%207.png?featherlight=false&width=90pc)

7. Sau khi cài đặt chúng ta có các file và folder như hình dưới.

```
ls -la /etc/strongswan/
```

![VPN Configuration](/images/24/image%208.png?featherlight=false&width=90pc)

8. Cấu hình file ipsec.conf

```bash
vi /etc/strongswan/ipsec.conf
```

![VPN Configuration](/images/24/image%209.png?featherlight=false&width=90pc)

- Gõ lệnh `:%d` để xóa tất cả
- Ấn phím **i** để tiến hành chỉnh sửa file.
- Thêm cấu đoạn sau vào tập tin cấu hình. Chúng ta sẽ tạo **2 Tunnel** với thông tin được lấy từ file cấu hình **VPN Connection** bạn đã tải về và lưu chung vào thư mục chứa key pair trước đó.
- Đảm bảo bạn chỉnh sửa địa chỉ IP và lớp mạng phù hợp trước khi copy đoạn cấu hình trên.
- **leftid**: **IP Public Address phía Onprem**. (Ở đây chính là **IP public** của **EC2 Customer Gateway trong ASG VPN VPC**).
- **right**: **IP Public Address phía AWS VPN Tunnel**.
- **leftsubnet**: **CIDR của Mạng phía Local** (Nếu có nhiều lớp mạng, bạn có thể để là **0.0.0.0/0**).
- **rightsubnet**: **CIDR của Mạng phía Private Subnet trên AWS**.
- Ấn phím **ESC** và tổ hợp **:wq!** để lưu file cấu hình.

```bash
conn Tunnel1
    authby=secret
    auto=start
    left=%defaultroute
    leftid=YOUR_ONPREM_PUBLIC_IP
    right=AWS_VPN_TUNNEL1_IP
    ike=aes128-sha1-modp1024
    esp=aes128-sha1-modp1024
    keyexchange=ike
    ikelifetime=8h
    keylife=1h
    dpdaction=restart
    dpddelay=10s
    dpdtimeout=30s
    leftsubnet=10.11.0.0/16
    rightsubnet=10.10.0.0/16
    type=tunnel

conn Tunnel2
    authby=secret
    auto=start
    left=%defaultroute
    leftid=YOUR_ONPREM_PUBLIC_IP
    right=AWS_VPN_TUNNEL2_IP
    ike=aes128-sha1-modp1024
    esp=aes128-sha1-modp1024
    keyexchange=ike
    ikelifetime=8h
    keylife=1h
    dpdaction=restart
    dpddelay=10s
    dpdtimeout=30s
    leftsubnet=10.11.0.0/16
    rightsubnet=10.10.0.0/16
    type=tunnel
```

![VPN Configuration](/images/24/image%2010.png?featherlight=false&width=90pc)

9. Chỉnh sửa file **/etc/strongswan/ipsec.secrets** để thiết lập chứng thực cho 2 Tunnel.
    - Chạy lệnh `vi /etc/strongswan/ipsec.secrets` để tạo tập tin.
    - Gõ lệnh `:%d` để xóa tất cả
    - Thêm cấu đoạn sau vào cuối tập tin cấu hình (đoạn cấu hình này ở bước 4 của **IPSEC Tunnel #1** và **IPSEC Tunnel #2**)

```bash
13.208.242.73 13.208.84.230 : PSK "g2XToPyWlZALYxaIRtEkmrMV1vbh_IYR"
13.208.242.73 13.208.68.96 : PSK "EGBSrQnCXxJ881JL_Q3V1rMM1DpbL5RY"
```

![VPN Configuration](/images/24/image%2011.png?featherlight=false&width=90pc)

- Ấn phím **ESC** và tổ hợp `:wq!` để lưu file cấu hình.
- Chạy lệnh `cat /etc/strongswan/ipsec.secrets` để kiểm tra nội dung file cấu hình

![VPN Configuration](/images/24/image%2012.png?featherlight=false&width=90pc)

10. **Khởi động strongSwan**:
    - Bật và khởi động strongSwan:
    
    ```bash
    sudo systemctl enable strongswan
    sudo systemctl start strongswan
    sudo systemctl status strongswan
    ```
    
    ![VPN Configuration](/images/24/image%2013.png?featherlight=false&width=90pc)
    
11. **Kiểm tra trạng thái kết nối**:
    - Kiểm tra trạng thái VPN bằng cách sử dụng lệnh:
    
    ```bash
    sudo swanctl --list-conns
    ```
    
    ![VPN Configuration](/images/24/image%2014.png?featherlight=false&width=90pc)
    
    - Kiểm tra trạng thái **PSK** (Pre-Shared Key):
    
    ```bash
    sudo swanctl --list-sas
    ```
    
    ![VPN Configuration](/images/24/image%2015.png?featherlight=false&width=90pc)
    
    Chúng ta cần chú ý hàng `in` và `out` đây là thông dữ liệu vào và ra thông qua tunnel. Hiện tại nó đang là 0 byte
    
    Kiểm tra trên Tunnel Details của **VPN connections** thì trạng thái của cả hai tunnel đã là **Up**  
    
    ![VPN Configuration](/images/24/image%2016.png?featherlight=false&width=90pc)
    

12. Sau khi hoàn tất cấu hình. Hãy thử thực hiện lệnh ping từ phía máy chủ **Customer Gateway** tới máy chủ **EC2 Private**. Nếu cấu hình VPN thành công bạn sẽ được kết quả như dưới đây.

```bash
ping <EC2 Private IP> -c5
```

![VPN Configuration](/images/24/image%2017.png?featherlight=false&width=90pc)

![VPN Configuration](/images/24/image%2018.png?featherlight=false&width=90pc)

13. Hãy thử thực hiện lệnh ping từ phía máy chủ **EC2 Private đến** máy chủ **Customer Gateway.**

```bash
ping <Customer Gateway IPV4> -c5
```

![VPN Configuration](/images/24/image%2019.png?featherlight=false&width=90pc)

![VPN Configuration](/images/24/image%2020.png?featherlight=false&width=90pc)

14. Hãy thử kiểm tra lưu lượng truyền qua tunnel 

```bash
sudo swanctl --list-sas
```

![VPN Configuration](/images/24/image%2021.png?featherlight=false&width=90pc)

Vậy là chúng ta đã thành công trong việc triển khai VPN Site to Site với Transit gateway bằng vendor Strongswan.