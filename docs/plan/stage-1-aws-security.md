
# Stage 1 – AWS & Cloud Security (Days 1–12)

**Goal:**  
Build a solid foundation in AWS cloud security, IAM, secrets management and secure infrastructure as code (Terraform).  
By the end of this stage you will have:

- A secure AWS baseline (IAM, S3, CloudTrail, GuardDuty, KMS, EC2 security groups).
- A Terraform project that provisions this baseline.
- Documentation that explains your security decisions.

---

## Outcomes / Deliverables

By the end of Stage 1 you should have in GitHub:

- Repository folder (example): `projects/cloud-security-lab/`
- Terraform code that creates:
  - VPC (optional, even a minimal one)
  - Private/public subnets (optional but recommended)
  - Secure S3 bucket(s)
  - IAM roles, policies, users (if needed)
  - CloudTrail logging
  - GuardDuty enabled in the region
  - KMS keys (if relevant)
- A short architecture & security overview in Markdown:
  - File: `docs/cloud-security-lab-overview.md`
- At least one diagram (can be drawn in any tool and exported as PNG):
  - File: `docs/cloud-security-lab-diagram.png`

---

## Day-by-Day Plan

### Day 1 – AWS Account & IAM Basics

- Ensure you have an AWS account ready (Free Tier if possible).
- Enable MFA on the root account.
- Create an **admin IAM user or role** for daily work.
- Read/Watch:
  - AWS IAM basics
  - AWS Shared Responsibility Model

**Definition of Done:**

- Root account has MFA.
- You do not work directly with the root user.
- A short note in `docs/stage-1-notes.md` describing your IAM setup.

---

### Day 2 – AWS Security Fundamentals (High-Level)

- Go through an introductory security course/module:
  - Example: AWS SkillBuilder – Security Fundamentals (or similar).
- Focus on:
  - IAM (users, roles, policies)
  - Encryption (at rest, in transit)
  - Logging and monitoring basics (CloudTrail, CloudWatch)

**Definition of Done:**

- Notes from the course in `docs/stage-1-notes.md` (bullets).
- 3–5 key takeaways about IAM and encryption.

---

### Day 3 – IAM Users, Roles & Policies

- Create:
  - At least one **IAM role** for EC2 or general use.
  - A custom **managed policy** with limited permissions (least privilege).
- Practice:
  - Attach/detach policies.
  - Use policy simulator.
- Read briefly about:
  - AWS best practices for IAM.

**Definition of Done:**

- One role and one custom managed policy created.
- Short explanation of the policy in `docs/stage-1-notes.md`.

---

### Day 4 – S3 Security

- Create a test S3 bucket for security practice.
- Configure:
  - Block all public access (unless strictly needed).
  - Bucket policy that follows least privilege.
  - Default SSE encryption (SSE-S3 or SSE-KMS).
- Optional:  
  - Versioning and lifecycle rules.

**Definition of Done:**

- Secure S3 bucket exists.
- Screenshot or CLI output saved (optional).
- Notes about what you configured and why.

---

### Day 5 – CloudTrail & GuardDuty

- Enable **CloudTrail** in the account (if not already enabled).
- Review basic events/logs.
- Enable **GuardDuty** in your region.
- Explore GuardDuty findings (even if only “sample” findings).

**Definition of Done:**

- CloudTrail enabled and logging.
- GuardDuty enabled.
- 2–3 bullet points about how each service helps security.

---

### Day 6 – KMS & Secrets Manager

- Learn KMS basics:
  - Difference between AWS-managed keys and customer-managed keys (CMK).
- Create:
  - One test CMK.
- Use AWS Secrets Manager to store:
  - A dummy password or API key.
- Optionally integrate reading this secret from a small script/app.

**Definition of Done:**

- One CMK created.
- One secret stored in Secrets Manager.
- Short note explaining when to use Secrets Manager vs SSM Parameter Store.

---

### Day 7 – EC2 Hardening

- Launch a small EC2 instance (Free Tier if possible).
- Configure:
  - Security Group – minimal inbound rules (e.g., SSH from your IP only).
  - Key pair for SSH access.
  - System updates (e.g., `apt update && apt upgrade`).
- Think about:
  - Where logs go (CloudWatch Logs or local).

**Definition of Done:**

- EC2 instance accessible only in a controlled way.
- Notes about your security group rules and ssh key management.

---

### Day 8 – Terraform: Secure Baseline (Part 1)

- Initialize a new Terraform project:
  - Directory: `projects/cloud-security-lab/terraform/`
- Create Terraform code for:
  - A secure S3 bucket (with encryption and block public access).
  - CloudTrail logging to that bucket (if possible).

**Definition of Done:**

- `main.tf` (or modular structure) with:
  - Provider configuration
  - S3 + CloudTrail resources
- `terraform init` and `terraform apply` work successfully.

---

### Day 9 – Terraform: IAM & GuardDuty (Part 2)

- Extend the Terraform project to:
  - Create IAM role(s) and policy(ies).
  - Enable GuardDuty (if possible via Terraform).
  - Optionally create KMS key via Terraform.

**Definition of Done:**

- Terraform project now includes IAM and GuardDuty resources.
- All changes are applied successfully.
- Commit with clear message (example:  
  `feat: add IAM roles and GuardDuty to security baseline`).

---

### Day 10 – Terraform Refinement

- Refactor Terraform:
  - Use variables, outputs and locals where needed.
  - Add tags for all supported resources (e.g., `Environment`, `Owner`).
- Split the code into modules if it’s getting big:
  - Example: `modules/s3`, `modules/iam`, `modules/logging`.

**Definition of Done:**

- Code is cleaner and easier to extend.
- `terraform fmt` and `terraform validate` pass.
- Commit with message (example:  
  `refactor: modularize terraform security baseline`).

---

### Day 11 – Documentation & Diagram

- Write a short architecture & security overview:
  - File: `docs/cloud-security-lab-overview.md`
  - Explain:
    - What resources exist.
    - How they work together.
    - Which security controls you implemented.
- Create a simple diagram of the architecture:
  - Can be done in draw.io, Excalidraw, or any tool.
  - Export as `docs/cloud-security-lab-diagram.png`.

**Definition of Done:**

- Overview markdown file created.
- Diagram exists and is stored in the repo.

---

### Day 12 – Review & Publish

- Review all Terraform and docs from Stage 1.
- Clean up:
  - Remove unused resources.
  - Make sure secrets are **not** committed to Git.
- Push to GitHub:
  - Terraform code.
  - Documentation.
  - Diagram.

**Definition of Done:**

- Stage 1 is fully represented in GitHub.
- You can show this repo as a “Cloud Security / Terraform baseline” project.
