---
title : "Customer Gateway Configuration"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 5.2.4 </b> "
---

# Configure Customer Gateway

1. Access to VPC
- Select **Site-to-Site VPN Connection**
- Select **VPN Connection** created
- Select **Download Configuration**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/4-Config/Config-1.png?featherlight=false&width=60pc)

2. Download Configuration
In the **Download Configuration** dialog, choose the appropriate **appliance**, e.g., **OpenSwan**.

- **Vendor**: Select **OpenSwan**
- **Platform**: Select **OpenSwan**
- **Software**: Select **OpenSwan 2.6.38+**
- **IKE version**: Select **ikev1**
- Select **Download**.

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/4-Config/Config-2.png?featherlight=false&width=60pc)

3. Save the image file information to the folder used for storing the key pair and lab tools. Modify the configuration based on your device.

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/4-Config/Config-3.png?featherlight=false&width=60pc)

Connect SSH to **EC2 Customer Gateway**.

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/4-Config/Config-4.png?featherlight=false&width=60pc)

4. Install **OpenSwan**

```
sudo su
yum install openswan -y
```
![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/4-Config/Config-5.png?featherlight=false&width=60pc)


5. Check the configuration file **/etc/ipsec.conf**

```
vi /etc/ipsec.conf
```
- Check the configuration is as shown below.

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/4-Config/Config-6.png?featherlight=false&width=60pc)

- Press the **ESC** key and the combination **:q!** to exit the **vi** editor.

6. Configuration file **/etc/sysctl.conf**

```
vi /etc/sysctl.conf
```

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/4-Config/Config-7.png?featherlight=false&width=60pc)

- Move down to the last position in the configuration file. Press the **i** key to proceed with editing the file.
- Add the following configuration at the end of the configuration file.

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/4-Config/Config-8.png?featherlight=false&width=60pc)

- Press the **ESC** key and the combination **:wq!** to save the configuration file.

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/4-Config/Config-9.png?featherlight=false&width=60pc)

7. Then to apply this configuration, run the command:

```
sysctl -p
```

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/4-Config/Config-10.png?featherlight=false&width=60pc)

8. Next we will configure the file **/etc/ipsec.d/aws.conf**

   
```
vi /etc/ipsec.d/aws.conf
```

   - Press **i** to proceed to edit the file.
   - Add the following configuration to the configuration file. We will create **2 Tunnel** with information taken from the **VPN Connection** configuration file you downloaded and saved in the folder containing the key pair earlier.
   - Make sure you edit the IP address and network class accordingly before copying the above configuration.
   - For **Amazon Linux**, we will omit the **auth=esp** line in the original configuration file.
   - Since we only have **1 public IP addres** for **Customer Gateway**, we will need to configure **overlapip=yes**.
   - **leftid**: **IP Public Address on the Onprem side**. (Here is **public IP** of **EC2 Customer Gateway in ASG VPN VPC**) .
   - **right**: **IP Public Address on AWS VPN Tunnel** side.
   - **leftsubnet**: **CIDR of Local Side Network** (If there are multiple network layers, you can leave it as **0.0.0.0/0**).
   - **rightsubnet**: **CIDR of Private Subnet on AWS**.
   - Based on downloaded configuration file.
  
![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/4-Config/Config-11.png?featherlight=false&width=60pc)

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/4-Config/Config-12.png?featherlight=false&width=60pc)

   - Check code.
  
![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/4-Config/Config-13.png?featherlight=false&width=60pc)

- Press the **ESC** key and the combination **:wq!** to save the configuration file.

9. Check the next step in the configuration file we downloaded.

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/4-Config/Config-14.png?featherlight=false&width=60pc)

10. Create and configure the file **etc/ipsec.d/aws.secrets** Create a new file with the following configuration to set up authentication for the 2 Tunnels.

- Run the command **touch /etc/ipsec.d/aws.secrets** to create the file.

```
touch /etc/ipsec.d/aws.secrets
```
![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/4-Config/Config-15.png?featherlight=false&width=60pc)

- Run the command **vi /etc/ipsec.d/aws.secrets**

```
vi /etc/ipsec.d/aws.secrets
```

11. Press the **i** key to edit the file.

- Add the following configuration to the end of the configuration file (this configuration is in step 5 of **IPSEC Tunnel #1** and **IPSEC Tunnel #2**)

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/4-Config/Config-16.png?featherlight=false&width=60pc)
![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/4-Config/Config-17.png?featherlight=false&width=60pc)

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/4-Config/Config-18.png?featherlight=false&width=60pc)


- Press the **ESC** key and the combination **:wq!** to save the configuration file.
- Run the command **cat /etc/ipsec.d/aws.secrets** to check the content of the configuration file

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/4-Config/Config-19.png?featherlight=false&width=60pc)

12. Restart **Network service & IPSEC service**

```
service network restart
chkconfig ipsec on
service ipsec start
service ipsec status
```

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/4-Config/Config-20.png?featherlight=false&width=60pc)


- If the status tunnel is still not running correctly, after checking and updating the configuration you will need to run the command to **restart** **service network and IPsec** :

```
sudo service network restart
sudo service ipsec restart
```

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/4-Config/Config-21.png?featherlight=false&width=60pc)


13. After completing the configuration.Try to ping from the **Customer Gateway** server side to the **EC2 Private** server. If the VPN configuration is successful you will get the result as below.

```
ping <EC2 Private IP> -c5
```

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/4-Config/Config-22.png?featherlight=false&width=60pc)

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/4-Config/Config-23.png?featherlight=false&width=60pc)


14. After completing the configuration.Try to ping from the **EC2 Private** server side to the **Customer Gateway** server. If the VPN configuration is successful you will get the result as below.

```
ping <Customer gateway instance IP> -c5
```

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/4-Config/Config-24.png?featherlight=false&width=60pc)

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/4-Config/Config-25.png?featherlight=false&width=60pc)
