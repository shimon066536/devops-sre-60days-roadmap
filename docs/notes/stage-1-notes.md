
# Stage 1 – AWS & Cloud Security: Notes

## Day 1 – AWS account & IAM setup

### What I did
- Enabled MFA for the root user.
- Verified the root user has **no active access keys**.
- Created IAM admin user (`shimon-admin`) inside the `Admins` group.
- Enabled MFA for the `shimon-admin` user.
- Configured AWS CLI with the profile `shimon-admin`.
- Tested CLI access with `aws sts get-caller-identity --profile shimon-admin`.

### Key security decisions
- Root user will never be used for day-to-day work.
- IAM admin user is protected with MFA and is the only one used for console/CLI access.
- No long-term credentials will be created unless required, and will be rotated periodically.

### Notes / Follow-ups
- Consider later creating “least-privilege” roles for Terraform and CI/CD.
- Consider enforcing password policy and enabling AWS Organizations SCPs in the future.
