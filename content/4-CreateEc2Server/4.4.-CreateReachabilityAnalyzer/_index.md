---
title : "Using Reachability Analyzer"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 4.4 </b> "
---


#### Using Reachability Analyzer

![Create VPC](/images/4-CreateEc2Server-update/4-Using-Reachability-Analyzer/Check-img1.png?featherlight=false&width=60pc)

1. Access to **VPC** interface

   - Select **Reachability Analyzer**
   - Select **Create and analyze path**

![Create VPC](/images/4-CreateEc2Server-update/4-Using-Reachability-Analyzer/Check-img2.png?featherlight=false&width=60pc)

2. Implement **Path Configuration**

   - Name tag, enter **```EC2 private with EC2 Public```**
   - For **Source type**, select **Instance**
   - Select **source** as **EC2 Public**

![Create VPC](/images/4-CreateEc2Server-update/4-Using-Reachability-Analyzer/Check-img3.png?featherlight=false&width=60pc)

   - For **Destination type**, select **Instance**
   - For **Destination**, select **EC2 Private**

![Create VPC](/images/4-CreateEc2Server-update/4-Using-Reachability-Analyzer/Check-img4.png?featherlight=false&width=60pc)

   - The remaining parameters are left to default.
   - Select **Create and analyze path**

![Create VPC](/images/4-CreateEc2Server-update/4-Using-Reachability-Analyzer/Check-img5.png?featherlight=false&width=60pc)

3. Wait 5 minutes will show the **Reachable** status

![Create VPC](/images/4-CreateEc2Server-update/4-Using-Reachability-Analyzer/Check-img6.png?featherlight=false&width=60pc)

![Create VPC](/images/4-CreateEc2Server-update/4-Using-Reachability-Analyzer/Check-img7.png?featherlight=false&width=60pc)

4. Then see path details.

![Create VPC](/images/4-CreateEc2Server-update/4-Using-Reachability-Analyzer/Check-img8.png?featherlight=false&width=60pc)

5. View reverse path details.

![Create VPC](/images/4-CreateEc2Server-update/4-Using-Reachability-Analyzer/Check-img9.png?featherlight=false&width=60pc)
