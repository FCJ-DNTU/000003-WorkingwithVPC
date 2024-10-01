---
title : "Create VPN Connection"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 5.2.3 </b> "
---

## Create a VPN Connection

1. Access **VPC**:
   - Select **Site-to-Site VPN Connections**
   - Select **Create VPN Connection**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/3-VPN/vpn-1.png?featherlight=false&width=60pc)

2. In the **Create VPN Connection** Interface:
   - **Name Tag**: Enter **`VPN Connection`**
   - **Target Gateway Type**: Select **Virtual Private Gateway**
   - **Virtual Private Gateway**: Select **VPN Gateway**
   - **Customer Gateway**: **Existing**
   - **Customer Gateway ID**: Select **Customer Gateway**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/3-VPN/vpn-2.png?featherlight=false&width=60pc)

3. Continue to Perform Configuration:
   - **Routing Options**: **Static**
   - **Static IP Prefixes**: **10.11.0.0/16**. This is the IP address resolution in a simulated On-premise environment.
   - Other configurations keep the default.

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/3-VPN/vpn-3.png?featherlight=false&width=60pc)

4. Select **Create VPN Connection**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/3-VPN/vpn-4.png?featherlight=false&width=60pc)

5. Wait for about 5 minutes to finish creating the **VPN Connection**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/3-VPN/vpn-5.png?featherlight=false&width=60pc)

6. Configure **Propagation** for **Route Tables**:
   - In the **VPC** interface, select **Route Tables**
   - Select **Route table - Public**
   - Select **Route Propagation**
   - Select **Edit Route Propagation**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/3-VPN/vpn-6.png?featherlight=false&width=60pc)

7. In the **Edit Route Propagation** Interface:
   - Select **Enable**
   - Select **Save**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/3-VPN/vpn-7.png?featherlight=false&width=60pc)

8. Complete and Recheck: **Route Propagation** should have changed to **Yes**

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/3-VPN/vpn-8.png?featherlight=false&width=60pc)

9. Similar Route Propagation for Private Subnet:

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/3-VPN/vpn-9.png?featherlight=false&width=60pc)
![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/3-VPN/vpn-10.png?featherlight=false&width=60pc)
![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/3-VPN/vpn-11.png?featherlight=false&width=60pc)
