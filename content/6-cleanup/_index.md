---
title : "Clean up resources"
date : "`r Sys.Date()`"
weight : 6
chapter : false
pre : " <b> 6. </b> "
---
## Clean up resources

We will proceed to delete the resources in the following order:

### Terminate EC2 Instances

1. Terminate EC2 instance:
- Access the Amazon EC2 console at [EC2](https://console.aws.amazon.com/ec2/).
- On the left navigation bar, select "Instances."
- Select all EC2 instances related to the lab.
- Select **Instance state**.
- Select **Terminate instance**.

![Create VPC](/images/6-Clear-update/Clear-1.png?featherlight=false&width=60pc)

2. Confirm termination.

![Create VPC](/images/6-Clear-update/Clear-2.png?featherlight=false&width=60pc)

### Remove NAT Gateway and Elastic IP Address

- Remove NAT Gateway and Elastic IP Address. AWS charges for wasted EIPs, so you need to double-check to avoid unintended charges.
- Visit the Amazon VPC console page at [VPC](https://console.aws.amazon.com/vpc/).
- On the left navigation bar, click "NAT Gateway."
- Select NAT Gateway.
- Click **Action**.
- Click **Delete NAT Gateway**.

![Create VPC](/images/6-Clear-update/Clear-3.png?featherlight=false&width=60pc)

- Type "delete."
- Click **Delete** to confirm the deletion of NAT Gateway.

![Create VPC](/images/6-Clear-update/Clear-4.png?featherlight=false&width=60pc)

![Create VPC](/images/6-Clear-update/Clear-5.png?featherlight=false&width=60pc)

### Delete Elastic IP Address

- Continue to delete Elastic IP Address.
- Visit the Amazon VPC console page at [VPC](https://console.aws.amazon.com/vpc/).
- On the left navigation bar, click "Elastic IP."
- Select the Elastic IP Address we created.
- Click **Action**.
- Click **Release Elastic IP Address**.
- Click **Release**.

![Create VPC](/images/6-Clear-update/Clear-6.png?featherlight=false&width=60pc)

![Create VPC](/images/6-Clear-update/Clear-7.png?featherlight=false&width=60pc)

#### Delete the EC2 Instance connection endpoint
- Access to Endpoint transactions
- Select Action, select Delete VPC endpoints
- Enter delete
![Create VPC](/images/16/00020.png?featherlight=false&width=90pc)

### Delete in the following order:

- VPN Site to Site connection.

![Create VPC](/images/6-Clear-update/Clear-8.png?featherlight=false&width=60pc)

![Create VPC](/images/6-Clear-update/Clear-9.png?featherlight=false&width=60pc)

- Virtual Private Gateway.

![Create VPC](/images/6-Clear-update/Clear-10.png?featherlight=false&width=60pc)

![Create VPC](/images/6-Clear-update/Clear-11.png?featherlight=false&width=60pc)

![Create VPC](/images/6-Clear-update/Clear-12.png?featherlight=false&width=60pc)

![Create VPC](/images/6-Clear-update/Clear-13.png?featherlight=false&width=60pc)

- Customer Gateway.

![Create VPC](/images/6-Clear-update/Clear-14.png?featherlight=false&width=60pc)

![Create VPC](/images/6-Clear-update/Clear-15.png?featherlight=false&width=60pc)

- VPC ASG VPN.

![Create VPC](/images/6-Clear-update/Clear-16.png?featherlight=false&width=60pc)

![Create VPC](/images/6-Clear-update/Clear-17.png?featherlight=false&width=60pc)

- VPC ASG.

![Create VPC](/images/6-Clear-update/Clear-18.png?featherlight=false&width=60pc)

![Create VPC](/images/6-Clear-update/Clear-19.png?featherlight=false&width=60pc)
