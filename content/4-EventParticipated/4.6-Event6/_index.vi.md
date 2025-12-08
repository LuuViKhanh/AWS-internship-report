---
title: "Event 6"
weight: 1
chapter: false
pre: " <b> 4.6. </b> "
---

## Báo cáo sự kiện BUILDING AGENTIC AI: Context Optimization with Amazon Bedrock

### Mục đích của sự kiện
- Workshop được tổ chức nhằm giúp người tham dự hiểu sâu về **Agentic AI** và cách xây dựng các **AI agents** thông minh trên **Amazon Bedrock**. Sự kiện tập trung vào việc tối ưu hóa **context** và xây dựng **agentic workflows** trong môi trường thực tế. Các mục tiêu chính:
  - Hiểu rõ khái niệm **Agentic AI** và vai trò của nó trong hệ thống AI hiện đại.
  - Nắm vững kiến trúc và tính năng cốt lõi của **Amazon Bedrock Agent**.
  - Tìm hiểu các kỹ thuật **context optimization** để cải thiện hiệu suất AI agents.
  - Học cách xây dựng **agentic workflows** trên AWS services.
  - Thực hành hands-on với **CloudThinker orchestration framework**.

---

### Danh sách diễn giả & chủ đề chia sẻ
- **Kien Nguyen** – Solutions Architect  
  *Chủ đề: AWS Bedrock Agent Core*
  
- **Viet Pham** – Founder cum CEO (Diaflow)  
  *Chủ đề: [Use Case] Building Agentic Workflow on AWS*
  
- **Thang Ton** – Co-founder & COO (CloudThinker)  
  *Chủ đề: CloudThinker Introduction*
  
- **Henry Bui** – Head of Engineering (CloudThinker)  
  *Chủ đề: CloudThinker Agentic Orchestration, Context Optimization on Amazon Bedrock (L300)*
  
- **Kha Van** – CloudThinker Engineer  
  *Chủ đề: CloudThinker Hack: Hands-on Workshop*

---

### Nội dung nổi bật

#### 1. AWS Bedrock Agent Core
**Kien Nguyen** trình bày về kiến trúc và khả năng cốt lõi của **Amazon Bedrock**:
- **Agent capabilities**: Các tính năng chính của Bedrock agents trong việc xử lý tác vụ tự động.
- **Core concepts**: 
  - **Foundation Models (FMs)** và cách tích hợp với agents
  - **Agent architecture** và workflow execution
  - **Action groups** và **knowledge bases**
- **Key features**:
  - **Multi-step reasoning** và **task decomposition**
  - **Tool integration** và **API orchestration**
  - **Memory management** và **context handling**
- Cách xây dựng AI agents có khả năng tự động hóa quy trình phức tạp trên AWS.

#### 2. Building Agentic Workflow on AWS - Use Case thực tế
**Viet Pham** (CEO Diaflow) chia sẻ case study thực tế:
- Giới thiệu về **Diaflow** và bài toán kinh doanh cần giải quyết.
- **Agentic workflow implementation**:
  - Thiết kế workflow với nhiều agents phối hợp
  - Tích hợp với các AWS services (Lambda, Step Functions, DynamoDB)
  - **Event-driven architecture** cho real-time processing
- **Challenges & Solutions**:
  - Xử lý **context switching** giữa các agents
  - Đảm bảo **consistency** và **reliability**
  - **Cost optimization** khi sử dụng Foundation Models
- Kết quả đạt được và bài học kinh nghiệm từ production deployment.

#### 3. CloudThinker Introduction
- Được giới thiệu về **CloudThinker platform**:
- Tổng quan về **CloudThinker** - nền tảng **AI orchestration**.
- **Product vision**: Đơn giản hóa việc xây dựng và quản lý AI agents.
- **Core capabilities**:
  - **Agent orchestration** và **workflow management**
  - **Context optimization engine**
  - **Multi-model support** và **model routing**
- Vị trí của CloudThinker trong ecosystem AI/ML trên AWS.

#### 4. CloudThinker Agentic Orchestration & Context Optimization (L300)
**Henry Bui** trình bày technical deep-dive (Level 300):
- **Orchestration Framework**:
  - **Agent coordination patterns** và **communication protocols**
  - **State management** trong multi-agent systems
  - **Error handling** và **retry mechanisms**
  
- **Context Optimization Techniques**:
  - **Context window management**: Tối ưu hóa token usage
  - **Semantic chunking** và **relevance scoring**
  - **Dynamic context injection**: Chỉ đưa thông tin cần thiết vào prompt
  - **Context caching strategies** để giảm latency và cost
  
- **Performance Optimization**:
  - **Prompt engineering** best practices
  - **Model selection** dựa trên task complexity
  - **Parallel execution** và **batch processing**
  - **Monitoring & observability** với CloudWatch và X-Ray

- **Integration with Amazon Bedrock**:
  - Sử dụng **Bedrock APIs** hiệu quả
  - **Knowledge base integration** cho RAG (Retrieval-Augmented Generation)
  - **Guardrails** và **safety controls**

#### 5. CloudThinker Hack: Hands-on Workshop
**Kha Van** hướng dẫn workshop thực hành tập trung vào hai vấn đề chính:

- **Kết nối với AWS**:
  - Thiết lập tài khoản **CloudThinker** và kết nối với AWS services
  - Upgrade tài khoản
  
  
- **Tối ưu hóa chi phí (Cost Optimization)**:
  - Phân tích các **services** đã sử dụng 
  - Tính toán chi phí phát sinh
  - Best practices để **minimize costs** 

---

### Trải nghiệm và bài học cá nhân

- **Học hỏi từ chuyên gia AI/ML**:
  - Hiểu rõ cách **Amazon Bedrock** hoạt động và các use cases thực tế.
  - Các kỹ thuật **context optimization** rất hữu ích cho việc giảm cost và tăng performance.
  - **CloudThinker framework** cung cấp abstraction layer giúp đơn giản hóa việc xây dựng agents.

- **Trải nghiệm kỹ thuật**:
  - Thực hành tối ưu chi phí với cloudthinker.
  

- **Insights từ use case thực tế**:
  - Case study của **Diaflow** cho thấy challenges thực tế khi deploy agentic AI.
  - Tầm quan trọng của **context management** trong việc đảm bảo agent quality.
  - **Cost optimization** là yếu tố quan trọng khi scale AI applications.

---

### Kết quả đạt được

- Hiểu rõ khái niệm **Agentic AI** và cách xây dựng AI agents trên **Amazon Bedrock**.
- Nắm vững kiến trúc và core features của **Bedrock Agent framework**.
- Học được các kỹ thuật **context optimization** để cải thiện performance và giảm cost:
- Hiểu cách xây dựng **agentic workflows** với multiple agents coordination.
- Có kinh nghiệm hands-on kết nối AWS và cấu hình **CloudThinke**.
- Nắm được các kỹ thuật **cost optimization** thực tế để giảm chi phí khi sử dụng AI services.
- Học hỏi từ real-world use case về challenges và solutions khi deploy AI agents.

---

### Hình ảnh tại sự kiện
![Building Agentic AI Event](/images/4-EventParticipated/event6_1.png) 
![Building Agentic AI Event](/images/4-EventParticipated/event6_2.png)
![Building Agentic AI Event](/images/4-EventParticipated/event6_3.png)
