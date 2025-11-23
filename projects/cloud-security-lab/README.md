# Cloud Security Lab - AWS + Terraform

This project is part of **Stage 1 – AWS & Cloud Security** in my 60-day DevOps / SRE roadmap.

The goal of this lab is to build a small but realistic **secure AWS baseline** using Terraform:

- IAM best practices (roles, managed policies, least privilege).
- Secure S3 buckets with encryption and blocked public access.
- Centralized logging using CloudTrail.
- Threat detection with GuardDuty.
- Optional: KMS customer-managed keys and Secrets Manager.

---

## Architecture Overview

High-level components:

- **VPC (optional)** – basic networking for the environment.
- **S3 (logging bucket)** – stores CloudTrail logs.
- **CloudTrail** – records API calls and writes to the S3 logging bucket.
- **GuardDuty** – analyzes AWS events and generates security findings.
- **IAM Roles & Policies** – for admin / service access with least privilege.
- **KMS (optional)** – key management for encryption.
- **Secrets Manager (optional)** – secure storage for application secrets.

See:

- `../../docs/architecture/cloud-security-lab-overview.md`
- `../../docs/architecture/cloud-security-lab-diagram.png`

---

## Repository Layout

```text
projects/cloud-security-lab/
├── README.md
└── terraform/
    ├── main.tf
    ├── variables.tf
    ├── outputs.tf
    └── modules/
        ├── s3-logging/
        ├── iam/
        ├── cloudtrail/
        └── guardduty/
