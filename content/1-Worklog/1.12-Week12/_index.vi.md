---
title: "Worklog Tuần 12"
date: 2025-09-09
weight: 2
chapter: false
pre: " <b> 1.12 </b> "
---


### Mục tiêu tuần 12:

* Tiếp tục phát triển và hoàn thiện dự án cuối khóa.
* Phối hợp với team database và frontend để tích hợp hệ thống.
* Giải quyết các lỗi kỹ thuật về data type và configuration.
* Xử lý các vấn đề CORS trong API integration.
* Viết workshop và chuẩn bị tài liệu dự án.
* Tham dự sự kiện AWS Cloud Mastery Series về Security Pillar.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tiếp tục làm project <br>&emsp; + Phối hợp với bên database để kết nối dữ liệu  <br>&emsp; +  Gặp loi java.lang.NumberFormatException: Character N is neither a decimal digit number, decimal point, nor \"e\" notation exponential mark" <br>&emsp; + Lỗi này là do có null trong integer <br>&emsp; + Sua lai database, bỏ null <br>&emsp; Đã hết loi<br> - Gặp lỗi java.lang.IllegalArgumentException: Could not resolve placeholder 'app.jwt.secret' in value \"${app.jwt.secret}\ <br>&emsp; + thêm environment variable vào <br>&emsp; Đã hết loi                                                                                           | 24/11/2025   | 24/11/2025      |
| 3   | - Tiếp tục làm project <br>&emsp; + Phối hợp với bên front-end để gọi api  <br>&emsp; +  Gặp loi java.lang.IllegalArgumentException: Boolean string was not 'true' or 'false': 1" <br>&emsp; + Sửa các boolean thành integer <br> Đã hết loi                                            | 25/11/2025   | 25/11/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 4   |- Tiếp tục làm project <br>&emsp; + Phối hợp với bên front end để goi api  <br>&emsp; +  Gặp loi has been blocked by CORS policy: No 'Access-Control-Allow-Origin' header is present on the requested resource <br>&emsp; + Sua bên fe <br>&emsp; + Thêm vào method options, Access-Control-Allow-Methods     ->  'GET,POST,PUT,DELETE,OPTIONS' <br> Đã hết loi | 26/11/2025   | 26/11/2025      | [loi has been blocked by CORS policy: No 'Access-Control-Allow-Origin' header is present on the requested resource](https://www.youtube.com/watch?v=PNtFSVU-YTI) |
| 5   | - Tiếp tục làm project <br>&emsp; + Viết workshop  <br>&emsp; + push backend lên github                  | 27/11/2025   | 27/11/2025      | [workshop](https://github.com/Huntrot/Group7_Workshop.git) <br>[backend](https://github.com/LuuViKhanh/Group7_Workshop_BE.git)  |
| 6   | - Tham dự sự kiện  AWS Cloud Mastery Series #3 - AWS Well-Architected Security Pillar                                                                                       | 28/11/2025   | 28/11/2025      | [AWS Cloud Mastery Series #3](https://luma.com/0nl16e1p?tk=OBSrJI) |


### Kết quả đạt được tuần 12:

* **Giải quyết lỗi NumberFormatException và JWT configuration:**
  * Phối hợp với team database để kết nối dữ liệu
  * Gặp lỗi java.lang.NumberFormatException: Character N is neither a decimal digit number
  * Phát hiện lỗi do có giá trị null trong các trường integer
  * Sửa lại database, loại bỏ các giá trị null
  * Gặp lỗi Could not resolve placeholder 'app.jwt.secret'
  * Thêm environment variable để giải quyết vấn đề JWT configuration
  * Đã giải quyết tất cả các lỗi và hệ thống hoạt động ổn định

* **Phối hợp với frontend team và giải quyết lỗi API:**
  * Phối hợp với bên frontend để gọi API
  * Gặp lại lỗi java.lang.IllegalArgumentException về Boolean data type
  * Sửa các boolean thành integer để đảm bảo tính nhất quán
  * Đã giải quyết vấn đề data type mismatch
  * Nâng cao kỹ năng debug và xử lý lỗi integration

* **Xử lý vấn đề CORS trong API Gateway:**
  * Tiếp tục phối hợp với frontend team để gọi API
  * Gặp lỗi CORS policy: No 'Access-Control-Allow-Origin' header
  * Sửa bên frontend để xử lý CORS
  * Thêm vào method OPTIONS: Access-Control-Allow-Methods -> 'GET,POST,PUT,DELETE,OPTIONS'
  * Đã giải quyết hoàn toàn vấn đề CORS
  * Nắm vững cách cấu hình CORS cho API Gateway

* **Viết workshop và quản lý source code:**
  * Viết workshop cho dự án để hướng dẫn người khác
  * Push backend code lên GitHub để quản lý version
  * Tổ chức và document hóa toàn bộ dự án
  * Chuẩn bị tài liệu cho việc demo và bàn giao
  * Nâng cao kỹ năng viết tài liệu kỹ thuật

* **Tham dự sự kiện và học hỏi về Security:**
  * Tham dự sự kiện AWS Cloud Mastery Series #3
  * Học về AWS Well-Architected Security Pillar
  * Nắm được các best practices về bảo mật trên AWS
  * Ứng dụng kiến thức security vào dự án thực tế
  * Cập nhật kiến thức về security compliance và governance

* **Cải thiện kỹ năng teamwork và problem-solving:**
  * Làm việc hiệu quả với nhiều team (database, frontend)
  * Giải quyết nhanh chóng các vấn đề kỹ thuật phức tạp
  * Nâng cao kỹ năng debug và troubleshooting
  * Phát triển kỹ năng giao tiếp và điều phối dự án


