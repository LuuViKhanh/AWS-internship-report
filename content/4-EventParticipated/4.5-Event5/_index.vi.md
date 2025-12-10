---
title: "Event 5"
weight: 1
chapter: false
pre: " <b> 4.5. </b> "
---

## Báo cáo sự kiện AWS Cloud Mastery Series #3 - AWS Well-Architected Security Pillar

### Mục đích của sự kiện
- Workshop được tổ chức nhằm giúp người tham dự hiểu sâu về Security Pillar trong AWS Well-Architected Framework và cách xây dựng hệ thống cloud an toàn, kiểm soát được truy cập, giám sát liên tục, bảo vệ dữ liệu và phản ứng sự cố hiệu quả. Các mục tiêu chính:
  - Hiểu thêm vai trò của Security trong kiến trúc cloud hiện đại.
  - Nắm các nguyên tắc cốt lõi như Least Privilege, Zero Trust, Defense in Depth.
  - Hiểu Shared Responsibility Model và top threats trong môi trường cloud tại Việt Nam.
  - Tìm hiểu 5 Pillars quan trọng: IAM, Detection, Infrastructure Protection, Data Protection, Incident Response.
  - Thực hành phân tích policy, xây dựng guardrails, ghi log, giám sát và mô phỏng tình huống sự cố. 

---

### Danh sách diễn giả & chủ đề chia sẻ
- **Mendel Grabski (Long)** – ex Head of Security & DevOps, Cloud Security Solutions Architect  
- **Truong Quang Tinh** – AWS Community Builder, Platform Engineer tại TymeX  
- **Thịnh Lâm** – FCJ Cloud Engineer  
- **Việt Nguyễn** – FCJ Cloud Engineer
- **Danh Hoàng Hiếu Nghị** – FCJ Cloud Engineer


---

### Nội dung nổi bật
#### 1. Security Foundation & Thách thức trong môi trường cloud
Workshop mở đầu với các vấn đề phổ biến mà môi trường cloud tại Việt Nam gặp phải:
- Quản lý IAM chưa đúng, cấp quá nhiều quyền (over-permission).
- Rò rỉ long-term credentials, key không được rotate.
Diễn giả nhấn mạnh 3 nguyên tắc cốt lõi:
- **Least Privilege** – chỉ cấp quyền tối thiểu.
- **Zero Trust** – không tin cậy mặc định, luôn xác minh.
- **Defense in Depth** – bảo vệ theo nhiều lớp từ IAM → Network → Workload → Data.

#### 2. Identity & Access Management (Pillar 1)
- Nội dung IAM tập trung vào mô hình kiến trúc hiện đại:  
  - Giảm tối đa việc tạo IAM Users, thay bằng IAM Roles và Identity Center (SSO).
  - Permission Sets để quản lý quyền tập trung cho nhiều account.
  - Service Control Policies (SCP) để đặt giới hạn quyền cấp độ Organization.
  - Permission Boundaries đảm bảo quyền developers không vượt mức cho phép.
  - MFA, credential rotation, Access Analyzer để giảm rủi ro lộ thông tin truy cập.

#### 3. Detection & Continuous Monitoring (Pillar 2)
- CloudTrail org-level: ghi lại mọi API call trong toàn bộ Organization.
- GuardDuty: phát hiện bất thường như credential lộ, port scanning, malicious traffic.
- Security Hub: gom toàn bộ cảnh báo từ GuardDuty, IAM Analyzer, S3…
- Logging ở mọi lớp:
  - VPC Flow Logs
  - ALB & S3 Access Logs
- EventBridge + Lambda để tự động cảnh báo hoặc khóa tài khoản bị xâm phạm.
- Khái niệm Detection-as-Code giúp dễ dàng quản lý qua Git.

#### 4. Infrastructure Protection (Pillar 3)
- Thiết kế VPC hợp lý: private subnet cho workloads, public subnet chỉ cho những gì thật sự cần thiết.
- Security Groups hướng inbound whitelist.
- NACLs cho subnet-level blocking.
- Edge security:
  - AWS WAF
  - AWS Shield (DDoS Protection)
  - AWS Network Firewall
#### 5. Data Protection (Pillar 4)
- KMS quản lý encryption keys: rotation, key policy, grant.
- Secrets Manager và SSM Parameter Store để quản lý secrets an toàn.
- Data classification giúp quyết định chính sách bảo vệ phù hợp
#### 6. Incident Response (Pillar 5)
- Các bước IR lifecycle theo AWS:
  - Preparation
  - Detection & Analysis
  - Containment
  - Eradication
  - Recovery
  - Post-Incident Review

- Playbook được mô phỏng:
  - Xử lý compromised IAM key.
  - S3 bucket public exposure.
  - EC2 malware detection và cách cô lập instance.
  - Snapshot, thu thập evidence, tự động phản ứng bằng Lambda/Step Functions.
---

### Trải nghiệm và bài học cá nhân
- **Học hỏi từ chuyên gia AWS**:
  - Diễn giả giải thích rõ cách xây dựng kiến trúc bảo mật theo chuẩn Well-Architected.
  - Các khái niệm IAM nâng cao như SCP, Permission Boundaries, Identity Center rất trực quan.
  
- **Trải nghiệm kỹ thuật**:
  - Thực hành validate IAM Policy.
  - Quan sát cảnh báo GuardDuty và phân tích log.
  - Tìm hiểu cách thiết lập CloudTrail org-level và kích hoạt Security Hub.
  - Mô phỏng sự cố để hiểu quy trình Incident Response trong thực tế.

---

### Kết quả đạt được
- Hiểu thêm vai trò của Security trong AWS Well-Architected và cách áp dụng 5 pillars vào hệ thống thực tế.
- Nắm được mô hình IAM hiện đại với Identity Center, SCP và Permission Boundaries.
- Được xem cách sử dụng các dịch vụ phát hiện sự cố như GuardDuty, CloudTrail và Security Hub.
- Có hiểu biết thực tế về quy trình Incident Response và cách automation bằng Lambda/Step Functions. 

---

### Hình ảnh tại sự kiện
![IoT Weather Station Architecture](/images/4-EventParticipated/event5_1.png) 
![IoT Weather Station Architecture](/images/4-EventParticipated/event5_2.png)
