---
title: "Event 4"
weight: 1
chapter: false
pre: " <b> 4.4. </b> "
---

## Báo cáo sự kiện chuyên đề về Edge Network Services

### Mục đích của sự kiện
- Workshop được tổ chức nhằm giúp người tham dự có cái nhìn toàn diện về cách tối ưu và bảo vệ hệ thống web thông qua các dịch vụ biên (edge services) của AWS. Các mục tiêu chính:
   - Hiểu thêm thách thức khi vận hành ứng dụng Internet ở quy mô lớn.  
   - Giới thiệu cách Amazon CloudFront giải quyết vấn đề về hiệu năng, chi phí, và bảo mật. 
   - Tìm hiểu các tính năng cốt lõi của CloudFront và cơ chế hoạt động của nó.
   - Giới thiệu các dịch vụ bao mat như AWS WAF, AWS Shield, Bot Control.  
   - Thực hành hands-on tối ưu web app và bảo vệ ứng dụng Internet. 

---

### Danh sách diễn giả & chủ đề chia sẻ
####  FROM EDGE TO ORIGIN: CloudFront as Your Foundation
- **Nguyen Gia Hung** –  Head of Solutions Architect Amazon Web Services Viet Nam

#### Defense from public threat: AWS WAF & Application Protection
- **Julian Lu** –Sr. Edge Specialist Solutions Architect at Amazon Web Services (AWS)



---

### Nội dung nổi bật
#### 1. Thách thức khi vận hành ứng dụng Internet
Workshop mở đầu bằng việc phân tích các vấn đề phổ biến mà doanh nghiệp thường gặp:
- Độ trễ cao (latency) do người dùng ở xa origin server.
- Tải lớn lên hệ thống backend dẫn đến chi phí tăng cao.
- Tấn công từ internet như DDoS, bot traffic, injection, scraping.
- Khó mở rộng (scalability) khi lượng truy cập tăng đột biến.
- Thiếu lớp phòng thủ biên, khiến origin dễ bị lộ và tấn công trực tiếp.

#### 2. CloudFront – Giải pháp nền tảng “From Edge to Origin”
- Diễn giả trình bày cách CloudFront giúp cải thiện hệ thống:  
  - Caching để giảm tải cho origin.
  - Global Edge Network giúp người dùng truy cập từ vị trí gần nhất → tăng performance.
  - Security at Edge với WAF, Shield, Bot Control tại biên.
  - Cost Optimization nhờ giảm request trực tiếp về origin.
  - Resiliency & Availability do phân tán toàn cầu và cơ chế failover.

#### 3. CloudFront hoạt động như thế nào
- Một mô hình kiến trúc đơn giản được trình bày:  
  1. Người dùng gửi request → đi đến Edge Location gần nhất. 
  2. CloudFront kiểm tra cached content. 
  3. Nếu không có → request được chuyển về origin.  
  4. Edge cache nội dung để phục vụ các request tiếp theo.  
  => Quy trình này giúp vừa tăng tốc độ vừa giảm chi phí và tăng độ bảo vệ.

#### 4. Bảo vệ ứng dụng khỏi các mối đe dọa
- **AWS WAF – Web Application Firewall**:
  - Lọc và chặn các kiểu tấn công phổ biến: SQL injection, XSS, unauthorized access…
  - Có thể cấu hình rules, rule groups, managed rules.
  - Hoạt động ngay trên CloudFront → bảo vệ ở lớp biên, giảm gánh nặng cho origin.
- **AWS WAF Bot Control**:
  - Nhận diện bot, phân biệt bot tốt vs bot xấu.
  - Chặn scraping, brute force, bad automated traffic.
  - Giảm tải và tăng độ an toàn cho hệ thống.
- **AWS Shield**:
  - Bảo vệ chống DDoS ở nhiều cấp độ.
  - Shield Standard (miễn phí) luôn bật cho CloudFront.
  - Shield Advanced hỗ trợ monitor, incident response, và chi phí bảo vệ tối ưu.


---

### Trải nghiệm và bài học cá nhân
- **Học hỏi từ chuyên gia AWS**:
  -Diễn giả chia sẻ những khó khắn, thách thức trong triển khai hệ thống lớn và quản trị traffic.
  - Các kiến thức về caching, bảo mật lớp biên, và tối ưu hiệu suất được giải thích rất dễ hiểu.
- **Trải nghiệm kỹ thuật**:
  - Phân tích sơ đồ kiến trúc thật và mô phỏng quá trình xử lý request của CloudFront.
  - Tìm hiểu cách xây dựng WAF rules và cơ chế Bot Control.
  - Hiểu rõ cách CloudFront kết hợp với Shield để ngăn ngừa DDoS.
- **Hands-on Workshop**:
  - **Optimize Internet Web Application**:
      - Cấu hình CloudFront, thiết lập caching policies, kiểm tra latency improvements.
  - **Secure Internet Web Application**:
      - Tạo và áp dụng WAF rules.
      - Quan sát bot traffic và tạo rule chặn.
      - Tích hợp CloudFront + WAF + Shield.
---

### Kết quả đạt được
- Hiểu thêm vai trò quan trọng của edge layer trong kiến trúc ứng dụng Internet hiện đại — không chỉ để tăng tốc độ phân phối nội dung mà còn để tạo thành một lớp phòng thủ hiệu quả.
- Có thể giải thích và triển khai mô hình kiến trúc trong đó CloudFront đóng vai trò entry point cho mọi web application, giúp tối ưu performance và tăng mức độ an toàn.
- Hiểu thêm cách AWS Shield hoạt động và áp dụng hiệu quả để bảo vệ ứng dụng khỏi các loại tấn công DDoS mà không cần cấu hình phức tạp. 
- Nắm được cơ chế phối hợp giữa CloudFront – WAF – Shield để tạo thành một lớp phòng thủ toàn diện, resilient và tiết kiệm chi phí.  

---

### Hình ảnh tại sự kiện
![IoT Weather Station Architecture](/images/4-EventParticipated/event4_1.png)
![IoT Weather Station Architecture](/images/4-EventParticipated/event4_2.png)