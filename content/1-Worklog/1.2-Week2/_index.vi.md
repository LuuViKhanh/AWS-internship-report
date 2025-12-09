---
title: "Worklog Tuần 2"
date: 2025-09-09
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---



### Mục tiêu tuần 2:

* Triển khai và quản lý Amazon EC2 instances trong môi trường VPC.
* Thiết lập hybrid DNS với Route 53 Resolver.
* Triển khai Microsoft AD và cấu hình DNS endpoints.
* Thực hành VPC Peering để kết nối các VPC.
* Thiết lập AWS Transit Gateway cho kết nối multi-VPC.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Triển khai Amazon EC2 Instances: <br>&emsp; + Tạo máy chủ EC2 <br>&emsp; + Kiểm tra kết nối  <br>&emsp; + Tạo NAT Gateway  <br>&emsp;+ Sử dụng Reachability Analyzer <br>&emsp;+ Tạo EC2 Instance Connect Endpoint <br>&emsp;+ AWS Systems Manager Session Manager <br>&emsp; CloudWatch Monitoring & Alerting                                                                                          | 15/09/2025   | 15/09/2025      |[- Bắt đầu với Amazon Virtual Private Cloud (VPC) và AWS Site-to-Site VPN](https://000003.awsstudygroup.com/vi/)|
| 3   | - Thiết lập hybrid DNS với Route 53 Resolver: <br>&emsp;+ Tạo key pair <br>&emsp;+ Khởi tạo CloudFormation Template <br>&emsp;+ Cấu hình security group                                           | 16/09/2025   | 16/09/2025      | [Thiết lập hybrid DNS với Route 53 Resolver ](https://000010.awsstudygroup.com/vi/)|
| 4   | - Kết nối RDGW  <br> - Triển khai Microsoft AD <br>&emsp; - Thiết lập DNS: <br>&emsp; + Tạo Route 53 Outbound Endpoint <br>&emsp; + Tạo Route 53 Resolver Rules <br>&emsp; + Thử nghiệm kết quả <br>&emsp; + Tạo Route 53 Inbound Endpoints | 17/09/2025   | 17/09/2025      | [Thiết lập hybrid DNS voi Route 53 Resolver ](https://000010.awsstudygroup.com/vi/) |
| 5   | - Lắp đặt VPC peering: <br>&emsp; + Khởi tạo CloudFormation Template <br>&emsp; + Tạo Security Group <br>&emsp; + Tạo EC2 instance <br>&emsp; + Cập nhật Network ACL <br> + Tạo kết nối Peering <br> - Kích hoạt Cross-Peer DNS   <br>                  | 18/09/2025   | 18/09/2025      | [Thiết lập VPC Peering](https://000019.awsstudygroup.com/vi/) |
| 6   | - Set up AWS Transit Gateway <br>&emsp; + Tạo Key Pair <br>&emsp; + Khởi tạo CloudFormation Template <br>&emsp; + Tạo Transit Gateway <br>&emsp; + Tạo Transit Gateway Attachments   <br>&emsp; + Tạo Transit Gateway Route Tables   <br>&emsp; + Thêm Transit Gateway Routes vào VPC Route Tables                                                                                           | 19/09/2025   | 19/09/2025      | [Set up AWS Transit Gateway](https://000020.awsstudygroup.com/vi/) |


### Kết quả đạt được tuần 2:

* **Triển khai Amazon EC2 Instances thành công:**
  * Tạo và cấu hình máy chủ EC2 trong VPC
  * Kiểm tra kết nối và troubleshoot network issues
  * Tạo NAT Gateway cho outbound internet access
  * Sử dụng Reachability Analyzer để phân tích connectivity
  * Thiết lập EC2 Instance Connect Endpoint
  * Cấu hình AWS Systems Manager Session Manager
  * Thiết lập CloudWatch Monitoring & Alerting

* **Thiết lập Hybrid DNS với Route 53 Resolver:**
  * Tạo key pair cho bảo mật
  * Khởi tạo và triển khai CloudFormation Template
  * Cấu hình security group cho DNS traffic
  * Hiểu cách DNS resolution hoạt động trong hybrid environment

* **Triển khai Microsoft AD và DNS Configuration:**
  * Kết nối RDGW (Remote Desktop Gateway)
  * Triển khai Microsoft Active Directory
  * Tạo Route 53 Outbound Endpoint
  * Cấu hình Route 53 Resolver Rules
  * Tạo Route 53 Inbound Endpoints
  * Thử nghiệm và xác minh kết quả DNS resolution

* **Thực hành VPC Peering:**
  * Khởi tạo CloudFormation Template cho multi-VPC setup
  * Tạo Security Group cho cross-VPC communication
  * Tạo EC2 instance trong các VPC khác nhau
  * Cập nhật Network ACL cho peering traffic
  * Tạo kết nối VPC Peering
  * Kích hoạt Cross-Peer DNS resolution

* **Thiết lập AWS Transit Gateway:**
  * Tạo Key Pair cho EC2 instances
  * Triển khai CloudFormation Template cho Transit Gateway
  * Tạo và cấu hình Transit Gateway
  * Thiết lập Transit Gateway Attachments
  * Tạo Transit Gateway Route Tables
  * Thêm Transit Gateway Routes vào VPC Route Tables
  * Hiểu cách Transit Gateway hoạt động như hub trung tâm


