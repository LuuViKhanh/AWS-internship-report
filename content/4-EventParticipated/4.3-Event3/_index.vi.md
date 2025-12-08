---
title: "Event 3"
weight: 1
chapter: false
pre: " <b> 4.3. </b> "
---

## Báo cáo sự kiện AWS Cloud Mastery Series #2 – DevOps on AWS

### Mục đích của sự kiện
- Xây dựng tư duy DevOps hiện đại và hiểu rõ văn hoá DevOps.  
- Học và thực hành quy trình **CI/CD** triển khai trên AWS. 
- Hướng dẫn sử dụng hạ tầng dưới dạng mã (Infrastructure as Code). 
- Nắm được và Nâng cao khả năng quan sát hệ thống thông qua các kỹ thuật **Monitoring & Observability** trên AWS, gồm CloudWatch và AWS X-Ray.  
- Tham gia workshop thực hành với các chuyên gia trong cộng đồng AWS Việt Nam.  

---

### Danh sách diễn giả & chủ đề chia sẻ
#### DevOps Mindset
- **Truong Quang Tinh** – AWS Community Builder, Platform Engineer – TymeX  

#### CI/CD Pipeline
- **Văn Hoàng Kha** – Chia sẻ về quy trình CI/CD và mô hình Pipeline Workflow (người trình bày nội dung của slide trong ảnh).  

#### DevOps on AWS – Workshop
- **Bao Huynh** – AWS Community Builder  
- **Thinh Nguyen** – AWS Community Builder  
- **Vi Tran** – AWS Community Builder  

#### Monitoring & Observability
- **Long Huynh** – AWS Community Builder  
- **Quy Pham** – AWS Community Builder  
- **Nghiem Le** – AWS Community Builder  

---

### Nội dung nổi bật
#### 1. DevOps Mindset
- Tư duy “collaboration-first”: tăng cường phối hợp giữa Development – Operations – QA Security để giảm silo và cải thiện chất lượng release.

- Tập trung tự động hóa toàn vòng đời: build, test, deploy, monitoring nhằm giảm lỗi thủ công và tăng tốc độ triển khai. 

#### 2. CI/CD Pipeline 
- Anh Kha trình bày **Pipeline Workflow** trực quan trên Lucidchart, mô tả đầy đủ các bước từ commit đến production:  
  - GitHub Version Control với nhánh chuẩn và quy trình commit rõ ràng.  
  - Peer Review & Pull Request đảm bảo chất lượng code và tuân thủ coding standards.
  - Automated Test & QA gồm unit test, integration test, security scan chạy tự động mỗi lần push.  
  - Multi-stage Deployment (Dev → QA → Pre-Prod → Prod) với kiểm soát approval và rollback rõ ràng. 
- Quy trình này giúp tôi hình dung chính xác pipeline CI/CD chuẩn đang được áp dụng trong các dự án.

#### 3. Infrastructure as Code (IaC)
- Các kien thức IaC :  
  - **AWS CloudFormation**: Template-based provisioning, quản lý stacks. Hỗ trợ drift detection giúp phát hiện thay đổi ngoài IaC.  
  - **AWS CDK (Cloud Development Kit)**: IaC bằng lập trình. Reusable constructs, patterns, library hỗ trợ tốt cho microservices.  
  - **Demo**: Triển khai hạ tầng bằng CloudFormation và CDK để so sánh.  
  - **Discussion**: Khi nào dùng CloudFormation và khi nào dùng CDK  
  

#### 4. Monitoring & Observability
- Ví dụ thực tế với **Amazon CloudWatch**giúp tôi thấy rõ cách xây dựng quan sát hệ thống: Logs tập trung, Metrics tùy chỉnh, Dashboards trực quan và Alarms phản ứng theo thời gian thực.  
- Minh họa phân tích lỗi và tracing bằng **AWS X-Ray** cho thấy cách theo dõi toàn bộ dòng chảy request :  
  - Service map để nhận diện các điểm phụ thuộc giữa microservices.  
  - Bottleneck analysis để tìm ra thành phần gây chậm hoặc lỗi.  
  - Request flow visualization giúp truy vết chính xác nguyên nhân sự cố.  
- Nhờ các demo này, tôi hiểu rõ giá trị của observability trong vận hành hệ thống hiện đại thay vì chỉ dừng lại ở việc xem log thủ công như trước đây.



---

### Trải nghiệm và bài học cá nhân
- **Pipeline Workflow của anh Kha**: Giúp tôi hiểu rõ cách một CI/CD pipeline hoạt động ngoài đời thực — từ commit, review, test đến deploy — và cách áp dụng vào quy trình dự án của team.  
- **Workshop DevOps on AWS**: Giúp tôi kết nối lý thuyết với thực hành thông qua việc trực tiếp quan sát CodePipeline, CodeBuild, CodeDeploy hoạt động liền mạch trong một quy trình tự động hóa hoàn chỉnh.  
- **CloudWatch & X-Ray**: Lần đầu tôi thấy rõ cách theo dõi hiệu năng end-to-end, xác định bottleneck và tìm root cause của sự cố mà không cần dò log thủ công. Điều này thay đổi hoàn toàn cách tôi tiếp cận troubleshooting.  
- **Tư duy DevOps**: Tôi học được cách tối ưu hóa quy trình làm việc bằng tự động hóa, tăng tính cộng tác trong team và rút ngắn feedback-loop để nâng cao chất lượng sản phẩm.  
---

### Kết quả đạt được
- Hiểu vững DevOps mindset và nắm được bức tranh tổng thể của quy trình CI/CD, từ kiểm soát mã nguồn đến triển khai đa môi trường.
- Có thể tự thiết kế và xây dựng một pipeline chuẩn, dựa trên mô hình đã được minh họa trong workshop, để áp dụng trực tiếp vào dự án nhóm.
- Sử dụng thành thạo CloudWatch và X-Ray để theo dõi hệ thống, phân tích lỗi, xác định bottleneck và tối ưu hiệu năng dịch vụ.  
- Trang bị nền tảng kiến thức và tư duy đúng hướng để tiếp tục phát triển chuyên sâu trong vai trò DevOps Engineer hoặc Cloud Engineer.  

---

### Hình ảnh tại sự kiện
![IoT Weather Station Architecture](/images/4-EventParticipated/event3_1.png)
![IoT Weather Station Architecture](/images/4-EventParticipated/event3_2.png)
