# Stage 1 – Day 2 (Build-First): AWS Security Fundamentals

## Evidence
- WA Tool Workload created: 60days-secure-platform (screenshot captured)
- IAM Access Analyzer: access-analyzer-60days (External access), findings: 0 (screenshot captured)
- Policy example added: yes (docs/snippets/iam/policy-example-least-privilege.json)

## 1) Shared Responsibility (1-minute summary)
- AWS: security OF the cloud
- Customer: security IN the cloud
- Practical example: <one example you observed today>

## 2) IAM Policy: minimal structure + example intent
- Key elements: Version, Statement, Effect, Action, Resource, Condition
- Evaluation: implicit deny by default; explicit deny wins
- Conditions are a primary tool for least privilege
- Explicit deny overrides allow (not used here, but rule is critical)
- Implicit deny blocks everything not explicitly allowed

## 3) Access Analyzer: what I checked today

**What I expected to see**
- Potential findings if any resource allowed external (public or cross-account) access.

**What I actually saw**
- Analyzer created successfully (type: External access).
- Findings: 0 – no externally accessible resources detected.

**Action taken (if any)**
- No action required at this stage.
- Analyzer left active for continuous monitoring.


## 4) Well-Architected (Security): why we created the workload

**Workload name**
- 60days-secure-platform

**What we will use it for later**
- Serve as a decision framework for security-related architectural choices.
- Map future implementations (IAM, logging, monitoring) to AWS Well-Architected Security Pillar questions.
