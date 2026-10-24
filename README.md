# aws-vpc-peering-project
AWS VPC Peering project with two VPCs, private EC2 instances, bastion host, routing and connectivity testing.
# AWS VPC Peering Project

## Project Overview
This project demonstrates secure communication between two Amazon Virtual Private Clouds (VPCs) using VPC Peering, route tables, security groups, and EC2 instances.

## Architecture
- **VPC A:** `10.10.0.0/16`
- **VPC B:** `10.20.0.0/16`
- **Bastion Host:** Public subnet in VPC A
- **App-A:** Private subnet in VPC A
- **App-B:** Private subnet in VPC B
- **VPC Peering:** Connects VPC A and VPC B

## AWS Services Used
- Amazon VPC
- VPC Peering
- Amazon EC2
- Subnets and Route Tables
- Internet Gateway
- Security Groups
- SSH and ICMP connectivity testing

## Connectivity Testing
The following connectivity tests were completed successfully:

1. Bastion Host → App-A using SSH
2. App-A → App-B using SSH
3. App-B → App-A using ICMP ping

The ping test returned 4 packets received with 0% packet loss.

## Learning Outcomes
- Created and configured two VPCs with non-overlapping CIDR ranges.
- Configured public and private subnets.
- Set up VPC Peering and routes.
- Configured security group rules.
- Tested private connectivity between EC2 instances.

## Screenshots
Project screenshots will be added to this repository as documentation.

## Security Note
Private keys, passwords, and AWS access credentials are not included in this repository.

## Author
AWS Cloud Learning Project
