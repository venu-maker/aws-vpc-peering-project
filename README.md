# AWS VPC Peering Project

## Project Overview

This project demonstrates how to establish private network communication between two Amazon Virtual Private Clouds (VPCs) using AWS VPC Peering.

The project includes VPC configuration, subnet planning, route tables, security groups, EC2 instances, SSH connectivity, and network connectivity testing.

## Objectives

- Create and configure two separate VPCs.
- Configure public and private subnets as required.
- Establish a VPC Peering connection between the VPCs.
- Configure route tables for communication between the VPCs.
- Configure security groups for controlled network access.
- Deploy a bastion host and application EC2 instances.
- Test connectivity using SSH and ping where permitted.

## AWS Services Used

- Amazon VPC
- VPC Peering
- Amazon EC2
- Subnets
- Route Tables
- Security Groups
- SSH
- Linux networking utilities

## Network Architecture

The project uses two separate VPCs connected through a VPC Peering connection.

**Logical architecture:**

```text
                 Internet
                    |
             Bastion Host
                    |
                 VPC A
                    |
                 App-A
                    |
              VPC Peering
                    |
                 VPC B
                    |
                 App-B
```

The diagram is a simplified logical representation. Actual routing and connectivity depend on the configured subnets, route tables, security groups, and network access rules.

## Project Configuration

The intended network design uses separate IPv4 CIDR ranges for the two VPCs.

| Component | Purpose |
|---|---|
| VPC A | First isolated virtual network |
| VPC B | Second isolated virtual network |
| Public subnet | Hosts resources that require public connectivity |
| Private subnets | Host application resources without direct public exposure |
| Bastion host | Entry point for authorized administrative SSH access |
| App-A | Application instance in VPC A |
| App-B | Application instance in VPC B |
| VPC Peering | Private routing between the two VPCs |
| Route tables | Define traffic destinations |
| Security groups | Control permitted inbound and outbound traffic |

Use the actual CIDR blocks and subnet details shown in your AWS console when documenting the final configuration.

## Project Screenshots

### 1. VPC A and VPC B

![VPC A and VPC B](01_VPC_A_and_B.jpeg)

### 2. Subnets

![Subnets](02a_Subnets.jpeg)

### 3. Public Route Table

![Public Route Table](02b_Public_Route_Table.jpeg)

### 4. Private Route Table - VPC A

![Private Route Table VPC A](02c_Private_Route_Table_VPC_A.jpeg)

### 5. Private Route Table - VPC B

![Private Route Table VPC B](02d_Private_Route_Table_VPC_B.jpeg)

### 6. Active VPC Peering Connection

![VPC Peering Active](03_VPC_Peering_Active.jpeg)

### 7. Security Groups

![Security Groups](04a_Security_Groups.jpeg)

### 8. EC2 Key Pair

![EC2 Key Pair](04b_EC2_Key_Pair%20%281%29.jpeg)

### 9. Bastion and App-A Instances

![Bastion and App-A Instances](05_Bastion_and_App_A_Instances.jpeg)

### 10. App-B Instance

![App-B Instance](06_App_B_Instance.jpeg)

### 11. Bastion SSH Key Generation

![Bastion SSH Key Generation](07_Bastion_SSH_Key_Generation.jpeg)

### 12. Bastion to App-A SSH

![Bastion to App-A SSH](08_Bastion_to_App_A_SSH.jpeg)

### 13. App-A to App-B SSH

![App-A to App-B SSH](09_App_A_to_App_B_SSH.jpeg)

### 14. App-B to App-A Ping

![App-B to App-A Ping](10_App_B_to_App_A_Ping.jpeg)

## Implementation Steps

1. Created two VPCs with separate IPv4 CIDR ranges.
2. Created the required subnets.
3. Configured route tables and subnet associations.
4. Created and activated the VPC Peering connection.
5. Added the required routes for communication between the VPCs.
6. Configured security groups to allow only the required traffic.
7. Launched the bastion and application EC2 instances.
8. Configured SSH access for administrative connectivity.
9. Performed SSH and ping connectivity tests where supported by the network configuration.

## Connectivity Testing

The following tests are relevant to this project:

| Test | Expected result |
|---|---|
| VPC Peering status | Active |
| Route table verification | Routes point to the correct peering connection |
| Bastion to App-A SSH | Successful with valid credentials and permitted network access |
| App-A to App-B SSH | Successful when SSH routing, security rules, and authentication are configured correctly |
| App-B to App-A ping | Successful when ICMP is permitted and the network path is valid |

**Important:** A test should be marked successful only when the actual command output confirms it. An active peering connection alone does not prove end-to-end connectivity.

## Troubleshooting

### SSH connection issues

- Verify that the destination EC2 instance is running.
- Check the destination's private IP address.
- Verify route tables in both VPCs.
- Confirm that security groups permit SSH traffic on TCP port 22 from the appropriate source.
- Verify that the correct private key and username are used.
- Confirm that the source host has access to the required private key.
- If SSH from a Windows laptop fails, check local network restrictions and outbound port 22 connectivity separately.

### Ping connectivity issues

- Confirm that routes exist in both directions.
- Check whether security groups permit ICMP traffic.
- Verify that the destination instance and operating system allow the traffic.

## Security Best Practices

- Do not upload private SSH keys, AWS access keys, passwords, or secret credentials to GitHub.
- Restrict SSH access to trusted sources.
- Avoid opening ports to `0.0.0.0/0` unless genuinely required.
- Use private IP addresses for communication between private application instances.
- Review and remove unused AWS resources to avoid unnecessary charges.

## What I Learned

Through this project, I practised AWS networking concepts, VPC configuration, subnetting, route tables, VPC Peering, EC2 deployment, security groups, SSH troubleshooting, and private network connectivity.

## Conclusion

This project provides practical experience with AWS VPC Peering and the networking components required for communication between separate virtual networks. It also demonstrates the importance of correct routing, security rules, authentication, and systematic troubleshooting.

## Author

**Venu Wadhonkar**

GitHub: [venu-maker](https://github.com/venu-maker)

Project Repository: [aws-vpc-peering-project](https://github.com/venu-maker/aws-vpc-peering-project)
