---
title : "Configure Route Tables"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 5.3.5 </b> "
---

#### Configure Transit Gateway and VPC Route Tables

Next, we will create a Static Route to the VPC `ASG VPN`.

1. Access **VPC**
    - Select **Transit gateway route tables**
    - Choose the **Transit gateway route tables** that have been created by default, ensuring that there are two attachments
    
    ![VPN Configuration](/images/23/image.png?featherlight=false&width=90pc)
    
    - Switch to the Routes tab
    - Select Create static route
    
    ![VPN Configuration](/images/23/image%201.png?featherlight=false&width=90pc)

2. In the **Create static route** interface
    - CIDR, enter the CIDR of ASG VPN: `10.11.0.0/16`
    - Type: `Active`
    - Choose attachment, select `VPN`
    - Click **Create static route**

![VPN Configuration](/images/23/image%202.png?featherlight=false&width=90pc)

Successfully created 

![VPN Configuration](/images/23/image%203.png?featherlight=false&width=90pc)

Access **Route tables** 

- Select Route table-Public
- Choose the Routes tab
- Select Edit routes

![VPN Configuration](/images/23/image%204.png?featherlight=false&width=90pc)

In the **Edit routes** interface

- Select Route table-Public
- Choose Add Route
- **Destination, enter `10.11.0.0/16`**
- **Target,** select Transit Gateway

![VPN Configuration](/images/23/image%205.png?featherlight=false&width=90pc)

Result

![VPN Configuration](/images/23/image%206.png?featherlight=false&width=90pc)

We perform similarly in the Route table - Private

![VPN Configuration](/images/23/image%207.png?featherlight=false&width=90pc)