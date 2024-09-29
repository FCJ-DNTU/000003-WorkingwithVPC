---
title : "Create Route Table"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 3.4 </b> "
---

## Create Route Table for Outbound Internet Routing via Internet Gateway

1. In the **VPC** interface:

   - Select **Route Tables**.
   - Click on **Create route table**.
   
![Create VPC](/images/3-Preparation-steps-update/4-Route-Table/RTB-1.png?featherlight=false&width=60pc)

2. Configure the **Route table**:

   - Enter a **Name**: **```Route table-Public```**
   - Choose the **VPC**: Select **ASG** VPC (VPC ID will auto-fill).
   - Click on **Create route table**.
   
![Create VPC](/images/3-Preparation-steps-update/4-Route-Table/RTB-2.png?featherlight=false&width=60pc)

3. Complete creating the **Route table**.

![Create VPC](/images/3-Preparation-steps-update/4-Route-Table/RTB-3.png?featherlight=false&width=60pc)

4. To make route edits:

   - Select **Actions**.
   - Choose **Edit routes**.
   
![Create VPC](/images/3-Preparation-steps-update/4-Route-Table/RTB-4.png?featherlight=false&width=60pc)

5. In the **Edit routes** interface:

   - Click on **Add route**.
   - Fill in the **Destination CIDR**: **```0.0.0.0/0```** representing the Internet.
   - In the **Target** section, select **Internet Gateway**, then choose the created **Internet Gateway** (Gateway ID auto-fills).
   - Click **Save changes**.
   
![Create VPC](/images/3-Preparation-steps-update/4-Route-Table/RTB-5.png?featherlight=false&width=60pc)

6. Review and confirm the updated **Routes**.

   - Select **Subnet Associations**.
   - Click on **Edit subnet associations**.
   
![Create VPC](/images/3-Preparation-steps-update/4-Route-Table/RTB-6.png?featherlight=false&width=60pc)

7. In the **Edit subnet associations** step:

   - Adjust the width of the **Subnet ID** column by dragging the pane to the right.
   - Select the appropriate **2 public subnets** that were created.
   - Click on **Save associations**.

![Create VPC](/images/3-Preparation-steps-update/4-Route-Table/RTB-7.png?featherlight=false&width=60pc)

8.  Review and confirm the updated **Subnet associations**.

![Create VPC](/images/3-Preparation-steps-update/4-Route-Table/RTB-8.png?featherlight=false&width=60pc)
