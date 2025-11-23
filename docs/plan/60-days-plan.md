## Study Plan – 60 Days
- Stage 1 (Days 1-12): AWS & Cloud Security
- Stage 2 (Days 13-22): Observability & Monitoring
- Stage 3 (Days 23-32): IaC & Multi-Cloud
- Stage 4 (Days 33-42): CI/CD & Security Automation
- Stage 5 (Days 43-55): Networking, Cost, HA/DR
- Stage 6 (Days 56-60+): Final Flagship Project

# DevOps / SRE – 60 Days Advanced Roadmap

This document describes the 60-day learning and practice plan, broken down into 6 stages.  
Each stage focuses on a key skill area that is highly valued for DevOps / SRE / Cloud roles.

## High-Level Stages

- **Stage 1 (Days 1–12): AWS & Cloud Security**
  - IAM, secure configuration, secrets, KMS, GuardDuty, CloudTrail, EC2 hardening, Terraform for secure infra.

- **Stage 2 (Days 13–22): Observability & Monitoring**
  - Prometheus, Grafana, logs (Loki / ELK), alerting, incident handling, RCA and postmortems.

- **Stage 3 (Days 23–32): IaC & Multi-Cloud**
  - Terraform modules, Azure/GCP basics, Helm on Kubernetes, infra as code across more than one cloud.

- **Stage 4 (Days 33–42): CI/CD & Security Automation**
  - Jenkins / GitHub Actions pipelines, tests, security scans, quality gates, deployment automation.

- **Stage 5 (Days 43–55): Networking, Cost Optimization, HA/DR**
  - VPC & networking, cost visibility, budgets, high availability, backups and disaster recovery.

- **Stage 6 (Days 56–60+): Production-Ready DevOps SaaS – Flagship Project**
  - Build a small “SaaS-style” stack in the cloud with IaC, CI/CD, monitoring, security and documentation.

---

## Daily Plan Overview

This is a high-level mapping of days to focus.  
Detailed tasks for each day live in the per-stage files (e.g. `stage-1-aws-security.md`).

### Stage 1 – AWS & Cloud Security (Days 1–12)

**Goal:** Become comfortable with core cloud security concepts on AWS and start automating them with Terraform.

| Day | Focus                                                              |
| --- | ------------------------------------------------------------------ |
| 1   | Open/verify AWS account, enable MFA, basic IAM concepts           |
| 2   | AWS Security Fundamentals (online course – IAM, shared responsibility) |
| 3   | IAM Users, Roles, Policies – least privilege, groups, MFA         |
| 4   | S3 security – bucket policies, block public access, encryption    |
| 5   | CloudTrail, GuardDuty, basic security alerts & findings           |
| 6   | KMS basics, CMK vs AWS-managed keys, Secrets Manager for secrets  |
| 7   | EC2 hardening – security groups, SSH keys, logging and audit      |
| 8   | Terraform – create secure baseline (VPC, Subnets, SG, S3, CloudTrail) |
| 9   | Extend Terraform – IAM roles/policies, KMS integration            |
| 10  | Add tags, outputs, variables; clean module structure              |
| 11  | Document architecture + security decisions (Markdown + diagram)   |
| 12  | Final review of Stage 1; push code & docs to GitHub               |

See details in: `stage-1-aws-security.md`.

---

### Stage 2 – Observability & Monitoring (Days 13–22)

**Goal:** Build a small but realistic observability stack with metrics, logs, alerts and an incident story.

| Day | Focus                                                              |
| --- | ------------------------------------------------------------------ |
| 13  | Install Prometheus + Grafana (Docker / VM / Kubernetes)           |
| 14  | Scrape metrics from EC2 / app; build first Grafana dashboard      |
| 15  | Create alerts (CPU, latency, errors) with email/Slack integration |
| 16  | Set up logs stack (Loki **or** ELK)                               |
| 17  | Connect app / system logs to the logs stack                       |
| 18  | Design and simulate an incident scenario                          |
| 19  | Investigate incident using metrics + logs; perform RCA            |
| 20  | Write a postmortem document (Markdown)                             |
| 21  | Build SLO/SLI-style dashboard (availability, error rate, latency) |
| 22  | Finalize docs, dashboards and screenshots; push to GitHub         |

