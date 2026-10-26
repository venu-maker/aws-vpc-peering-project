# AWS VPC Peering - Configuration Documentation

## 1. Project Information

- **Project:** AWS VPC Peering
- **Cloud Provider:** Amazon Web Services (AWS)

## 2. VPC Configuration

| Component | CIDR Block | Purpose |
|---|---|---|
| VPC A | `10.10.0.0/16` | First virtual network |
| VPC B | `10.20.0.0/16` | Second virtual network |

## 3. Subnet Configuration

| Subnet | Configuration |
|---|---|
| VPC A public subnet | `10.10.1.0/24` |
| Other private subnets | Refer to the AWS console screenshots |

## 4. VPC Peering

A VPC Peering connection is configured between VPC A and VPC B to enable private communication using private IP addresses.

Required configuration:
- VPC Peering connection between both VPCs
- Appropriate routes in both VPC route tables
- Security group rules allowing required traffic

## 5. EC2 Instances

The project includes:
- Bastion host for administrative access
- App-A in VPC A
- App-B in VPC B

Instance connectivity depends on the subnet configuration, route tables, security groups, and SSH authentication.

## 6. Security Groups

Security groups control network access to the EC2 instances.

- SSH: TCP port 22, restricted to authorized sources
- ICMP: Allowed only when required for connectivity testing
- Application traffic: Allow only the required ports

## 7. Routing

The route tables must contain:
- Local routes for each VPC CIDR
- Routes to the peer VPC CIDR through the active VPC Peering connection
- Internet Gateway routes only where public connectivity is required

## 8. Connectivity Verification

The project includes screenshots documenting:
- VPCs and subnets
- Route tables
- VPC Peering connection
- Security groups
- EC2 instances
- SSH and ping connectivity tests

Refer to the screenshots in this repository for the recorded configuration and test results.

## 9. Security Notes

- Never commit AWS access keys or secret keys.
- Never upload private SSH keys (`.pem`).
- Restrict SSH access to trusted sources.
- Verify actual AWS configuration before making changes.

