# Day 1 - Task 2: Virtual Private Cloud Config

## Objective

Build a custom VPC with public/private subnets, an Internet Gateway,
and route tables.

## Setup

- VPC: devops-intern-vpc (10.0.0.0/16)
- Public subnet: public-subnet-1 (10.0.1.0/24)
- Private subnet: private-subnet-1 (10.0.2.0/24)
- Internet Gateway: devops-intern-igw (attached to VPC)
- public-rtb: 0.0.0.0/0 -> IGW, associated with public-subnet-1
- private-rtb: local only, associated with private-subnet-1

## Verification

Confirmed via console and AWS CLI:
aws ec2 describe-vpcs --filters "Name=tag:Name,Values=devops-intern-vpc"
aws ec2 describe-subnets --filters "Name=vpc-id,Values=<vpc-id>"
aws ec2 describe-route-tables --filters "Name=vpc-id,Values=<vpc-id>"

## Screenshots

See `/screenshots` folder.

## Key Takeaway

Public/private subnet separation with distinct route tables is the
core pattern behind production AWS network architecture.
