# AWS EC2 Instance with SSH Security Group (Terraform)

This project uses [Terraform](https://www.terraform.io/) to provision an AWS EC2 instance with a security group that allows SSH access from anywhere.

## Features
- **AWS EC2 Instance**: Launches a t2.micro instance using a public Amazon Linux 2 AMI.
- **Security Group**: Allows inbound SSH (port 22) from any IP address and all outbound traffic.
- **Outputs**: Displays the public IP address of the created EC2 instance.

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
2. **Initialize Terraform**:
   ```sh
   terraform init
   ```
3. **Review the plan**:
   ```sh
   terraform plan
   ```
4. **Apply the configuration**:
   ```sh
   terraform apply
   ```
   Type `yes` when prompted to create the resources.

5. **Get the public IP**:
   After apply completes, Terraform will output the public IP address of the EC2 instance.

## File Structure
- `main.tf`: Main Terraform configuration file.
- `README.md`: This file.

## Notes
- The security group allows SSH access from anywhere (`0.0.0.0/0`). For production, restrict this to trusted IPs.
- The AMI ID (`ami-0c94855ba95c71c99`) is for Amazon Linux 2 in `us-east-1`. Change it if you use a different region or OS.

## Cleanup
To destroy all resources created by this project:
```sh
terraform destroy
```

---

**Author:** Your Name
