---
title: "Worklog Tuần 9"
date: 2025-09-09
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---



### Mục tiêu tuần 9:

* Tiếp tục ôn tập và củng cố kiến thức sau kỳ thi.
* Bắt đầu triển khai dự án cuối khóa với các dịch vụ serverless.
* Thiết lập Lambda Trigger và tích hợp với S3.
* Xây dựng API Gateway và kết nối với Lambda và DynamoDB.
* Bắt đầu làm workshop framework cho dự án.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tiếp tục review lại đề để ôn lại kiến thức                                                                                            | 3/11/2025   | 3/11/2025      | [Ôn tập kiến thức AWS](https://kananinirav.com/practice-exam/exams.html) |
| 3   | - Bắt đầu làm project <br>&emsp; + Chuẩn bị & Cấu hình Lambda Trigger cho S3 <br>&emsp; + Tạo S3 Bucket <br>&emsp; + Cấu hình Lambda Trigger cho S3 <br>&emsp; + Upload dữ liệu CSV lên Bucket                                           | 4/11/2025   | 4/11/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Tiếp tục làm project <br>&emsp; + Tạo API Gateway và tích hợp Lambda <br>&emsp; + Tạo IAM Role <br>&emsp; + Tạo Lambda Function DynamoDB_API_Handler <br> - Tạo API Gateway và tích hợp với Lambda <br>&emsp; + Truy cập dịch vụ API Gateway <br>&emsp; + Tạo REST API <br>&emsp; + Tạo Resource, tạo Method cho từng bảng trong DynamoDB <br>&emsp; + Gắn Lambda cho từng method <br>&emsp; + Bị lỗi The final policy size (20588) is bigger than the limit (20480) | 5/11/2025   | 5/11/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Tiếp tục hoàn thiện API Gateway: <br>&emsp; + Xóa Lambda DynamoDB_API_Handler cũ để xóa toàn bộ policies cũ và tạo DynamoDB_API_Handler mới với code được tinh chỉnh  <br>&emsp; + Tạo proxy Resource và Method mới <br>&emsp; + Gắn Lambda <br>&emsp; + Bật CORS <br>&emsp; + Deploy API <br>&emsp; + Kiểm thử API bằng Postman                  | 6/11/2025   | 6/11/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - Sau khi hoàn thành phần API Gateway: <br>&emsp; + Bắt đầu làm workshop framework                                                                                         | 7/11/2025   | 7/11/2025      | <https://cloudjourney.awsstudygroup.com/> |


### Kết quả đạt được tuần 9:

* **Ôn tập và củng cố kiến thức:**
  * Tiếp tục review lại các đề thi để ôn lại kiến thức
  * Củng cố các khái niệm AWS cơ bản sau kỳ thi
  * Xác định các điểm yếu cần cải thiện
  * Chuẩn bị kiến thức cho dự án thực tế

* **Bắt đầu triển khai dự án:**
  * Chuẩn bị và lên kế hoạch cho dự án cuối khóa
  * Tìm hiểu kiến trúc serverless và các thành phần
  * Xác định các dịch vụ AWS cần sử dụng
  * Thiết kế data flow và architecture

* **Thiết lập Lambda Trigger cho S3:**
  * Tạo và cấu hình S3 Bucket cho dự án
  * Cấu hình Lambda Trigger để xử lý sự kiện S3
  * Upload dữ liệu CSV lên S3 Bucket
  * Kiểm tra trigger hoạt động và xử lý dữ liệu
  * Hiểu event-driven architecture patterns

* **Xây dựng API Gateway và tích hợp:**
  * Tạo và cấu hình IAM Role cho Lambda
  * Viết và triển khai Lambda Function DynamoDB_API_Handler
  * Truy cập và thiết lập dịch vụ API Gateway
  * Tạo REST API và cấu hình endpoints
  * Tạo Resources và Methods cho từng bảng trong DynamoDB
  * Gắn Lambda function cho từng HTTP method

* **Giải quyết vấn đề và tối ưu hóa:**
  * Gặp và giải quyết lỗi policy size limit (20588 > 20480)
  * Xóa Lambda cũ và tạo DynamoDB_API_Handler mới
  * Tối ưu hóa code và tinh chỉnh policies
  * Tạo proxy Resource và Method mới
  * Gắn Lambda và bật CORS cho API
  * Deploy API và kiểm thử bằng Postman

* **Hoàn thiện API và chuẩn bị workshop:**
  * Hoàn thành phần API Gateway và kiểm tra tính năng
  * Bắt đầu làm workshop framework cho dự án
  * Chuẩn bị tài liệu và hướng dẫn
  * Lên kế hoạch cho các bước tiếp theo
  * Đánh giá tiến độ và chất lượng dự án


