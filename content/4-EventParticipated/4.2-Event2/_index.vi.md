---
title: "Event 2"
date: 2025-09-09
weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---



# Bài thu hoạch “AWS Cloud Mastery Series #1 - AI/ML/GenAI on AWS – Generative AI with Amazon Bedrock”

### Mục Đích Của Sự Kiện

- Giới thiệu tổng quan về hệ sinh thái AI/ML/GenAI của AWS.
- Khái quát về Managed AI Services trên AWS, công dụng, và mô hình giá.
- Nắm được kỹ thuật Prompt Engineering áp dụng vào các use case thực tế.
- Tìm hiểu kiến trúc Retrieval-Augmented Generation (RAG)
- Giới thiệu foundation Models và các loại Foundation Models (FMs) phổ biến

### Danh Sách Diễn Giả

- **Lam Tuan Kiet** – Sr DevOps Engineer, FPT Software  
- **Danh Hoang Hieu Nghi** – AI Engineer, Renova Cloud  
- **Dinh Le Hoang Anh** – Cloud Engineer Trainee, First Cloud AI Journey  

### Nội Dung Nổi Bật

#### Generative AI với Amazon Bedrock

- Giới thiệu các Foundation Models phổ biến (Claude, Llama, Titan) và tiêu chí lựa chọn theo bài toán: phân tích văn bản, chatbot, reasoning, sáng tạo nội dung, embedding.
- Thực hành các **Prompting Techniques**:  
  - **Zero-shot:** mô hình trả lời trực tiếp không cần ví dụ → phù hợp cho câu hỏi đơn giản.  
  - **Few-shot:** cung cấp ví dụ mẫu để mô hình học pattern → tăng độ chính xác trong các tác vụ chuyên biệt. 
  - **Chain-of-Thought (CoT):** yêu cầu mô hình suy luận từng bước → cải thiện các bài toán logic, phân tích dữ liệu, reasoning.  
- **RAG (Retrieval-Augmented Generation):** kết hợp LLM với dữ liệu doanh nghiệp (S3, DynamoDB, Aurora…) để giảm hallucination, tạo câu trả lời chính xác theo ngữ cảnh.  
- **Bedrock Agents:** xây dựng workflow đa bước (multi-step), gọi API, truy cập dữ liệu, tự động hóa process mà không cần viết backend phức tạp. 
- **Guardrails:** thiết lập chính sách an toàn nội dung (lọc toxic, hạn chế chủ đề, regex filtering, schema bắt buộc) để AI tuân thủ chuẩn doanh nghiệp.  
#### Managed AI Services trên AWS
- **Rekognition**: phân tích hình ảnh/video (detect objects, faces, text, moderation).
- **Transcribe:** chuyển giọng nói thành văn bản, phù hợp cho call center và caption.
- **Polly:** tạo giọng nói tự nhiên từ văn bản.
- **Comprehend**: phân tích ngôn ngữ tự nhiên (sentiment, key phrases, PII detection).
- **Translate:** dịch máy theo thời gian thực hoặc batch.
- **Textract:** trích xuất dữ liệu từ tài liệu scan/PDF.
- **Personalize**: xây dựng hệ thống gợi ý như Netflix/Amazon.




#### Mini Kahoot Review
- Mini quiz giúp củng cố kiến thức về **prompting techniques** (zero-shot, few-shot, CoT, structured output) thông qua các câu hỏi tình huống.
- Tăng mức độ tương tác và tạo không khí sôi nổi, giúp học viên nắm nội dung dễ hơn so với lý thuyết thuần túy.





---

### Trải nghiệm và bài học cá nhân
- **Prompting Techniques:** Ấn tượng nhất với các kỹ thuật **zero-shot, few-shot, CoT**, giúp tôi hiểu rõ cách triển khai GenAI trong các dự án thực tế.  
- **Hands-on Demo với Bedrock:** Giúp hình dung quy trình xây dựng và triển khai AI end-to-end.  
- **Mini Khoot:** Củng cố kiến thức ngay tại chỗ, giúp nhớ lâu hơn về các bước quan trọng và kỹ thuật prompt.  
- **Networking:** Kết nối với cộng đồng AWS và học hỏi từ các chuyên gia trong nước, mở rộng cơ hội hợp tác.  

### Trải nghiệm trong event

Tham dự workshop **“AI/ML/GenAI on AWS – Generative AI with Amazon Bedrock”** là một trải nghiệm cực kỳ giá trị, giúp tôi có cái nhìn hệ thống về cách xây dựng và triển khai các giải pháp GenAI trên nền AWS. Một vài điểm nổi bật mà tôi thu được::

#### Học hỏi từ các chuyên gia **AWS**
- Các diễn giả từ AWS đã chia sẻ nhiều góc nhìn thực tế về việc lựa chọn Foundation Model, thiết kế kiến trúc RAG và vận hành GenAI trong doanh nghiệp.
- Những ví dụ minh họa rõ ràng giúp tôi hiểu hơn cách áp dụng GenAI vào các bài toán thực tiễn như phân tích tài liệu, tạo chatbot, hay tự động hóa nghiệp vụ.

#### Khám phá công cụ & dịch vụ AWS
- Trải nghiệm trực tiếp với Amazon Bedrock và Guardrails giúp tôi hiểu rõ cách AWS hỗ trợ triển khai GenAI an toàn và hiệu quả.
- Tôi cũng học được cách tận dụng các dịch vụ AI có sẵn như Rekognition, Comprehend, Transcribe hoặc Textract để giải quyết nhanh các nhu cầu về thị giác máy tính và NLP.

#### Kết nối và trao đổi
- Workshop là cơ hội tốt để trao đổi với cộng đồng sử dụng AWS, cũng như lắng nghe các kinh nghiệm thực chiến từ những đội đã triển khai GenAI.


#### Bài học rút ra
-Sử dụng RAG, Bedrock Agents và Prompting Techniques giúp giảm dependency, tăng tính mở rộng (scalability) và độ bền (resilience) cho giải pháp GenAI.
- Các Managed AI Services và công cụ như Amazon Bedrock có thể tăng năng suất phát triển.

#### Một số hình ảnh khi tham gia sự kiện
![IoT Weather Station Architecture](/images/4-EventParticipated/event2_1.png)
![IoT Weather Station Architecture](/images/4-EventParticipated/event2_2.png)
![IoT Weather Station Architecture](/images/4-EventParticipated/event2_3.png)
