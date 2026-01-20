# Flagship Scope: Secure EKS Workload Platform

## North Star Outcome
A demo workload running on Kubernetes (local → EKS) with security guardrails, end-to-end observability (metrics/logs/traces), a secure CI/CD pipeline, artifact management, automation, and basic SRE metrics.

## Components (deliverables)
1) Security Foundation
- IAM least privilege baseline, policy evaluation notes, and review workflow.
- Architecture decisions documented using AWS Well-Architected Security Pillar and WA Tool.

2) Observability (ADOT / OpenTelemetry)
- Deploy ADOT/OTel Collector (DaemonSet + gateway pattern).
- Export metrics/traces to AWS-native targets (CloudWatch/X-Ray) and/or Prometheus.

3) Logging (Loki)
- Loki deployed via Helm values.
- LogQL queries + alert rules.
- Retention configured and documented.

4) CI/CD (Jenkins + Groovy)
- Declarative Jenkinsfile with stages: build → test → scan → SBOM → sign → deploy (as applicable).
- Shared library skeleton for reusable steps (later).

5) Artifact Management (Artifactory)
- Repo strategy: local + remote + virtual (federated optional).
- Permissions + retention/cleanup policy.
- Promotion flow documented.

6) Automation (Ansible)
- ansible-ops-kit: hardening baseline + repeatable playbooks.
- lint/tests (as applicable).

7) SRE Metrics (DORA)
- Track key delivery metrics (basic dashboard or documented approach).
- Optional: integrate Four Keys later.

## Repo layout (suggested)
projects/flagship/
  infra/
  k8s/
  obs/
  logging/
  cicd/
  artifacts/
  automation/
docs/notes/
docs/architecture/
