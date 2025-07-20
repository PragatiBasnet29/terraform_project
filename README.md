# AWS VPC, EC2, and S3 Infrastructure with Terraform

This project uses [Terraform](https://www.terraform.io/) to provision a basic AWS infrastructure, including a VPC, public and private subnets, an EC2 instance, and an S3 bucket.

## Features
- **VPC**: Custom Virtual Private Cloud with DNS support and hostnames enabled.
- **Subnets**: One public and one private subnet.
- **Internet Gateway**: For public subnet internet access.
- **Route Table**: Public route table associated with the public subnet.
- **Security Group**: Allows SSH (port 22) from anywhere and all outbound traffic.
- **EC2 Instance**: Amazon Linux 2 instance in the public subnet with a public IP.
- **S3 Bucket**: Private S3 bucket with tags.
- **Outputs**: Public IP and ID of the EC2 instance, and the S3 bucket name.

## Prerequisites
- [Terraform](https://www.terraform.io/downloads.html) installed
- An AWS account
- AWS credentials configured (via environment variables, `~/.aws/credentials`, or similar)

## Usage
1. **Clone this repository** (or copy the files to your local machine):
   ```sh
   git clone <this-repo-url>
   cd my-terraform-projecte-with-aws
   ```
2. **Edit the S3 bucket name**:
   - In `main.tf`, update the value for `bucket` in the `aws_s3_bucket` resource to a globally unique name.
3. **Initialize Terraform**:
   ```sh
   terraform init
   ```
4. **Review the plan**:
   ```sh
   terraform plan
   ```
5. **Apply the configuration**:
   ```sh
   terraform apply
   ```
   Type `yes` when prompted to create the resources.
6. **Get the outputs**:
   - After apply completes, Terraform will output:
     - The public IP of the EC2 instance
     - The EC2 instance ID
     - The S3 bucket name

## File Structure
- `main.tf`: Main Terraform configuration file.
- `README.md`: This file.

## Notes
- The security group allows SSH access from anywhere (`0.0.0.0/0`). For production, restrict this to trusted IPs.
- The AMI ID (`ami-0c02fb55956c7d316`) is for Amazon Linux 2 in `us-east-1`. Change it if you use a different region or OS.
- The S3 bucket name must be globally unique. Edit it in `main.tf` before applying.

## Cleanup
To destroy all resources created by this project:
```sh
terraform destroy
```

---

**Author:** Pragati Basnet
