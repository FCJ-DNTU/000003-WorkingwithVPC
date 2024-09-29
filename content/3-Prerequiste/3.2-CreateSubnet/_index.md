---
title : "Create Subnet"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 3.2 </b> "
---

## Create Subnet

1. In the **VPC** Interface:
   - Select **Subnets**
   - Select **Create subnet**
   
![Create VPC](/images/3-Preparation-steps-update/2-Create-Subnet/Subnet-1.png?featherlight=false&width=60pc)

2. In the **Create subnet** Interface:
   - Select **ASG** VPC
   
![Create VPC](/images/3-Preparation-steps-update/2-Create-Subnet/Subnet-2.png?featherlight=false&width=60pc)

3. Implement **Subnet Settings**:
   - **Subnet name**: Enter **`Public Subnet 1`**
   - Select AZ **ap-southeast-1a**
   - **IPv4 CIDR block**: Import **`10.10.1.0/24`** according to the architecture description
   - Select **Create subnet**
   
![Create VPC](/images/3-Preparation-steps-update/2-Create-Subnet/Subnet-3.png?featherlight=false&width=60pc)

4. Finish Creating **Subnet**
   
![Create VPC](/images/3-Preparation-steps-update/2-Create-Subnet/Subnet-4.png?featherlight=false&width=60pc)

5. Follow the same steps to create more subnets:
   - **Public subnet 2** with **CIDR** of **`10.10.2.0/24`** located in **Availability Zone ap-southeast-1b**
   
![Create VPC](/images/3-Preparation-steps-update/2-Create-Subnet/Subnet-5.png?featherlight=false&width=60pc)

   - **Private subnet 1** with **CIDR** of **`10.10.3.0/24`** located in **Availability Zone ap-southeast-1a**
   
![Create VPC](/images/3-Preparation-steps-update/2-Create-Subnet/Subnet-6.png?featherlight=false&width=60pc)

   - **Private subnet 2** with **CIDR** of **`10.10.4.0/24`** located in **Availability Zone ap-southeast-1b**
   
![Create VPC](/images/3-Preparation-steps-update/2-Create-Subnet/Subnet-7.png?featherlight=false&width=60pc)

{{% notice tip %}}
 You can see there are 2 columns: **Availability Zone** and **Availability Zone ID**. To avoid uneven usage of EC2 resources (for example, using AZ a for primary and AZ b for standby), AWS randomly assigns **Availability Zone** into **Availability Zone ID**. Availability Zone is an alias, and Availability Zone ID is the identifier. For instance, in the image above, Availability Zone ap-southeast-1a is assigned the Availability Zone ID apse1-az2. In another AWS account, Availability Zone ap-southeast-1a may have an Availability Zone ID of apse1-az1.
{{% /notice %}}


![Create VPC](/images/3-Preparation-steps-update/2-Create-Subnet/Subnet-8.png?featherlight=false&width=60pc)

## Allow Automatic Allocation of Public IP Addresses for 2 Public Subnets

{{% notice tip %}}
 Another important point to note is that even though the subnets are the same, configuring the routing table and allocating a public IP address allows us to distinguish between Public and Private Subnets.
{{% /notice %}}


6. In the **VPC** Interface:
   - Select **Subnets**
   - Select **Public Subnet 1**
   - Select **Actions**
   - Select **Edit subnet settings**
   
![Create VPC](/images/3-Preparation-steps-update/2-Create-Subnet/Subnet-9.png?featherlight=false&width=60pc)

7. Under **Auto-assign IP settings**:
   - Select **Enable auto-assign public IPv4 address**
   - Select **Save**
   
![Create VPC](/images/3-Preparation-steps-update/2-Create-Subnet/Subnet-10.png?featherlight=false&width=60pc)

![Create VPC](/images/3-Preparation-steps-update/2-Create-Subnet/Subnet-11.png?featherlight=false&width=60pc)

8. Repeat the same process for **Public subnet 2**.

![Create VPC](/images/3-Preparation-steps-update/2-Create-Subnet/Subnet-12.png?featherlight=false&width=60pc)

![Create VPC](/images/3-Preparation-steps-update/2-Create-Subnet/Subnet-13.png?featherlight=false&width=60pc)
