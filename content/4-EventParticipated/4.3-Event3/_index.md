---
title: "Event 3"
weight: 1
chapter: false
pre: " <b> 4.3. </b> "
---

## Event Report: AWS Cloud Mastery Series #2 – DevOps on AWS

### Event Purpose
- Build modern DevOps mindset and clearly understand DevOps culture.
- Learn and practice **CI/CD** deployment processes on AWS.
- Guide on using Infrastructure as Code (IaC).
- Master and enhance system observability through **Monitoring & Observability** techniques on AWS, including CloudWatch and AWS X-Ray.
- Participate in hands-on workshops with experts from the AWS Vietnam community.

---

### Speaker List & Topics

#### DevOps Mindset
- **Truong Quang Tinh** – AWS Community Builder, Platform Engineer at TymeX

#### CI/CD Pipeline
- **Văn Hoàng Kha** – Shared about CI/CD processes and Pipeline Workflow models

#### DevOps on AWS – Workshop
- **Bao Huynh** – AWS Community Builder
- **Thinh Nguyen** – AWS Community Builder
- **Vi Tran** – AWS Community Builder

#### Monitoring & Observability
- **Long Huynh** – AWS Community Builder
- **Quy Pham** – AWS Community Builder
- **Nghiem Le** – AWS Community Builder

---

### Highlighted Content

#### 1. DevOps Mindset
- "Collaboration-first" thinking: enhancing coordination between Development – Operations – QA – Security to reduce silos and improve release quality.

- Focus on automating the entire lifecycle: build, test, deploy, and monitoring to reduce manual errors and accelerate deployment speed.

#### 2. CI/CD Pipeline
- Kha presented a visual **Pipeline Workflow** on Lucidchart, describing complete steps from commit to production:
  - GitHub Version Control with standard branches and clear commit processes.
  - Peer Review & Pull Request ensuring code quality and adherence to coding standards.
  - Automated Test & QA including unit tests, integration tests, and security scans running automatically on each push.
  - Multi-stage Deployment (Dev → QA → Pre-Prod → Prod) with clear approval controls and rollback mechanisms.
- This process helped me visualize exactly what a standard CI/CD pipeline looks like in real projects.

#### 3. Infrastructure as Code (IaC)
- IaC knowledge covered:
  - **AWS CloudFormation**: Template-based provisioning, stack management. Supports drift detection to identify changes outside IaC.
  - **AWS CDK (Cloud Development Kit)**: IaC through programming. Reusable constructs, patterns, and libraries with good support for microservices.
  - **Demo**: Deployed infrastructure using both CloudFormation and CDK for comparison.
  - **Discussion**: When to use CloudFormation versus when to use CDK.

#### 4. Monitoring & Observability
- Real-world examples with **Amazon CloudWatch** showed me clearly how to build system observability: Centralized Logs, Custom Metrics, Visual Dashboards, and real-time reactive Alarms.
- Error analysis and tracing demonstration with **AWS X-Ray** showed how to track the entire request flow:
  - Service map to identify dependencies between microservices.
  - Bottleneck analysis to find components causing slowdowns or errors.
  - Request flow visualization to accurately trace incident root causes.
- Thanks to these demos, I clearly understood the value of observability in modern system operations instead of just manually viewing logs as before.

---

### Personal Experience and Lessons Learned

- **Kha's Pipeline Workflow**: Helped me clearly understand how a CI/CD pipeline works in real life — from commit, review, test to deploy — and how to apply it to my team's project workflow.
- **DevOps on AWS Workshop**: Helped me connect theory with practice by directly observing CodePipeline, CodeBuild, and CodeDeploy working seamlessly in a complete automation process.
- **CloudWatch & X-Ray**: For the first time, I clearly saw how to monitor end-to-end performance, identify bottlenecks, and find root causes of incidents without manual log searching. This completely changed my approach to troubleshooting.
- **DevOps Mindset**: I learned how to optimize workflows through automation, increase team collaboration, and shorten feedback loops to improve product quality.

---

### Results Achieved

- Solidly understood DevOps mindset and grasped the overall picture of CI/CD processes, from source control to multi-environment deployment.
- Can independently design and build a standard pipeline based on the model demonstrated in the workshop, to apply directly to team projects.
- Proficiently use CloudWatch and X-Ray to monitor systems, analyze errors, identify bottlenecks, and optimize service performance.
- Equipped with foundational knowledge and proper mindset to continue developing expertise in DevOps Engineer or Cloud Engineer roles.

---

### Event Photos
![DevOps on AWS Event](/images/4-EventParticipated/event3_1.png)
![DevOps on AWS Event](/images/4-EventParticipated/event3_2.png)
