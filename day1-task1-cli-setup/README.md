# Day 1 - Task 1: AWS Console & CLI Setup

## Objective

Install and configure the AWS CLI, create a scoped IAM user, generate
programmatic access keys, and verify authentication.

## Steps

1. Created IAM user `devops-intern` with `AmazonVPCFullAccess` policy
   (scoped instead of AdministratorAccess - least privilege).
2. Generated programmatic access keys (CLI use case).
3. Installed AWS CLI v2 and verified with `aws --version`.
4. Configured CLI via `aws configure`.
5. Verified authentication with `aws sts get-caller-identity`.

## Screenshots

See `/screenshots` folder.

## Key Takeaway

Used a scoped IAM policy (AmazonVPCFullAccess) rather than
AdministratorAccess, reducing blast radius while covering both
this task's CLI verification and the upcoming VPC task.
