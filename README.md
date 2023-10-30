## Terraform AWS Infrastructure Deployment

This repository contains Terraform code for deploying AWS infrastructure resources. The provided code provisions the following AWS resources:

- AWS Key Pair
- Virtual Private Cloud (VPC)
- Subnet
- Internet Gateway
- Route Table
- Route Table Association
- Security Group
- EC2 Instance

### Prerequisites

Before you begin, ensure you have the following:

- [Terraform](https://www.terraform.io/downloads.html) installed on your local machine.
- AWS CLI configured with your AWS access and secret keys.

### Configuration

In order to deploy this infrastructure, you may need to customize the following parameters in the `main.tf` file:

- AWS region: Replace the `region` in the AWS provider block with your desired AWS region.

```hcl
provider "aws" {
  region = "us-east-1"  # Replace with your desired AWS region.
}
```

- Key Pair: You should replace the `key_name` and `public_key` with your preferred values in the `aws_key_pair` resource block.

- VPC CIDR Block: You can change the VPC CIDR block in the `variable` block in the `main.tf` file.

- EC2 AMI: Replace the `ami` in the `aws_instance` resource block with the desired Amazon Machine Image (AMI) ID.

- SSH Configuration: Modify the SSH connection settings in the `aws_instance` resource block to match your preferred configuration.

- Provisioning: Customize the provisioner sections to suit your application's needs.

### Usage

1. Clone this repository to your local machine.

2. Open your terminal and navigate to the repository folder.

3. Initialize Terraform by running:

```bash
terraform init
```

4. Plan the infrastructure deployment to verify the changes:

```bash
terraform plan
```

5. Deploy the infrastructure by running:

```bash
terraform apply
```

6. Confirm and apply the changes when prompted.

### Cleaning Up

If you want to tear down the infrastructure created by this Terraform configuration, run:

```bash
terraform destroy
```

### Notes

- Make sure to protect your AWS access keys and do not hardcode them in your code. Consider using environment variables or AWS profile for secure access.
- Review the security group and network settings to ensure they align with your application's requirements.

Please be cautious when deploying and destroying infrastructure, as it can result in real-world financial costs and potential data loss.
