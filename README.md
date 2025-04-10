# Prisma Cloud DevSecOps Workshop

This repository is designed to help DevOps and security teams understand how to integrate **Prisma Cloud by Palo Alto Networks** into a modern CI/CD pipeline using **Infrastructure as Code (IaC)** practices.

It provides hands-on examples of securing AWS infrastructure with Terraform and scanning for vulnerabilities, misconfigurations, and exposed secrets.

---

##  Workshop Objectives

- Understand DevSecOps principles using Prisma Cloud
- Learn how to scan Terraform code for security issues
- Detect hardcoded secrets and insecure configurations
- Automate security checks in the development pipeline
- Gain visibility into cloud risks using Prisma Cloud

---

##  Repository Structure

```bash
.
├── code/
│   ├── deployment_ec2.tf         # Terraform code to deploy EC2
│   ├── deployment_s3.tf          # Terraform code to deploy S3 with logging & encryption
│   ├── s3.tf                     # Simple S3 bucket (no logging)
│   ├── simple_s3.tf              # Another S3 example without logging
│   └── ...
├── scan-reports/
│   └── ...                       # Sample reports from security scans
├── .github/
│   └── workflows/                # GitHub Actions for CI/CD security scanning
├── .gitignore
└── README.md                     # This file
```


## Prerequisites
To run this workshop locally, you need:

Terraform

Checkov (for scanning IaC)

Prisma Cloud Account

AWS CLI configured with appropriate IAM permissions

Git and GitHub account

## Security Scanning Tools Used
Checkov – Static analysis for Terraform security misconfigurations

Prisma Cloud – Cloud-native security platform for CI/CD pipelines

GitHub Actions – Automates code scanning and validation on every push

## Getting Started
Clone the repository:

```bash

git clone https://github.com/offranking/prisma-cloud-devsecops.git
cd prisma-cloud-devsecops
```
Run Checkov locally:

```bash
checkov -d .
```
(Optional) Deploy infrastructure (use with caution):

```bash
terraform init
terraform plan
terraform apply
```
View scan reports or configure GitHub Actions to run them automatically.

## Sample Checkov Failures
CKV_AWS_18: Ensure the S3 bucket has access logging enabled

CKV_SECRET_2: Avoid hardcoded AWS credentials in source files

Reports are automatically generated on pull requests and can be viewed under the Actions tab in GitHub.

## Security Best Practices
Never commit credentials or access tokens

Use aws_s3_bucket logging blocks

Enable server-side encryption with KMS

Follow the Prisma Cloud IaC Security Guide for more

## Resources
Prisma Cloud Docs

Checkov Docs

Terraform AWS Provider

## Author
Offranking
GitHub Profile




