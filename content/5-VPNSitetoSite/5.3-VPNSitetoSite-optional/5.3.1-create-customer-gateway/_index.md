---
title : "Create Virtual Private Gateway"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 5.3.1 </b> "
---

#### Create Customer Gateway

1. Access **VPC**
    - Select **Customer Gateways**
    - Click **Create Customer Gateway**

![VPN Configuration](/images/19/image.png?featherlight=false&width=90pc)

2. In the **Create Customer Gateway** interface
    - **Name tag**, enter **`Customer Gateway`**
    - **IP address**, enter the **public IP address** of the **EC2 Customer Gateway**.
    - Click **Create Customer Gateway**

![VPN Configuration](/images/19/image%201.png?featherlight=false&width=90pc)

3. Wait about 5 minutes to complete the creation of the **Customer Gateway**

![VPN Configuration](/images/19/image%202.png?featherlight=false&width=90pc)

{{% notice tip %}}
Note: According to the architectural model, the Customer Gateway will be located in the VPC in the on-premises environment. Currently, we are declaring to AWS that we will have a Customer Gateway with the public IP address being the public address of the EC2 instance: Customer Gateway located in the ASG VPN VPC.
{{% /notice %}}