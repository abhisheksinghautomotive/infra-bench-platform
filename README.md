# Cloud-Based HIL/SIL Bench Orchestration

Scalable AWS infrastructure for provisioning and managing distributed HIL/SIL “virtual bench” environments.

---

## 🚀 Overview

This project delivers a secure, autoscaling cloud platform that hosts virtual test benches for ECU validation. All resources are defined using reusable Terraform modules and deployed through a controlled CI/CD pipeline.

---

## 📦 Key Features

* Private, multi-AZ AWS VPC with restricted networking
* Autoscaling bench hosts (EC2 or EKS) with warm pools
* Shared workspace via EFS and test artifacts via S3
* Bench state and metadata stored in DynamoDB
* Secure access through SSM Session Manager (no SSH)
* End-to-end Terraform pipelines (plan/apply + drift detection)
* Observability via CloudWatch dashboards and alarms
* Cost controls: tagging, lifecycle policies, budgets

---

## 🧱 Architecture Components

* **Networking**: VPC, private subnets, NAT, VPC endpoints
* **Compute**: ASG with Launch Templates (or EKS runners)
* **Storage**: EFS, S3 with lifecycle rules
* **State/Metadata**: DynamoDB (optional RDS)
* **Security**: IAM least privilege, KMS, SSM-only access
* **CI/CD**: GitHub Actions (OIDC), tfsec/checkov scans

---

## 📁 Repository Structure

```
infra-terraform/
├─ modules/
│  ├─ vpc/
│  ├─ sg/
│  ├─ efs/
│  ├─ asg/
│  ├─ dynamodb/
│  ├─ s3/
│  ├─ iam/
│  ├─ eks/ (optional)
│  └─ monitoring/
├─ envs/
│  ├─ dev/
│  ├─ stage/
│  └─ prod/
├─ .github/workflows/
├─ ADRs/
├─ docs/
└─ README.md
```

---

## 🔧 Environments

Each environment (dev, stage, prod) is isolated with:

* Separate Terraform state
* Independent variable configurations
* Identical module structure

---

## ✔️ Acceptance Criteria

* Scalable bench hosts with warm pools
* Private networking; SSM-only access
* Full Terraform CI (plan → apply)
* Bench can receive tasks from Orchestrator
* Observability + alerts active
* Cost tagging enforced across all modules

---

## 📚 Documentation

See:

* **ADRs/** for architectural decisions
* **docs/** for module usage and runbooks

---

## License

This project is licensed under the MIT License. See the LICENSE file for details.

---
