---
title: "Worklog Tuần 6"
date: 2025-09-09
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---



### Mục tiêu tuần 6:

* Tối ưu hóa chi phí EC2 sử dụng AWS Lambda và automation.
* Quản lý tài nguyên hiệu quả bằng Tag và Resource Groups.
* Tìm hiểu quản lý truy cập với AWS IAM và Resource Tags.
* Thực hành giới hạn quyền với IAM Permission Boundary.
* Triển khai mã hóa dữ liệu với AWS KMS.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tối ưu chi phí EC2 với Lambda: <br>&emsp; + Tạo VPC <br>&emsp; + Tạo Security Group <br>&emsp; + Tạo EC2 instance <br>&emsp; + Incoming Web-hooks Slack <br>&emsp; + Tạo Tag cho Instance <br>&emsp; + Tạo Role cho Lambda <br>&emsp; + Tạo Lambda Function <br>&emsp; + Kiểm tra kết quả                                                                                            | 13/10/2025   | 13/10/2025      | [Tối ưu chi phí EC2 với Lambda](https://000022.awsstudygroup.com/vi/)|
| 3   | - Quản lý tài nguyên bằng Tag và Resource Groups: <br>&emsp; + Sử dụng Tag <br>&emsp; + Tạo một Resource Group <br>&emsp; + Dọn dẹp tài nguyên                                            | 14/10/2025   | 14/10/2025      | [Quản lý tài nguyên bằng Tag và Resource Groups](https://000027.awsstudygroup.com/vi/) |
| 4   | - Quản lý truy cập vào dịch vụ EC2 Resource Tag với AWS IAM: <br>&emsp; + Tạo IAM user <br>&emsp; + Tạo IAM Policy <br>&emsp; + Tạo IAM Role <br>&emsp; + Kiểm tra chính sách <br>&emsp; + Dọn dẹp tài nguyên | 15/10/2025   | 15/10/2025      | [Quản lý truy cập vào dịch vụ EC2 Resource Tag với AWS IAM](https://000028.awsstudygroup.com/vi/) |
| 5   | - GIỚI HẠN QUYỀN CỦA USER VỚI IAM PERMISSION BOUNDARY: <br>&emsp; + Tạo Policy Giới hạn <br>&emsp; + Tạo IAM User Giới Hạn <br>&emsp; + Kiểm tra IAM User Giới Hạn <br>&emsp; + Dọn dẹp tài nguyên                   | 16/10/2025   | 16/10/2025      | [GIỚI HẠN QUYỀN CỦA USER VỚI IAM PERMISSION BOUNDARY](https://000030.awsstudygroup.com/vi/) |
| 6   | - Mã hóa ở trạng thái lưu trữ với AWS KMS: <br>&emsp; + Tạo Policy và Role <br>&emsp; + Tạo Group và User <br>&emsp; + Tạo Key Management Service <br>&emsp; + Tạo Amazon S3 <br>&emsp; + Tạo AWS CloudTrail và Amazon Athena <br>&emsp; +Kiểm thử và chia sẻ dữ liệu mã hóa trên S3 <br>&emsp; + Dọn dẹp tài nguyên                                                                                         | 17/10/2025   | 17/10/2025      | [Mã hóa ở trạng thái lưu trữ với AWS KMS](https://000033.awsstudygroup.com/vi/) |


### Kết quả đạt được tuần 6:

* **Tối ưu hóa chi phí EC2 với Lambda:**
  * Tạo VPC và cấu hình môi trường mạng
  * Thiết lập Security Group cho bảo mật
  * Triển khai EC2 instance cho testing
  * Cấu hình Incoming Web-hooks Slack cho thông báo
  * Tạo và quản lý Tag cho EC2 instances
  * Tạo IAM Role cho Lambda function
  * Viết và triển khai Lambda Function tự động hóa
  * Kiểm tra kết quả và xác minh tính năng cost optimization

* **Quản lý tài nguyên với Tag và Resource Groups:**
  * Hiểu và áp dụng chiến lược Tag cho tài nguyên
  * Tạo và cấu hình Resource Groups
  * Quản lý và tổ chức tài nguyên theo nhóm
  * Dọn dẹp tài nguyên một cách hiệu quả
  * Hiểu lợi ích của resource organization

* **Quản lý truy cập EC2 với IAM và Resource Tags:**
  * Tạo và cấu hình IAM users
  * Viết và triển khai IAM Policies dựa trên tags
  * Tạo và quản lý IAM Roles
  * Kiểm tra và xác minh chính sách truy cập
  * Dọn dẹp tài nguyên và IAM entities
  * Hiểu fine-grained access control

* **Giới hạn quyền với IAM Permission Boundary:**
  * Tạo Policy giới hạn (Permission Boundary)
  * Tạo IAM User với giới hạn quyền
  * Kiểm tra và test IAM User giới hạn
  * Hiểu cách Permission Boundary hoạt động
  * Dọn dẹp tài nguyên và policies
  * Tìm hiểu security best practices

* **Mã hóa dữ liệu với AWS KMS:**
  * Tạo IAM Policy và Role cho KMS
  * Thiết lập IAM Group và User
  * Tạo và quản lý AWS Key Management Service keys
  * Cấu hình Amazon S3 với encryption
  * Triển khai AWS CloudTrail và Amazon Athena cho monitoring
  * Kiểm thử và chia sẻ dữ liệu mã hóa trên S3
  * Dọn dẹp tài nguyên và quản lý chi phí
  * Hiểu encryption at rest và key management


