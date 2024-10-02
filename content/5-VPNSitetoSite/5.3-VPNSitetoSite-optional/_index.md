---
title : "VPN Connection using Strongswan with Transit Gateway (Optional)"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 5.3 </b> "
---

#### VPN Connection using Strongswan with Transit Gateway

A common model today is for on-premises networks to establish a Site-to-Site VPN connection with **AWS Transit Gateway**, acting as a central router connecting multiple VPCs.

![VPN Configuration](/images/18/image1.png?featherlight=false&width=90pc)

In this model, an **EC2 instance** with the VPN software **strongSwan** is deployed in a VPC to simulate the customer's internal network. This EC2 instance acts as the **Customer Gateway** in the Site-to-Site VPN connection with the AWS Transit Gateway on the AWS side.

StrongSwan is open-source software that supports VPN using the **IPsec** protocol. It is commonly used to establish secure VPN connections between two networks. In this model, strongSwan runs on EC2 and is responsible for encrypting and decrypting data between the internal network and AWS, ensuring the safety of the data flow.

The Transit Gateway acts as a central router, connecting multiple VPCs and on-premises networks through a single VPN connection. Instead of having to set up a VPN for each VPC, only one connection from the internal network to the Transit Gateway is needed, and the system will automatically route traffic to the corresponding VPCs, simplifying management and scaling.

#### Contents:

1. [Create Customer Gateway](5.3.1-create-customer-gateway/)
2. [Create Transit Gateway](5.3.2-create-transit-gateway/)
3. [Create VPN Connection](5.3.3-create-vpn-connection/)
4. [Create Transit Gateway Attachment](5.3.4-create-transit-gateway-attachment/)
5. [Configure Route Tables](5.3.5-configure-route-tables/)
6. [Configure Customer Gateway](5.3.6-configure-customer-gateway/)