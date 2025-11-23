# Track 1 – Cloud Security & IAM

## Goals

- Understand core cloud security concepts on AWS.
- Apply least-privilege IAM design (users, roles, policies).
- Configure secure storage (S3), logging (CloudTrail) and threat detection (GuardDuty).
- Use Terraform to build a repeatable, secure infrastructure baseline.
- Document security decisions in a clear, professional way.

---

## Related Stages

- **Stage 1 – AWS & Cloud Security (Days 1–12)**
- **Stage 5 – Networking, Cost Optimization, HA/DR (Days 43–55)** – some networking & HA aspects also relate to security.

---

## Related Projects

- `projects/cloud-security-lab/` – main project for this track.
- Later:
  - `projects/ha-dr-infra/` – will extend the security baseline with HA/DR patterns.

---

## Topics Covered

- AWS Identity and Access Management (IAM)
  - Users, groups, roles, managed policies.
  - Policy documents and least privilege.
- Data Protection
  - S3 security, encryption at rest (SSE-S3, SSE-KMS).
  - Key management with KMS.
- Logging & Monitoring
  - CloudTrail for audit logs.
  - GuardDuty for threat detection.
- Secrets Management
  - AWS Secrets Manager (or SSM Parameter Store).
- Infrastructure as Code
  - Terraform for building security baselines and enforcing standards.

---

## Learning Resources (Examples)

You can replace these with the exact courses and links you use:

- AWS documentation – IAM, CloudTrail, GuardDuty, KMS, S3 security.
- AWS SkillBuilder – Security Fundamentals.
- Official Terraform docs – AWS provider, IAM, S3, CloudTrail, GuardDuty.
- Blog posts / tutorials about “AWS secure baseline” or “Terraform AWS security”.

---

## Progress Notes

Personal notes for this track live in:

- `../notes/stage-1-notes.md`

I use them to summarize what I learned, questions I still have, and ideas for improving the lab.
