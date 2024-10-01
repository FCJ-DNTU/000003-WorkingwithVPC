---
title : "Create VPN Connection"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 5.3.3 </b> "
---

### Create VPN Connection

1. Access **VPC**
    - Select **Site-to-Site VPN Connections**
    - Click **Create VPN Connection**
    
    ![VPN Configuration](/images/21/image.png?featherlight=false&width=90pc)
    
2. In the **Create VPN Connection** interface
    - **Name tag**, enter **`VPN Connection`**
    - **Target Gateway Type**: Select **Transit gateway**
    - **Transit gateway**: Choose **Transit Gateway ASG**
    - **Customer Gateway**: **Existing**
    - **Customer Gateway ID**: Select **Customer Gateway**
    - **Routing Options**: **Static**
    - Keep other configurations as default.

![VPN Configuration](/images/21/image%201.png?featherlight=false&width=90pc)

3. Click **Create VPN Connection**

![VPN Configuration](/images/21/image%202.png?featherlight=false&width=90pc)

4. Wait about 5 minutes to complete the creation of the **VPN Connection**

![VPN Configuration](/images/21/image%203.png?featherlight=false&width=90pc)

5. You can see that the status of the Tunnel is currently Down. We will configure in the Customer Gateway Instance to change the status to Up.

![VPN Configuration](/images/21/image%204.png?featherlight=false&width=90pc)
