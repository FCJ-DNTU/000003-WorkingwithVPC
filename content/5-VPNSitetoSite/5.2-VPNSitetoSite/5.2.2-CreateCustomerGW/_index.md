---
title : "Create Customer Gateway"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 5.2.2 </b> "
---

## Create Customer Gateway

1. Access the **VPC**:
   - Navigate to **Customer Gateways**
   - Click on **Create Customer Gateway**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/2-CG/CG-1.png?featherlight=false&width=90pc)

2. In the **Create Customer Gateway** interface:
   - Set the **Name tag** to **`Customer Gateway`**
   - Enter the **IP address** as the public IP address of the **EC2 Customer Gateway** server
   - Click on **Create Customer Gateway**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/2-CG/CG-2.png?featherlight=false&width=90pc)

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/2-CG/CG-3.png?featherlight=false&width=90pc)

3. Wait for approximately 5 minutes for the **Customer Gateway** creation to complete:

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/2-CG/CG-4.png?featherlight=false&width=90pc)

{{% notice tip %}}
According to the architectural model, the Customer Gateway will reside in the VPC in the on-premise environment. The current action declares to AWS the intent to create a Customer Gateway with a public IP address, which corresponds to the public address of the EC2 instance. This Customer Gateway is located in the ASG VPN VPC.
{{% /notice %}}
