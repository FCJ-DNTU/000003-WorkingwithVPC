---
title : "Create EC2 Server"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 4.1 </b> "
---

## Create EC2 Instances in Subnets

1. Access the **AWS Management Console**:

    - Navigate to **EC2**
    - Click on **Instances**

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img1.png?featherlight=false&width=60pc)

2. In the **EC2** interface:

    - Select **Instances**
    - Choose **Launch instances**

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img2.png?featherlight=false&width=60pc)

3. Provide a **Name and tags** for the instance, enter **```EC2 Public```**

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img3.png?featherlight=false&width=60pc)

4. Choose the **AMI**:

    - Select **Quick Start**
    - Choose **Amazon Linux 2**
    - Select an **AMI**

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img4.png?featherlight=false&width=60pc)

5. Select an **Instance type** and opt to **Create a new key pair**

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img5.png?featherlight=false&width=60pc)

6. In the **Create key pair** interface:

    - Specify the **Key pair name**, e.g., **```aws-keypair```** (optional name, you can set any).
    - Choose **Key pair type: RSA**
    - Select **Private key file format: .pem**

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img6.png?featherlight=false&width=60pc)

7. Configure the **Network**:

    - Select the **VPC**: **ASG**
    - Choose the **Subnet**: **Public Subnet 1**
    - Enable **Auto-assign public IP**
    - For **Firewall (Security Group)**, select **Select existing security group**
    - Choose **Public subnet -SG**
    - Click **Launch instance**

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img7.png?featherlight=false&width=60pc)

8. Complete the instance creation

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img8.png?featherlight=false&width=60pc)

9. Wait for about 5 minutes until the **Status check** shows **2/2 checks passed**

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img9.png?featherlight=false&width=60pc)

## Create EC2 in a Private Subnet

10. In the **EC2** interface:

    - Select **Instances**
    - Choose **Launch instances**

11. Provide a **Name and tags**, enter **```EC2 Private```**

     - Select **Quick Start**
     - Choose **Amazon Linux 2**
     - Select an **AMI**

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img10.png?featherlight=false&width=60pc)

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img11.png?featherlight=false&width=60pc)


12. Make an **instance type** selection. Choose **Key pair name: ```aws-keypair```**

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img12.png?featherlight=false&width=60pc)

13. Configure the **Network**:

      - Select the **VPC**: **ASG** VPC
      - Choose the **Subnet**: **Private subnet 2**
      - Disable **Auto-assign public IP**. If not disabling it, ensure you've checked the configuration for **automatically allocating public IP for the subnet.**

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img13.png?featherlight=false&width=60pc)

14. Complete the instance creation:

      - Click **View all instances**

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img14.png?featherlight=false&width=60pc)

15. Select **EC2 Private**:

      - Choose **Details**
      - Store **Private IPv4 addresses**

   ![Create VPC](/images/4-CreateEc2Server-update/1-Create-EC2-Server/EC2-img15.png?featherlight=false&width=60pc)
