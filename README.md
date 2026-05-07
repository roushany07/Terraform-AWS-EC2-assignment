# Terraform AWS EC2 Assignment

## Objective
Deploy an AWS EC2 instance using Terraform (Infrastructure as Code).

## Resources Created
- **EC2 Instance** — Amazon Linux 2, `t2.micro`, tagged `Terraform-Student-Instance`

## Prerequisites
- [Terraform](https://developer.hashicorp.com/terraform/downloads) >= 1.3.0
- AWS CLI configured with valid credentials (`aws configure`)
- An AWS account with EC2 permissions

## Project Structure
```
terraform-aws-ec2/
├── main.tf        # Provider and EC2 resource
├── variables.tf   # Input variables
├── outputs.tf     # Output values
└── README.md      # This file
```

## Steps to Run

### 1. Clone the Repository
```bash
git clone <your-repo-url>
cd terraform-aws-ec2
```

### 2. Initialize Terraform
Downloads required providers and sets up the backend.
```bash
terraform init
```

### 3. Preview the Plan
Shows what resources Terraform will create — no changes are made yet.
```bash
terraform plan
```

### 4. Apply the Configuration
Creates the EC2 instance on AWS. Type `yes` when prompted.
```bash
terraform apply
```

### 5. View Outputs
After apply, Terraform prints:
- `instance_public_ip` — Public IP of the instance
- `instance_id` — EC2 instance ID
- `instance_state` — Current state (e.g., `running`)

### 6. Destroy Resources (Cleanup)
To avoid AWS charges, destroy resources when done:
```bash
terraform destroy
```

## Configuration Details

| Parameter      | Value                        |
|----------------|------------------------------|
| Region         | `ap-south-1` (Mumbai)        |
| AMI            | `ami-0f58b397bc5c1f2e8` (Amazon Linux 2) |
| Instance Type  | `t2.micro`                   |
| Name Tag       | `Terraform-Student-Instance` |

## Notes
- Make sure your AWS credentials are configured before running any Terraform commands.
- The AMI ID is specific to the `ap-south-1` region. If you change regions, update `ami_id` in `variables.tf`.
