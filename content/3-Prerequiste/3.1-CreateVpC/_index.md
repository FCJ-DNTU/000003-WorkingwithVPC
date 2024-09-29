---
title : "Create VPC"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 3.1 </b> "
---
## Create VPC

1. Access the **AWS Management Console** interface:
   - Locate and click on **VPC**
   - Choose **VPC**

![Create VPC](/images/3-Preparation-steps-update/1-Create-VPC/VPC-1.png?featherlight=false&width=60pc)

2. Within the **VPC** interface:
   - Select **Your VPC**
   - Click on **Create VPC**

![Create VPC](/images/3-Preparation-steps-update/1-Create-VPC/VPC-2.png?featherlight=false&width=60pc)

3. Follow these steps to create a VPC:
   - Choose **Resource** and select **VPC only**
   - Enter **Name tag** as **`ASG`**
   - Set **IPv4 CIDR** to **`10.10.0.0/16`**

![Create VPC](/images/3-Preparation-steps-update/1-Create-VPC/VPC-3.png?featherlight=false&width=60pc)

{{% notice warning %}}
For the **Tenancy** configuration, it's recommended to keep the default setting. Switching to **Dedicated** may restrict the creation of certain **EC2 Instance types** within the VPC, as they require the default tenancy.
{{% /notice %}}

4. Click on **Create VPC**

![Create VPC](/images/3-Preparation-steps-update/1-Create-VPC/VPC-4.png?featherlight=false&width=60pc)

5. Complete the process of creating the **VPC**

![Create VPC](/images/3-Preparation-steps-update/1-Create-VPC/VPC-5.png?featherlight=false&width=60pc)

6. Review the details of the newly created VPC. Ensure that **Enable DNS resolution and DNS Hostname** is disabled:
   - Go to **Edit VPC settings**
   - Navigate to **DNS settings**
   - Choose and then click **Save**

![Create VPC](/images/3-Preparation-steps-update/1-Create-VPC/VPC-6.png?featherlight=false&width=60pc)
