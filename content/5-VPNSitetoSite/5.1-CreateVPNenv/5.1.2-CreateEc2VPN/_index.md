---
title : "Create EC2 as a Customer Gateway"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 5.1.2 </b> "
---
## Create EC2 as a Customer Gateway

1. **Access to VPC**

   - Select **Security Group**
   - Select **Create security group**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/2-EC2/EC2-1.png?featherlight=false&width=60pc)

2. **In the Create security group interface**

   - **Security group name**: Enter **`VPN Public -SG`**
   - **Description**: Allow IPSec, SSH, and Ping for servers in the public subnet.
   - **VPC**: Select **ASG VPN** VPC

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/2-EC2/EC2-2.png?featherlight=false&width=60pc)

3. **Configure Inbound rules**

   - Select **Add rule**
   - **Type**: **SSH**, **Source**: **My IP** (Your public IPv4 address).
   - Click **Add rule** to add a new rule.
   - **Type**: **All ICMP IPv4**, **Source**: **Anywhere** (Allow ping from any IP address).
   - Click **Add rule** to add a new rule.
   - **Type**: **Custom UDP**, **Port: 400**, **Source**: **Anywhere**.
   - Click **Add rule** to add a new rule.
   - **Type**: **Custom TCP**, **Port: 500**, **Source**: **Anywhere**.

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/2-EC2/EC2-3.png?featherlight=false&width=60pc)

4. Check **Outbound rules** and select **Create security group**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/2-EC2/EC2-4.png?featherlight=false&width=60pc)

5. Complete the creation of **VPN Public - SG**. A Security Group has been created. Next, we will proceed to create an EC2 server that plays the Customer Gateway role.

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/2-EC2/EC2-5.png?featherlight=false&width=60pc)

6. **Access to EC2**

   - Select **Instances**
   - Select **Launch instances**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/2-EC2/EC2-6.png?featherlight=false&width=60pc)

7. In the **Launch instances** interface

   - **Name**: Enter **`Customer Gateway instance`**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/2-EC2/EC2-7.png?featherlight=false&width=60pc)

8. Executing **AMI** Selection

   - Select **Quick Start**
   - Select **Amazon Linux**
   - Select **AMI**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/2-EC2/EC2-8.png?featherlight=false&width=60pc)

9. Select **Instance type** and select **Key pair**: **aws-keypair** (keypair created with instances)

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/2-EC2/EC2-9.png?featherlight=false&width=60pc)

10. Configure **Network**

    - **VPC**: Select **ASG VPN** VPC
    - **Subnet**: Select **VPN Public**
    - **Auto-assign public IP**: Select **Enable**
    - **Firewall**: Select **Select existing security group**
    - Select **VPN Public - SG**
    - Check again and select **Launch instance**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/2-EC2/EC2-10.png?featherlight=false&width=60pc)

11. Finish creating the **EC2 instance**

    - Select **View all instances**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/2-EC2/EC2-11.png?featherlight=false&width=60pc)

12. View details of the **Customer Gateway instance**

![Create VPC](/images/5-SitetositeVPN-update/1-Create-environment/2-EC2/EC2-12.png?featherlight=false&width=60pc)
