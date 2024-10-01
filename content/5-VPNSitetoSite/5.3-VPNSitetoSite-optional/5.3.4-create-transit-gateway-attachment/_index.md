---
title : "Create Transit Gateway Attachment"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 5.3.4 </b> "
---

#### Create Transit Gateway Attachment

![VPN Configuration](/images/22/image.png?featherlight=false&width=90pc)

By default, when creating a Transit Gateway VPN connection, the **Transit Gateway Attachments** interface automatically creates a VPN attachment for us. We will create an additional attachment for the VPC ASG.

1. Access **VPC**
    - Select **Transit Gateway Attachment**
    - Click **Create transit gateway attachment**

![VPN Configuration](/images/22/image%201.png?featherlight=false&width=90pc)

2. In the **Create transit gateway attachment** interface
    - **Name tag**, enter `VPC Attachment ASG VPN`
    - Transit gateway ID, select `Transit Gateway ASG`
    - Attachment type, select **`VPC`**

![VPN Configuration](/images/22/image%202.png?featherlight=false&width=90pc)

- Click **`Create transit gateway attachment`**

![VPN Configuration](/images/22/image%203.png?featherlight=false&width=90pc)

3. Successfully created **transit gateway attachment**

![VPN Configuration](/images/22/image%204.png?featherlight=false&width=90pc)