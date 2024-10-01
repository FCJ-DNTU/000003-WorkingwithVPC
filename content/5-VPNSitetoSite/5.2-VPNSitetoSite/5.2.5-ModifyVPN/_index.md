---
title : "Modify AWS VPN Tunnel"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 5.2.5 </b> "
---

## Modify AWS VPN Tunnel

1. Access the **VPC** Interface:

   - Go to **Site-to-Site VPN connections**.
   - Choose the recently created **VPN**.
   - Click on **Actions**.
   - Select **Modify VPN tunnel options**.

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/5-Modify/Modify-1.png?featherlight=false&width=60pc)

2. Choose the **VPN Tunnel Outside IP Address**:

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/5-Modify/Modify-2.png?featherlight=false&width=60pc)

3. Confirm UP Tunnel Modification and Keep Other Parameters Default:

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/5-Modify/Modify-3.png?featherlight=false&width=60pc)

4. Enable Tunnel Activity Log:

   - Enable **Tunnel activity log**.
   - Choose an existing **Amazon CloudWatch log group** (or create one in CloudWatch if not already done).
   - Set **Output format** to **text**.
   - Click **Save changes**.

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/5-Modify/Modify-4.png?featherlight=false&width=60pc)

5. Access **CloudWatch**:

   - Navigate to **Log groups**.
   - Go to **Log streams**.
   - Choose a log stream.

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/5-Modify/Modify-5.png?featherlight=false&width=60pc)

6. View **Log Events**:

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/5-Modify/Modify-6.png?featherlight=false&width=60pc)

7. Repeat the Process for the Remaining Tunnel(s):

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/5-Modify/Modify-7.png?featherlight=false&width=60pc)
![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/5-Modify/Modify-8.png?featherlight=false&width=60pc)
![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/5-Modify/Modify-9.png?featherlight=false&width=60pc)

8. Verify That Both Tunnels are UP:

![Create VPC](/images/5-SitetositeVPN-update/2-VPN-Connection/5-Modify/Modify-10.png?featherlight=false&width=60pc)
