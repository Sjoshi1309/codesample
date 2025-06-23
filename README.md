# Terraform AWS EKS Cluster Setup

This project provisions a **Kubernetes cluster on AWS using EKS**, including a custom VPC, EC2-based node groups with auto-scaling, and secure network access via security groups.

## Architecture Design

- Provision a custom **VPC** with public and private subnets.
- Create an **EKS Cluster** within the VPC.
- Attach **EC2-based node groups** with:
  - Minimum: 2 nodes
  - Maximum: 6 nodes
  - Auto-scaling based on traffic
- Associate **security groups** to control access.

---

## Prerequisites

- [Terraform](https://www.terraform.io/downloads.html) (v1.0+)
- [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)
- AWS account credentials configured (`aws configure`)

---

## Folder Structure

```bash
.
├── main.tf               # Main EKS module definition
├── vpc.tf                # VPC setup using terraform-aws-modules/vpc
├── variables.tf          # Input variable definitions
├── outputs.tf            # Output values
├── providers.tf          # AWS provider config
├── terraform.tfvars      # Variable values (ignored in .gitignore)
├── README.md             # Project documentation
