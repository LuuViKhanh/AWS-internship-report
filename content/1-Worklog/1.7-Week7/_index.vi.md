---
title: "Worklog Tuần 7"
date: 2025-09-09
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---



### Mục tiêu tuần 7:

* Hoàn thiện và tối ưu hóa kiến trúc dự án cuối khóa.
* Nâng cao kiến thức về IAM Role và Condition policies.
* Ôn tập và nâng sâu kiến thức về Database services.
* Ôn lại các khái niệm cơ bản về Cloud Computing và IAM.
* Nắm vững EC2 và Storage concepts cho kỳ thi giữa kỳ.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tiếp tục chỉnh sửa kiến trúc và cân nhắc những dịch vụ sẽ dùng: <br>&emsp; + Thay thế Amazon RDS thành DynamoDB <br>&emsp; + Thay Amazon Lex thành Bedrock <br>&emsp; + Chỉnh sửa sơ đồ toàn diện  <br>&emsp; + Chỉnh sửa kích thước đúng chuẩn                                                                                              | 20/10/2025   | 20/10/2025      |
| 3   | - IAM Role & Condition: <br>&emsp; + Giới thiệu về IAM <br>&emsp; + Tạo IAM Group <br>&emsp; + Tạo IAM User <br>&emsp; + Cấu hình Role Condition <br>&emsp; + Dọn dẹp tài nguyên <br>&emsp;                                             | 21/10/2025   | 21/10/2025      | [IAM Role & Condition](https://000044.awsstudygroup.com/vi/) |
| 4   | - Học lý thuyết: <br>&emsp; + Ôn tập Database Concepts <br>&emsp; + Amazon RDS & Amazon Aurora <br>&emsp; + Redshift - ElastiCache | 22/10/2025   | 22/10/2025      | <br> [- Database Concepts review](https://www.youtube.com/watch?v=OOD2RwWuLRw&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=217) <br> [-  Amazon RDS & Amazon Aurora](https://www.youtube.com/watch?v=qbrobQZrokY&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=218) <br> [- Redshift - Elasticache](https://www.youtube.com/watch?v=UvdiRW34aNI&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=219)<br> |
| 5   | - Ôn lý thuyết về cloud computing: <br>&emsp; + What is Cloud Computing? <br>&emsp; + AWS Global Infrastructure <br>&emsp; + AWS Shared Responsibility Model <br> - Ôn lý thuyết về IAM: Identity Access & Management (IAM) <br>&emsp; + What Is IAM? <br>&emsp; +Multi-Factor Authentication (MFA) <br>&emsp; + CLI và SDK <br> - Học và nắm vững Well Architected Framework                  | 23/10/2025   | 23/10/2025      | <br> [- Cloud computing](https://kananinirav.com/sections/cloud_computing.html) <br> [- IAM: Identity Access & Management (IAM)](https://kananinirav.com/sections/iam.html) <br> [- Well Architected Framework](https://kananinirav.com/sections/architecting_and_ecosystem.html)<br> |
| 6   | - Ôn lý thuyết về EC2: Virtual Machines: <br>&emsp; + What is Amazon EC2? <br>&emsp; +  Security Groups <br>&emsp; + EC2 Instance Launch Types <br> - Ôn lý thuyết về EC2 Instance Storage <br>&emsp; + EBS Volumes <br>&emsp; + EFS: Elastic File System và EFS Infrequent Access (EFS-IA) <br>&emsp; + Đặc điểm EC2 Instance Store <br> - Học và nắm vững Well Architected Framework                                                                                           | 24/10/2025   | 24/10/2025      | <br> [- EC2: Virtual Machines](https://kananinirav.com/sections/ec2.html) <br> [- EC2 Instance Storage](https://kananinirav.com/sections/ec2_storage.html) <br> [- Well Architected Framework](https://kananinirav.com/sections/architecting_and_ecosystem.html)<br> |


### Kết quả đạt được tuần 7:

* **Hoàn thiện kiến trúc dự án:**
  * Tiếp tục chỉnh sửa và tối ưu hóa kiến trúc
  * Cân nhắc và lựa chọn những dịch vụ phù hợp nhất
  * Thay thế Amazon RDS bằng DynamoDB cho NoSQL solution
  * Thay Amazon Lex bằng Amazon Bedrock cho AI capabilities
  * Chỉnh sửa sơ đồ toàn diện và tổng thể
  * Chỉnh sửa kích thước đúng chuẩn và professional

* **Nâng cao kiến thức IAM Role & Condition:**
  * Ôn tập và giới thiệu sâu về IAM
  * Tạo và quản lý IAM Groups
  * Tạo và cấu hình IAM Users
  * Cấu hình Role Conditions cho fine-grained access
  * Dọn dẹp tài nguyên và best practices
  * Hiểu conditional access và context-based permissions

* **Nắm vững Database Concepts:**
  * Ôn tập Database Concepts cơ bản
  * Hiểu sâu về Amazon RDS và Amazon Aurora
  * Tìm hiểu Amazon Redshift cho data warehousing
  * Học về Amazon ElastiCache cho caching solutions
  * So sánh các loại database và use cases
  * Hiểu performance optimization strategies

* **Ôn tập Cloud Computing Fundamentals:**
  * Ôn lại "What is Cloud Computing?" và các khái niệm cơ bản
  * Nắm vững AWS Global Infrastructure
  * Hiểu rõ AWS Shared Responsibility Model
  * Ôn tập IAM: Identity Access & Management
  * Nắm vững Multi-Factor Authentication (MFA)
  * Hiểu CLI và SDK usage
  * Học và nắm vững Well Architected Framework

* **Nắm vững EC2 và Storage:**
  * Ôn tập "What is Amazon EC2?" và các concepts
  * Hiểu Security Groups và network security
  * Nắm vững EC2 Instance Launch Types
  * Học về EBS Volumes và storage options
  * Hiểu EFS: Elastic File System và EFS-IA
  * Nắm vững đặc điểm EC2 Instance Store
  * Tiếp tục học Well Architected Framework principles


