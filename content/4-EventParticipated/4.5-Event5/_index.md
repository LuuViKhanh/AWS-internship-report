---
title: "Event 5"
weight: 1
chapter: false
pre: " <b> 4.5. </b> "
---

## Event Report: AWS Cloud Mastery Series #3 - AWS Well-Architected Security Pillar

### Event Purpose
- The workshop was organized to help participants gain deep understanding of the Security Pillar in the AWS Well-Architected Framework and how to build secure cloud systems with controlled access, continuous monitoring, data protection, and effective incident response. Main objectives:
  - Learn more about the role of Security in modern cloud architecture.
  - Learn core principles such as Least Privilege, Zero Trust, and Defense in Depth.
  - Understand the Shared Responsibility Model and top threats in Vietnam's cloud environment.
  - Explore 5 important Pillars: IAM, Detection, Infrastructure Protection, Data Protection, and Incident Response.
  - Practice policy analysis, building guardrails, logging, monitoring, and simulating incident scenarios.

---

### Speaker List & Topics
- **Mendel Grabski (Long)** – ex Head of Security & DevOps, Cloud Security Solutions Architect  
- **Truong Quang Tinh** – AWS Community Builder, Platform Engineer at TymeX  
- **Thịnh Lâm** – FCJ Cloud Engineer  
- **Việt Nguyễn** – FCJ Cloud Engineer
- **Danh Hoàng Hiếu Nghị** – FCJ Cloud Engineer

---

### Highlighted Content

#### 1. Security Foundation & Challenges in Cloud Environment
The workshop opened with common issues faced by cloud environments in Vietnam:
- Improper IAM management, granting excessive permissions (over-permission).
- Long-term credential leaks, keys not being rotated.

Speakers emphasized 3 core principles:
- **Least Privilege** – grant only minimum necessary permissions.
- **Zero Trust** – no default trust, always verify.
- **Defense in Depth** – multi-layered protection from IAM → Network → Workload → Data.

#### 2. Identity & Access Management (Pillar 1)
- IAM content focused on modern architecture models:  
  - Minimize creating IAM Users, replace with IAM Roles and Identity Center (SSO).
  - Permission Sets for centralized permission management across multiple accounts.
  - Service Control Policies (SCP) to set permission limits at Organization level.
  - Permission Boundaries to ensure developer permissions don't exceed allowed limits.
  - MFA, credential rotation, and Access Analyzer to reduce access information exposure risks.

#### 3. Detection & Continuous Monitoring (Pillar 2)
- CloudTrail org-level: logs all API calls across the entire Organization.
- GuardDuty: detects anomalies such as credential exposure, port scanning, and malicious traffic.
- Security Hub: aggregates all alerts from GuardDuty, IAM Analyzer, S3, etc.
- Logging at every layer:
  - VPC Flow Logs
  - ALB & S3 Access Logs
- EventBridge + Lambda for automatic alerts or locking compromised accounts.
- Detection-as-Code concept for easy management through Git.

#### 4. Infrastructure Protection (Pillar 3)
- Proper VPC design: private subnets for workloads, public subnets only for truly necessary resources.
- Security Groups with inbound whitelist approach.
- NACLs for subnet-level blocking.
- Edge security:
  - AWS WAF
  - AWS Shield (DDoS Protection)
  - AWS Network Firewall

#### 5. Data Protection (Pillar 4)
- KMS manages encryption keys: rotation, key policy, and grants.
- Secrets Manager and SSM Parameter Store for secure secrets management.
- Data classification helps determine appropriate protection policies.

#### 6. Incident Response (Pillar 5)
- IR lifecycle steps according to AWS:
  - Preparation
  - Detection & Analysis
  - Containment
  - Eradication
  - Recovery
  - Post-Incident Review

- Simulated playbooks:
  - Handling compromised IAM keys.
  - S3 bucket public exposure.
  - EC2 malware detection and instance isolation methods.
  - Snapshot, evidence collection, and automated response using Lambda/Step Functions.

---

### Personal Experience and Lessons Learned

- **Learning from AWS experts**:
  - Speakers clearly explained how to build security architecture according to Well-Architected standards.
  - Advanced IAM concepts like SCP, Permission Boundaries, and Identity Center were very intuitive.
  
- **Technical experience**:
  - Practiced validating IAM Policies.
  - Observed GuardDuty alerts and analyzed logs.
  - Explored how to set up org-level CloudTrail and activate Security Hub.
  - Simulated incidents to understand real-world Incident Response processes.

---

### Results Achieved

- Learned more about the role of Security in AWS Well-Architected and how to apply the 5 pillars to real systems.
- Grasped modern IAM models with Identity Center, SCP, and Permission Boundaries.
- Learned how to use incident detection services like GuardDuty, CloudTrail, and Security Hub.
- Gained practical understanding of Incident Response processes and automation using Lambda/Step Functions.

---

### Event Photos
![AWS Security Pillar Event](/images/4-EventParticipated/event5_1.png) 
![AWS Security Pillar Event](/images/4-EventParticipated/event5_2.png)
