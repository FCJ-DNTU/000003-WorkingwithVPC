---
title : "Create Internet Gateway"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3.3 </b> "
---

## Create an Internet Gateway

1. In the **VPC** interface:
   - Select **Internet Gateways**
   - Click on **Create internet gateway**  
![Create VPC](/images/3-Preparation-steps-update/3-Internet-Gateway/IG-1.png?featherlight=false&width=60pc)

2. Configure the internet gateway:
   - Enter **```Internet Gateway```** for the **Name tag**
   - Click on **Create internet gateway**  

![Create VPC](/images/3-Preparation-steps-update/3-Internet-Gateway/IG-2.png?featherlight=false&width=60pc)

3. Complete the creation of the **Internet Gateway**  

![Create VPC](/images/3-Preparation-steps-update/3-Internet-Gateway/IG-3.png?featherlight=false&width=60pc)

4. Implement **Attach VPC**:
   - Click on **Actions**
   - Click on **Attach to VPC**
   - Select **ASG**; the VPC ID will be automatically populated
   - Click on **Attach internet gateway**  

![Create VPC](/images/3-Preparation-steps-update/3-Internet-Gateway/IG-4.png?featherlight=false&width=60pc)

5. Once attached successfully, the **State** of the internet gateway will change to **Attached**  

![Create VPC](/images/3-Preparation-steps-update/3-Internet-Gateway/IG-5.png?featherlight=false&width=60pc)
