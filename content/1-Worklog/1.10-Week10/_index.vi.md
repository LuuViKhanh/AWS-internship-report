---
title: "Worklog Tuần 10"
date: 2025-09-09
weight: 2
chapter: false
pre: " <b> 1.10. </b> "
---



### Mục tiêu tuần 10:

* Tiếp tục phát triển và hoàn thiện dự án cuối khóa.
* Tích hợp API vào frontend và giải quyết các vấn đề CORS.
* Chuyển đổi từ Node.js sang Java cho Lambda functions.
* Giải quyết các lỗi kỹ thuật và tối ưu hóa deployment.
* Tham dự sự kiện AWS Cloud Mastery Series.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tiếp tục làm project <br>&emsp; + Tạo API Gateway và tích hợp Lambda <br>&emsp; + Tạo IAM Role <br>&emsp; + Tạo Lambda Function DynamoDB_API_Handler <br> - Tạo API Gateway và tích hợp với Lambda <br>&emsp; + Truy cập dịch vụ API Gateway <br>&emsp; + Tạo REST API <br>&emsp; + Tạo Resource, tạo Method cho từng bảng trong DynamoDB <br>&emsp; + Gắn Lambda cho từng method <br>&emsp; + Bị lỗi The final policy size (20588) is bigger than the limit (20480)                                                                                             | 11/08/2025   | 11/08/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - Tiếp tục làm project <br>&emsp; + Lên văn phòng làm project cùng thành viên trong nhóm  <br>&emsp; + Tích hợp API vào frontend <br>&emsp; + Gặp lỗi CORS policy: No 'Access-Control-Allow-Origin' <br>&emsp; + Sửa method OPTIONS để sửa lỗi <br>&emsp; + Sửa Lambda <br> - Gặp lỗi the server responded with a status of 400 <br>&emsp; + Tiếp tục sửa code và logic trong Lambda                                             | 12/08/2025   | 12/08/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Tiếp tục làm project <br>&emsp; + Làm lại từ đầu code Java để deploy lên Lambda <br>&emsp; + Chỉnh sửa code nhiều lần để đưa code từ local lên Lambda <br>&emsp; + Build file JAR <br>&emsp; + Deploy lên Lambda  | 13/08/2025   | 13/08/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Tiếp tục làm project <br>&emsp; + Gặp lỗi ClassNotFoundException <br>&emsp; + Đổi từ Spring Cloud Function sang aws-serverless-java-container-springboot2 <br>&emsp; + Thêm maven-shade-plugin  <br>&emsp; + Thêm core và event <br>&emsp; + Đã sửa được lỗi                   | 14/08/2025   | 15/08/2025      | [Giải quyết lỗi ClassNotFoundException](https://docs.aws.amazon.com/lambda/latest/dg/java-package.html#java-package-maven) |
| 6   | - Tham dự sự kiện AWS Cloud Mastery Series #1                                                                                           | 15/08/2025   | 15/08/2025      | <https://cloudjourney.awsstudygroup.com/> |


### Kết quả đạt được tuần 10:

* **Tiếp tục phát triển API Gateway và Lambda:**
  * Tiếp tục xây dựng API Gateway và tích hợp Lambda
  * Tạo và cấu hình IAM Role cho Lambda functions
  * Triển khai Lambda Function DynamoDB_API_Handler
  * Truy cập và thiết lập dịch vụ API Gateway
  * Tạo REST API và cấu hình endpoints
  * Tạo Resources và Methods cho từng bảng trong DynamoDB
  * Gắn Lambda functions cho từng HTTP method
  * Gặp và giải quyết lỗi policy size limit

* **Làm việc nhóm và tích hợp frontend:**
  * Lên văn phòng làm project cùng thành viên trong nhóm
  * Tích hợp API vào frontend application
  * Gặp và giải quyết lỗi CORS policy: No 'Access-Control-Allow-Origin'
  * Sửa method OPTIONS để giải quyết lỗi CORS
  * Chỉnh sửa Lambda function để hỗ trợ CORS
  * Gặp lỗi "the server responded with a status of 400"
  * Tiếp tục sửa code và logic trong Lambda

* **Chuyển đổi sang Java và tối ưu hóa deployment:**
  * Làm lại từ đầu code Java để deploy lên Lambda
  * Chỉnh sửa code nhiều lần để đưa code từ local lên Lambda
  * Build file JAR cho Java application
  * Deploy ứng dụng Java lên AWS Lambda
  * Hiểu các thách thức khi chuyển đổi ngôn ngữ

* **Giải quyết lỗi ClassNotFoundException:**
  * Gặp lỗi ClassNotFoundException khi chạy Java trên Lambda
  * Đổi từ Spring Cloud Function sang aws-serverless-java-container-springboot2
  * Thêm maven-shade-plugin vào Maven configuration
  * Thêm AWS Lambda core và event dependencies
  * Đã sửa được lỗi và Lambda hoạt động ổn định
  * Nắm vững cách package Java applications cho AWS Lambda

* **Tham dự sự kiện và học hỏi:**
  * Tham dự sự kiện AWS Cloud Mastery Series #1
  * Tìm hiểu các xu hướng mới trong AWS cloud services
  * Kết nối với cộng đồng AWS và chia sẻ kinh nghiệm
  * Cập nhật kiến thức về best practices và new features
  * Ứng dụng kiến thức học được vào dự án thực tế