See details in: `stage-2-observability.md`.

---

### Stage 3 – IaC & Multi-Cloud (Days 23–32)

**Goal:** Become comfortable with Terraform across clouds and Helm on Kubernetes.

| Day | Focus                                                              |
| --- | ------------------------------------------------------------------ |
| 23  | Review Terraform basics; create a reusable module on AWS          |
| 24  | Apply similar Terraform concepts on GCP or Azure                  |
| 25  | Install Helm; deploy a simple app to Kubernetes (kind/minikube/EKS/AKS/GKE) |
| 26  | Add configuration via Helm values; understand releases and rollback |
| 27  | Create Terraform that provisions the Kubernetes cluster (if possible in chosen cloud) |
| 28  | Wire Terraform + Helm together (infra + app)                      |
| 29  | Add basic monitoring to this stack (reuse Stage 2 pieces)         |
| 30  | Clean up modules, variables and documentation                     |
| 31  | Add diagrams and explain the IaC design                           |
| 32  | Finalize multi-cloud/IaC demo; push to GitHub                     |

*(Stage 3 detailed file can be added later: `stage-3-iac-multi-cloud.md`.)*

---

### Stage 4 – CI/CD & Security Automation (Days 33–42)

**Goal:** Show a realistic pipeline with tests, security checks and deployments.

| Day | Focus                                                              |
| --- | ------------------------------------------------------------------ |
| 33  | Choose tool (GitHub Actions / Jenkins); set up basic pipeline     |
| 34  | Add build + unit tests stages                                     |
| 35  | Integrate security scan (Snyk / Trivy / Checkov)                  |
| 36  | Add static analysis (PHPCS / PHPStan / ESLint / etc.)             |
| 37  | Configure quality gates / required checks                         |
| 38  | Add deployment step (to test environment or Kubernetes)           |
| 39  | Add manual approval / promotion to “production”                   |
| 40  | Add notifications (Slack / email) on failures and successes       |
| 41  | Document the pipeline + diagrams (what happens, when and why)     |
| 42  | Final review, tags and GitHub documentation                       |

---

### Stage 5 – Networking, Cost Optimization, HA/DR (Days 43–55)

**Goal:** Understand how production-ready infra is built and paid for.

| Day | Focus                                                              |
| --- | ------------------------------------------------------------------ |
| 43  | Build a VPC (subnets, routing, IGW, NAT)                           |
| 44  | Add Security Groups, NACLs and basic network flows                 |
| 45  | Explore AWS Cost Explorer and Budgets; set alerts                  |
| 46  | Identify cost drivers; think about rightsizing/spot                |
| 47  | Design Multi-AZ web + DB architecture                              |
| 48  | Implement Multi-AZ DB (RDS or similar)                             |
| 49  | Implement backup & restore strategy                                |
| 50  | Simulate a DR scenario and document runbook                        |
| 51  | Add health checks and failover concepts                            |
| 52  | Refine architecture diagram and explanation                        |
| 53  | Add tagging + cost allocation strategies                           |
| 54  | Finalize HA/DR demo; clean Terraform and docs                      |
| 55  | Push everything to GitHub, including diagrams and runbooks         |

---

### Stage 6 – Flagship Project – Production-Ready DevOps SaaS (Days 56–60+)

**Goal:** Combine everything into one coherent “mini production” system.

| Day | Focus                                                              |
| --- | ------------------------------------------------------------------ |
| 56  | Define the SaaS-style app idea (simple but realistic)              |
| 57  | Design architecture (IaC, CI/CD, monitoring, security)             |
| 58  | Implement core infrastructure + CI/CD                              |
| 59  | Add observability, security hardening and backups                  |
| 60  | Final polishing, documentation, README, LinkedIn post              |

> Note: In practice, Stage 6 may take 2–3 additional weeks.  
> This document focuses on structure; the actual pace can be adjusted.
