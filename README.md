# AWS VPC Peering Project

## Project Overview
This project demonstrates AWS VPC Peering between two Virtual Private Clouds (VPCs), including routing configuration and private connectivity testing between EC2 instances.

## AWS Architecture

- **VPC A:** `10.10.0.0/16`
- **VPC B:** `10.20.0.0/16`
- **Bastion Host:** Public subnet in VPC A
- **App-A:** Private subnet in VPC A
- **App-B:** Private subnet in VPC B
- **VPC Peering:** Active

## AWS Services Used

- Amazon VPC
- VPC Peering
- Amazon EC2
- Route Tables
- Security Groups
- SSH

## Project Screenshots

### 1. VPC A and VPC B
![VPC A and B](01_VPC_A_and_B.jpeg)

### 2. Subnets
![Subnets](02a_Subnets.jpeg)

### 3. Public Route Table
![Public Route Table](02b_Public_Route_Table.jpeg)

### 4. VPC A Private Route Table
![VPC A Private Route Table](02c_Private_Route_Table_VPC_A.jpeg)

### 5. VPC B Private Route Table
![VPC B Private Route Table](02d_Private_Route_Table_VPC_B.jpeg)

### 6. VPC Peering Active
![VPC Peering Active](03_VPC_Peering_Active.jpeg)

### 7. Security Groups
![Security Groups](04a_Security_Groups.jpeg)

### 8. EC2 Key Pair
<!-- Confirm the exact filename in the repository before adding this image. -->

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

## Connectivity Results

- Bastion to App-A: SSH connection successful.
- App-A to App-B: SSH connection successful.
- App-B to App-A: Ping successful.

## Learning Outcomes

- Created and configured AWS VPCs and subnets.
- Configured route tables and VPC Peering.
- Practiced EC2 access using SSH.
- Tested private connectivity between instances.

## Security Note

Never upload private `.pem` keys, AWS access keys, passwords, or other credentials.

This project was completed as a hands-on AWS VPC Peering lab.
