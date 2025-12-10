---
title: "Worklog Tuần 3"
date: 2025-09-09
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---



### Mục tiêu tuần 3:

* Tìm hiểu kiến thức sâu về Amazon EC2 và các thành phần liên quan.
* Triển khai AWS Backup cho việc bảo vệ dữ liệu hệ thống.
* Thực hành File Storage Gateway để kết nối on-premises và cloud.
* Bắt đầu với Amazon S3 và các tính năng cơ bản.
* Tích hợp S3 với CloudFront và quản lý lifecycle.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Học lý thuyết: <br>&emsp; + Amazon Elastic Compute Cloud (EC2) - Instance type <br>&emsp; + Amazon Elastic Compute Cloud (EC2) - AMI / Backup / Key Pair<br>&emsp; + Amazon Elastic Compute Cloud (EC2) - Elastic block store <br>&emsp; + Amazon Elastic Compute Cloud (EC2) - Instance store <br>&emsp; + Amazon Elastic Compute Cloud (EC2) - User data <br>&emsp; + Amazon Elastic Compute Cloud (EC2) - Meta data <br>&emsp; + Amazon Elastic Compute Cloud (EC2) - EC2 auto scaling <br>&emsp; + EC2 Autoscaling - EFS/FSx - Lightsail - MGN                                                                                             | 22/09/2025   | 22/09/2025      | <br> [- Amazon Elastic Compute Cloud ( EC2 ) - Instance type](https://www.youtube.com/watch?v=e7XeKdOVq40&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=73) <br> [- Amazon Elastic Compute Cloud ( EC2 ) - AMI / Backup / Key Pair](https://www.youtube.com/watch?v=yAR6QRT3N1k&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=74) <br> [- Amazon Elastic Compute Cloud ( EC2 ) - Elastic block store](https://www.youtube.com/watch?v=hKr_TfGP7NY&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=75)<br> [- Amazon Elastic Compute Cloud ( EC2 ) -  Instance store](https://www.youtube.com/watch?v=6IHNDJ85aoQ&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=76)<br> [- Amazon Elastic Compute Cloud ( EC2 ) - User data ](https://www.youtube.com/watch?v=_v_43Wi7zjo&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=77)<br> [- Amazon Elastic Compute Cloud ( EC2 ) - Meta data ](https://www.youtube.com/watch?v=Ew3QRaKJQSA&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=78)<br> [- Amazon Elastic Compute Cloud ( EC2 ) - EC2 auto scaling](https://www.youtube.com/watch?v=bbLcPitXJSY&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=79)<br> [- EC2 Autoscaling - EFS/FSx - Lightsail - MGN](https://www.youtube.com/watch?v=hFVYG8WqfU0&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=80)|
| 3   | - Triển khai AWS Backup cho hệ thống - Giới thiệu <br>&emsp; + Triển khai hạ tầng <br>&emsp; + Tạo Backup plan <br>&emsp; + Test Restore  <br>&emsp; + Dọn tài nguyên<br>                                            | 23/09/2025   | 23/09/2025      | [Triển khai AWS Backup cho hệ thống](https://000013.awsstudygroup.com/vi/) |
| 4   | - Triển khai File Storage Gateway <br>&emsp; + Tạo S3 Bucket <br>&emsp; + Tạo EC2 cho Storage Gateway <br>&emsp; + Tạo Storage Gateway <br>&emsp; + Tạo File Shares | 24/09/2025   | 24/09/2025      |[ Triển khai File Storage Gateway](https://000024.awsstudygroup.com/vi/) |
| 5   | - Khởi Đầu Với Amazon S3<br>&emsp; + Tạo S3 bucket <br>&emsp; + Tải dữ liệu <br>&emsp; + Bật tính năng static website <br>&emsp; + Cấu hình public access block <br>&emsp; + Cấu hình public objects <br> - Kiểm tra website <br>                   | 25/09/2025   | 25/09/2025      | [Khởi Đầu Với Amazon S3](https://000057.awsstudygroup.com/vi/) |
| 6   | - Khởi Đầu Với Amazon S3 <br>&emsp; + Khóa tất cả public access <br>&emsp; + Cấu hình Amazon CloudFront <br>&emsp; + Kiểm tra Amazon CloudFront   <br>&emsp; + Bucket Versioning <br>&emsp; + Move objects <br>&emsp; + Sao chép đối tượng đa vùng<br>&emsp; + Xóa tài nguyên                                                                                  | 26/09/2025   | 26/09/2025      | [Khởi Đầu Với Amazon S3](https://000057.awsstudygroup.com/vi/) |


### Kết quả đạt được tuần 3:

* **Tìm hiểu kiến thức sâu về Amazon EC2:**
  * Hiểu các loại Instance types và cách chọn phù hợp
  * Học về AMI, Backup strategies và Key Pair management
  * Hiểu Elastic Block Store (EBS) và các loại volume
  * Biết về Instance Store và sự khác biệt với EBS
  * Sử dụng User Data để tự động hóa cấu hình
  * Truy cập và sử dụng Meta Data service
  * Hiểu EC2 Auto Scaling và các chiến lược scaling
  * Tìm hiểu EFS/FSx, Lightsail và MGN

* **Triển khai AWS Backup thành công:**
  * Triển khai hạ tầng cho backup system
  * Tạo và cấu hình Backup Plan
  * Thực hiện test restore để xác minh backup
  * Dọn dẹp tài nguyên sau khi hoàn thành
  * Hiểu các best practices cho backup strategy

* **Thực hành File Storage Gateway:**
  * Tạo S3 Bucket làm backend storage
  * Triển khai EC2 instance cho Storage Gateway
  * Cấu hình và kích hoạt Storage Gateway
  * Tạo và quản lý File Shares
  * Hiểu cách hybrid storage hoạt động

* **Bắt đầu với Amazon S3 - Cơ bản:**
  * Tạo và cấu hình S3 bucket
  * Tải lên và quản lý dữ liệu
  * Bật tính năng static website hosting
  * Cấu hình public access block cho bảo mật
  * Quản lý public objects và permissions
  * Kiểm tra và xác minh website hoạt động

* **Amazon S3 - Nâng cao và Tích hợp:**
  * Khóa tất cả public access để bảo mật
  * Cấu hình Amazon CloudFront distribution
  * Kiểm tra và tối ưu hóa CloudFront performance
  * Thiết lập Bucket Versioning cho version control
  * Sử dụng lifecycle policies để move objects
  * Thực hiện sao chép đối tượng đa vùng (cross-region replication)
  * Dọn dẹp tài nguyên và quản lý chi phí


