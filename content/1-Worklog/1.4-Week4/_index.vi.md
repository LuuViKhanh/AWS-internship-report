---
title: "Worklog Tuần 4"
date: 2025-09-09
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---



### Mục tiêu tuần 4:

* Nắm vững kiến thức chuyên sâu về các dịch vụ lưu trữ AWS.
* Thực hành triển khai AWS Backup với các tính năng nâng cao.
* Học cách sử dụng VM Import/Export để migration.
* Triển khai File Storage Gateway cho hybrid cloud.
* Tham gia sự kiện về AI-Driven Development.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Học lý thuyết:<br>&emsp; + Dịch Vụ Lưu Trữ Trên AWS  <br>&emsp; + Amazon Simple Storage Service (S3) - Access Point - Storage Class <br>&emsp; + S3 Static Website & CORS - Control Access - Object Key & Performance - Glacier <br>&emsp; + Snow Family - Storage Gateway - Backup                                                                                           | 29/09/2025   | 29/09/2025      |<br> [- Dịch Vụ Lưu Trữ Trên AWS](https://www.youtube.com/watch?v=hsCfP0IxoaM&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=103) <br> [- Amazon Simple Storage Service ( S3 ) - Access Point - Storage Class](https://www.youtube.com/watch?v=_yunukwcAwc&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=104) <br> [- S3 Static Website & CORS - Control Access - Object Key & Performance - Glacier](https://www.youtube.com/watch?v=mPBjB6Ltl_Q&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=105)<br> [- Snow Family - Storage Gateway - Backup](https://www.youtube.com/watch?v=YXn8Q_Hpsu4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=106)<br> |
| 3   | - Triển khai AWS Backup cho hệ thống: <br>&emsp; + Tạo S3 Bucket <br>&emsp; + Triển khai hạ tầng <br>&emsp; + Tạo Backup plan <br>&emsp; + Thiết lập thông báo <br>&emsp; + Kiểm tra hoạt động <br>&emsp; + Dọn dẹp tài nguyên<br>                                            | 30/09/2025   | 30/09/2025      | [Triển khai AWS Backup cho hệ thống](https://000013.awsstudygroup.com/vi/) |
| 4   | - VM Import/Export: <br>&emsp; + Chuẩn bị máy ảo <br>&emsp; + Export máy ảo từ On-premise <br>&emsp; + Tải máy ảo lên AWS <br>&emsp; + Import máy ảo vào AWS <br>&emsp; + Triển khai EC2 Instance từ AMI <br>&emsp; + Thiết lập ACL cho S3 Bucket <br>&emsp; + Export máy ảo từ EC2 Instance <br>&emsp; + Export máy ảo từ AMI <br>&emsp; + Dọn dẹp tài nguyên<br> | 1/10/2025   | 1/10/2025      | [VM Import/Export](https://000014.awsstudygroup.com/vi/) |
| 5   | - Triển khai File Storage Gateway: <br>&emsp; + Tạo S3 Bucket <br>&emsp; + Tạo EC2 cho Storage Gateway <br>&emsp; + Tạo Storage Gateway <br>&emsp; + Tạo File Shares <br>&emsp; + Kết nối File shares ở máy On-premise <br>&emsp; + Dọn dẹp tài nguyên   <br>                  | 2/10/2025   | 2/10/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - Tham gia sự kiện AI-Driven Development Life Cycle: Reimagining Software Engineering                                                                                       | 3/10/2025   | 3/10/2025      | <https://cloudjourney.awsstudygroup.com/> |


### Kết quả đạt được tuần 4:

* **Nắm vững kiến thức chuyên sâu về Storage Services:**
  * Hiểu tổng quan về các dịch vụ lưu trữ trên AWS
  * Nắm vững Amazon S3 Access Points và Storage Classes
  * Hiểu S3 Static Website, CORS, Control Access
  * Biết về Object Key optimization và Performance tuning
  * Tìm hiểu Amazon Glacier cho long-term storage
  * Học về Snow Family cho data migration
  * Nắm vững Storage Gateway và AWS Backup services

* **Triển khai AWS Backup nâng cao:**
  * Tạo S3 Bucket cho backup storage
  * Triển khai hạ tầng backup hoàn chỉnh
  * Tạo và cấu hình Backup Plan chi tiết
  * Thiết lập hệ thống thông báo (notifications)
  * Kiểm tra và monitor hoạt động backup
  * Dọn dẹp tài nguyên và quản lý chi phí

* **Thành thạo VM Import/Export:**
  * Chuẩn bị và đóng gói máy ảo từ on-premises
  * Export máy ảo từ môi trường on-premise
  * Tải máy ảo lên AWS S3
  * Import máy ảo vào AWS thành AMI
  * Triển khai EC2 Instance từ AMI đã import
  * Thiết lập ACL cho S3 Bucket security
  * Export máy ảo từ EC2 Instance và AMI
  * Dọn dẹp tài nguyên sau migration

* **Triển khai File Storage Gateway hoàn chỉnh:**
  * Tạo S3 Bucket làm backend storage
  * Triển khai EC2 instance cho Storage Gateway
  * Cấu hình và kích hoạt Storage Gateway
  * Tạo và quản lý File Shares
  * Kết nối File Shares từ máy on-premise
  * Test và xác minh kết nối hybrid storage
  * Dọn dẹp tài nguyên và tối ưu hóa

* **Tham gia sự kiện AI-Driven Development:**
  * Tìm hiểu về AI-Driven Development Life Cycle
  * Hiểu cách AI đang thay đổi Software Engineering
  * Nắm được các xu hướng mới trong phát triển phần mềm
  * Kết nối với cộng đồng developer và chia sẻ kinh nghiệm


