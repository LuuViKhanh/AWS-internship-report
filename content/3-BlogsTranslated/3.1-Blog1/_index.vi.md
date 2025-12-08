---
title: "Blog 1"
date: 2025-09-09
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---


# **Đánh Giá Khả Năng Phục Hồi (Resilience Assessment) Ứng Dụng Tập Trung Đa Tài Khoản Sử Dụng AWS Resilience Hub**

Bởi tác giả Venkata Kommuri, Venkata Moparthi, Santosh Vallurupalli, và Tracy Honeycutt | Ngày 05 tháng 08 năm 2025 | trong Management Tools

## **Giới thiệu**

Khi các tổ chức mở rộng môi trường điện toán đám mây của họ trên nhiều tài khoản và khu vực **AWS**, việc quản lý và truy cập **resilience** trở nên ngày càng phức tạp. Các phương pháp truyền thống trong việc đánh giá **resilience** riêng biệt cho từng **workload**, tài khoản hoặc khu vực có thể dẫn đến sự kém hiệu quả, thiếu nhất quán và tạo ra các khoảng trống trong phạm vi bao phủ. Thách thức này đặc biệt rõ ràng trong các kiến trúc phân tán sử dụng nhiều công cụ **Infrastructure as Code (IaC)** như **AWS CloudFormation** và **Terraform**.

**AWS Resilience Hub** giải quyết những thách thức này bằng cách cung cấp một dịch vụ được quản lý tập trung để giám sát và đánh giá **resilience** trên các kiến trúc đám mây đa tài khoản. Dịch vụ này cho phép các tổ chức xác định, theo dõi và tăng cường **resilience** của ứng dụng thông qua việc giám sát thống nhất trong một **centralized hub master account**. Việc tích hợp với **Amazon Simple Notification System (SNS)** mang lại khả năng phát hiện **drift** theo thời gian thực, giúp duy trì năng lực khôi phục mạnh mẽ trên các triển khai phân tán, đồng thời hỗ trợ các yêu cầu về độ trễ thấp, tuân thủ vị trí lưu trữ dữ liệu, và tăng cường **resilience** trước các sự cố gián đoạn.

## **Tìm hiểu AWS Resilience Hub**

**AWS Resilience Hub** là một vị trí trung tâm trong bảng điều khiển **AWS (AWS console)** giúp bạn quản lý và cải thiện tư thế phục hồi (**resilience posture**) của các ứng dụng trên **AWS**. **AWS Resilience Hub** cho phép bạn xác định mục tiêu phục hồi, đánh giá tư thế phục hồi của mình so với các mục tiêu đó và triển khai các khuyến nghị cải thiện dựa trên **AWS Well-Architected Framework**.

Khả năng phục hồi được định nghĩa bằng các chỉ số gọi là **RTO (Recovery Time Objective)** và **RPO (Recovery Point Objective)**. **RTO** là thước đo thời gian mà ứng dụng có thể khôi phục sau một sự cố ngừng hoạt động và **RPO** là thước đo lượng dữ liệu tối đa mà ứng dụng có thể chịu mất mát. **AWS Resilience Hub** cung cấp cái nhìn thống nhất về tư thế phục hồi của ứng dụng, xác định các rủi ro tiềm ẩn và đưa ra các khuyến nghị có thể hành động để tăng cường khả năng chống chịu trước sự gián đoạn. Bằng cách căn chỉnh với các thực tiễn tốt nhất của **AWS Well-Architected Framework**, **Resilience Hub** đảm bảo rằng các ứng dụng có thể chịu đựng và phục hồi từ nhiều tình huống lỗi khác nhau.

## **Những thách thức với các đánh giá phục hồi phân tán (Disaggregated Resilience Assessments)**

Dưới đây là một số thách thức chính khi sử dụng phương pháp đánh giá **resilience** phân tán:

### **Resilience Evaluations bị phân mảnh**
Các tổ chức quản lý **workload** trên nhiều tài khoản **AWS** thường tiến hành các đánh giá **resilience** độc lập, dẫn đến sự thiếu nhất quán trong tiêu chí đánh giá và xác định rủi ro.
Không có cái nhìn thống nhất, các nhóm có thể gặp khó khăn trong việc liên kết các kết quả **resilience** giữa các **workload**, dẫn đến những "điểm mù" trong tổng thể **resilience** của ứng dụng.

### **Thiếu các Resilience Policies chuẩn hóa**
Khi không có các **Resilience Policies** tiêu chuẩn hóa, các nhóm khác nhau có thể định nghĩa mục tiêu khả dụng, **RTO** và **RPO** khác nhau.
Sự thiếu nhất quán này có thể dẫn đến việc không đồng bộ giữa kế hoạch liên tục kinh doanh và khả năng thực tế của hạ tầng đám mây.

### **Khó khăn trong việc tổng hợp dữ liệu**
Việc tổng hợp dữ liệu **resilience** từ nhiều nguồn khác nhau là một thách thức lớn khác. Không có nền tảng thống nhất, quản trị viên phải tổng hợp thủ công chi tiết của cơ sở hạ tầng được triển khai từ các công cụ như **AWS CloudFormation** hoặc các tệp **Terraform state** trên nhiều **Region** và **account**.
Quy trình thủ công này có thể tạo ra lỗi và chậm trễ, khiến việc xác định các điểm lỗi trải dài trên nhiều **accounts** trở nên khó khăn, kéo dài thời gian phơi nhiễm với các gián đoạn tiềm ẩn.

Trong bài viết này, chúng ta sẽ khám phá một kiến trúc giúp giải quyết các thách thức được nêu ở trên. Kiến trúc này sẽ hỗ trợ bạn thực hiện các **resilience assessment** cho các ứng dụng được triển khai trên nhiều **AWS accounts** và **Regions**.

## **Điều kiện tiên quyết**

- Một tài khoản **AWS**
- Các mẫu **AWS CloudFormation** hoặc tệp **Terraform** định nghĩa ứng dụng của bạn
- Hướng dẫn **Recovery Time Objective (RTO)** và **Recovery Point Objective (RPO)** được xác định trước theo yêu cầu kinh doanh của bạn

## **Solution Architecture**

**AWS Resilience Hub Solution** sử dụng mô hình **hub and spoke** để cung cấp khả năng quản lý **resilience** tập trung trên toàn bộ môi trường **AWS**, giúp các tổ chức đánh giá và nâng cao **resilience** của ứng dụng một cách hiệu quả. Giải pháp này hoạt động thông qua một **central AWS hub account**, đóng vai trò là điểm quản trị trung tâm cho việc định nghĩa các **resilience policies**, quản lý các bài đánh giá, và giám sát các ứng dụng trên các **spoke account** được kết nối. Tài khoản **hub** kết nối đến nhiều **spoke account** thông qua **IAM roles** và **trust relationships**. Các **spoke account** này chứa các **workload** và tài nguyên cần được đánh giá **resilience**.

**AWS Resilience Hub** yêu cầu hai **IAM roles** để đảm bảo đánh giá **resilience** an toàn giữa các tài khoản. Vai trò chính **AWSResilienceHubAssessmentRole** trong **hub account** quản lý các hoạt động đánh giá, trong khi vai trò phụ **AWSResilienceHubCrossAccountRole** trong **spoke account** thực thi việc đánh giá **workload**. Vai trò đánh giá của **hub account** điều phối các đánh giá **resilience** bằng cách quản lý cấu hình, giả định các **cross-account role**, và phối hợp các hoạt động đánh giá **workload**.

Khách hàng có thể tận dụng khả năng **drift detection** của **AWS Resilience Hub** để tự động đánh giá các **workload** của họ hằng ngày. Việc đánh giá này diễn ra một lần mỗi 24 giờ. Để tăng cường giám sát và phản ứng, khách hàng có thể tích hợp kết quả đánh giá **drift detection** này với một **SNS topic**. Bằng cách này, các nhóm liên quan có thể đăng ký nhận thông báo, cho phép họ nhận cảnh báo kịp thời và thực hiện các hành động khắc phục nhanh chóng khi phát hiện sai lệch. Sự tích hợp này giúp xây dựng phương pháp tiếp cận chủ động trong việc duy trì **resilience** của ứng dụng và đảm bảo rằng mọi thay đổi ảnh hưởng đến tư thế **resilience** đều được xử lý nhanh chóng.

![AWS Resilience Hub Architecture](/images/3-BlogsTranslated/blog1/1.png)
*Hình 1 – Sơ đồ kiến trúc của giải pháp tập trung hóa việc đánh giá resilience của ứng dụng đa tài khoản bằng AWS Resilience Hub.*

## **Key Components of the Solution**

Dưới đây là các thành phần cấu thành giải pháp:

### **Central Hub Account**
Đóng vai trò là trung tâm quản trị cho **AWS Resilience Hub**, nơi quản trị viên có thể quản lý các chính sách **resilience**, xem kết quả đánh giá, và điều phối chiến lược **resilience** trên nhiều tài khoản và ứng dụng. Tài khoản này cũng bao gồm một **SNS topic** nhận thông báo **drift**, cung cấp cảnh báo theo thời gian thực cho người dùng đã đăng ký.

### **Spoke Accounts**
Chứa các **workload** và tài nguyên được **AWS Resilience Hub** đánh giá, kết nối đến **central hub account** thông qua **IAM roles** và **trust relationships** để cho phép đánh giá **resilience**.

### **IAM Roles**

#### **AWSResilienceHubAssessmentRole**
Nằm trong **central hub account**; quản lý cấu hình tổng thể, tạo các chính sách **resilience**, thiết lập ứng dụng để đánh giá, và giả định các **cross-account role** trong các **spoke account** để ủy quyền nhiệm vụ một cách an toàn.

#### **AWSResilienceHubCrossAccountRole**
Nằm trong **spoke account**; thực hiện đánh giá **workload**, thực thi các thao tác cấp tài nguyên, và báo cáo kết quả về **hub admin role**, đảm bảo việc đánh giá **resilience** chi tiết.

### **Trust Relationships**
Cho phép vai trò quản trị trong **hub account** ủy quyền nhiệm vụ cho vai trò thực thi trong **spoke account**, duy trì sự phân tách rõ ràng về trách nhiệm đồng thời tạo điều kiện cho việc quản lý và đánh giá **resilience** hiệu quả trên toàn bộ môi trường **AWS**.

## **Bắt đầu**

### **Tải về các tệp CloudFormation cần thiết**
```bash
wget \
https://d2908q01vomqb2.cloudfront.net/artifacts/MTBlog/cloudops-1962/ard.yaml \
https://d2908q01vomqb2.cloudfront.net/artifacts/MTBlog/cloudops-1962/AWSResilienceHubAssessmentRole.yaml \
https://d2908q01vomqb2.cloudfront.net/artifacts/MTBlog/cloudops-1962/AWSResilienceHubCrossAccountRole.yaml \
https://d2908q01vomqb2.cloudfront.net/artifacts/MTBlog/cloudops-1962/AWSResilienceHubSNSTopic.yaml
```

### **Triển khai các IAM Roles cho Central Hub Account và Spoke Accounts**

Trong **hub account**, chạy lệnh sau:
```bash
aws cloudformation create-stack \
--template-body AWSResilienceHubAssessmentRole.yaml \
--stack-name AWSResilienceHubAssessmentRole \
--capabilities CAPABILITY_IAM CAPABILITY_NAMED_IAM
```

Trong mỗi **spoke account**, chạy lệnh sau:
```bash
aws cloudformation create-stack \
--template-body AWSResilienceHubCrossAccountRole.yaml \
--stack-name AWSResilienceHubCrossAccountRole \
--capabilities CAPABILITY_IAM CAPABILITY_NAMED_IAM \
--parameter-overrides AWSResilienceHubAssessmentRoleARN=arn:aws:iam::<hubaccount_number>:role/AWSResilienceHubAssessmentRole
```

### **Tạo SNS topic để nhận thông báo khi ứng dụng phát hiện drift**

Mẫu **CloudFormation** này thiết lập một **SNS topic** cùng các quyền truy cập liên quan. Mẫu này cấu hình cả một **SNS topic** mới và tạo **Resource Policy** xác định các dịch vụ và người dùng nào có thể tương tác với **topic**. Cụ thể, cấu hình này cho phép **AWS Resilience Hub** gửi thông báo về kết quả đánh giá **drift detection** đến **SNS topic**, giúp giám sát các thay đổi trong **resilience policies** của bạn.

```bash
aws cloudformation create-stack \
--template-body AWSResilienceHubSNStopic.yaml \
--stack-name AWSResilienceHubSNSTopic \
--capabilities CAPABILITY_IAM CAPABILITY_NAMED_IAM \
--parameter-overrides TopicName=dev-sample-topic EmailAddress=<Enter_Email_Address_of_Recipeint>
```

### **Triển khai workload mẫu trong tài khoản Spoke**
```bash
aws cloudformation create-stack \
--template-body ard.yaml \
--stack-name resilience-hub-workloads \
--capabilities CAPABILITY_IAM CAPABILITY_NAMED_IAM
```

Sao chép **ARN** của **CloudFormation Stack** vừa được triển khai để sử dụng sau:
```bash
aws cloudformation describe-stacks --stack-name resilience-hub-workloads --query "Stacks[0].StackId" --output text
```

Để minh họa chức năng đánh giá **workload** giữa các tài khoản sử dụng **Resilience Hub**, chúng ta sẽ triển khai một **workload** mẫu trong **Spoke Account** và phân tích kết quả đánh giá của nó từ **Central Account**. Ứng dụng mẫu này có kiến trúc ba tầng với các dịch vụ được triển khai trong một **AZ** bất cứ khi nào có thể, bao gồm **Amazon CloudFront** cho việc phân phối và lưu trữ nội dung đệm, **Amazon Simple Storage Service (Amazon S3)** cho lưu trữ đối tượng, một **Amazon Elastic Compute Cloud (Amazon EC2)** instance đóng vai trò **web server**, và một **Amazon Relational Database Service (Amazon RDS)** instance cho hoạt động cơ sở dữ liệu. Mục tiêu chính của bài viết này là minh họa cách **Resilience Hub** đánh giá **resilience** của kiến trúc này và khám phá cách chúng ta có thể cải thiện nó dựa trên các khuyến nghị mà công cụ cung cấp. Lưu ý rằng kiến trúc mẫu này không tuân theo các thực hành tốt nhất của **AWS** và được sử dụng chỉ nhằm mục đích minh họa cách **AWS Resilience Hub** xác định các khoảng trống **resilience** và tạo khuyến nghị cải tiến.

![Three-tier Workload Architecture](/images/3-BlogsTranslated/blog1/2.png)

*Hình 2 - Sơ đồ kiến trúc của workload mẫu ba tầng*

## **Thiết Lập Resilience Assessment Tập Trung Trong Hub Account**

Để bắt đầu, đăng nhập vào tài khoản **AWS hub** và điều hướng đến **AWS Management Console**.

1. Chọn **AWS Resilience Hub** và chọn **Add application** → **Get started**, sau đó chọn **Add application**.

2. Chọn **Add Application** trong mục **Resilience management**.
![Add Application](/images/3-BlogsTranslated/blog1/3.png)


3. Nhập thông tin ứng dụng và chọn **Resource collection**.
![Resilience Management](/images/3-BlogsTranslated/blog1/4.png)


4. Thêm **ARN** của **AWS CloudFormation stack** của **workload** mẫu mà bạn đã sao chép từ Bước 3 (Deploy Sample Workload in Spoke Account).

![CloudFormation Stack ARN](/images/3-BlogsTranslated/blog1/5.png)

5. Xác định chính sách **resilience** mới cho **workload**. Với **workload** mẫu này, chúng ta sẽ đặt chính sách "**MissionCritical**" với **RTO** là 10 phút và **RPO** là 4 phút. Nếu bạn đã có các **Resiliency Policies** được định nghĩa sẵn trong tài khoản, bạn có thể chọn sử dụng chúng bằng cách đánh dấu vào tùy chọn "Choose an existing resiliency policy".

![Resilience Policy](/images/3-BlogsTranslated/blog1/6.png)

6. Đối với đánh giá đa tài khoản, chọn **AWSResilienceAssessmentRole** từ menu thả xuống và trong mục **Add cross account IAM role(s) ARN**, thêm **ARN** của **AWSResilienceCrossAccountRole** từ **Spoke Account(s)**.

   **Lưu ý:** Nếu triển khai **workload** trên nhiều **spoke accounts**, hãy thêm **ARN** của **AWSResilienceCrossAccountRole** từ từng **spoke account** để bật khả năng **resilience** giữa các tài khoản.

![Multi-Account Assessment](/images/3-BlogsTranslated/blog1/7.png)

7. Bằng cách chọn tùy chọn **Automatically assess daily**, bạn có thể thiết lập việc đánh giá tự động hằng ngày cho các **workload** được chỉ định trong **CloudFormation** và **Terraform templates**. Ngoài ra, bạn có thể nhận thông báo qua email thông qua **SNS topic** mà bạn đã đăng ký. Những thông báo này sẽ thông tin cho bạn về kết quả **drift detection assessment**, cảnh báo bạn về các thay đổi trong tư thế **resilience** của ứng dụng theo thời gian. Đánh dấu chọn "**Get Notified when the application drifts**" và chọn **SNS topic** đã được tạo trong Step 2.

![Daily Assessment Configuration](/images/3-BlogsTranslated/blog1/8.png)

8. Sau đó, chọn **Add application**.

![Add Application Button](/images/3-BlogsTranslated/blog1/9.png)

9. Khi ứng dụng được nhập thành công từ mẫu **AWS CloudFormation**, chọn **Publish application**.

![Publish Application](/images/3-BlogsTranslated/blog1/10.png)

10. Sau khi **publish**, ứng dụng của bạn đã sẵn sàng để được đánh giá.

## **Chạy một Resilience Assessment**

1. Đi đến tab **Resources** để xem các thành phần được triển khai từ mẫu **AWS CloudFormation** cho **workload** mẫu trong **Spoke Account**. Bây giờ, bạn có thể chọn **Assess application** để bắt đầu quá trình đánh giá.

![Resources Tab](/images/3-BlogsTranslated/blog1/11.png)

2. Đặt tên cho báo cáo đánh giá của bạn và chọn **Run**.

![Assessment Report Name](/images/3-BlogsTranslated/blog1/12.png)

3. Trạng thái đánh giá sẽ hiển thị là "**in progress**" và sẽ hoàn tất sau vài phút.

![Assessment In Progress](/images/3-BlogsTranslated/blog1/13.png)

## **Xem Xét Resilience Assessment**

Sau khi hoàn tất đánh giá, báo cáo sẽ được tạo để xem xét.

![Assessment Completed](/images/3-BlogsTranslated/blog1/14.png)

1. Bạn có thể tìm thấy các báo cáo đánh giá của ứng dụng trong phần **Assessments** của ứng dụng.
2. Trong menu điều hướng bên trái, chọn **Applications**.
3. Trong **Applications**, mở ứng dụng của bạn.
4. Trong tab **Assessments**, chọn một báo cáo từ phần **Resiliency assessments**.

Khi bạn mở báo cáo, bạn sẽ thấy:
- Tổng quan chung của báo cáo đánh giá
- Các khuyến nghị để cải thiện **resilience**
- Các khuyến nghị về thiết lập cảnh báo, **Standard Operating Procedures (SOPs)** và các bài kiểm thử

![Assessment Report Overview](/images/3-BlogsTranslated/blog1/15.png)

Khi xem xét báo cáo trên, bạn sẽ thấy phần "**Current Policy Compliance**" chỉ ra rằng cơ sở hạ tầng hiện tại chưa đáp ứng **RTO** và **RPO** được xác định trong chính sách **resilience** của bạn. Để khắc phục điều này, **AWS Resilience Hub** cung cấp các khuyến nghị hữu ích, cho phép bạn triển khai các biện pháp điều chỉnh và tăng cường **resilience** của ứng dụng để phù hợp với mục tiêu đã đặt ra. Ví dụ, khi chọn **RDS AppComponent**, bạn sẽ thấy một tập hợp chi tiết các khuyến nghị đánh giá, như minh họa trong hình dưới đây.

![Policy Compliance](/images/3-BlogsTranslated/blog1/16.png)



Với những khuyến nghị về **resilience** này, các nhóm ứng dụng và hạ tầng có thể thực hiện các thay đổi phù hợp cho hệ thống của họ, nâng cao khả năng chịu lỗi bất ngờ. Quy trình này thể hiện sức mạnh của chức năng **cross-account** trong **AWS Resilience Hub** – trong khi **workload** mẫu được triển khai trong **Spoke Account**, việc đánh giá được thực hiện trong **Central Hub Account**. Cách tiếp cận tập trung này cho phép các báo cáo đánh giá được tổng hợp tại **Central Hub Account**, mang lại cái nhìn toàn diện về **resilience** trên nhiều tài khoản và ứng dụng. Sự giám sát tập trung này giúp tổ chức duy trì tiêu chuẩn **resilience** nhất quán và quản lý hiệu quả các môi trường **AWS** đa tài khoản.

## **Kết Luận**

Giải pháp này mang lại phương pháp tiếp cận tập trung để đánh giá và cải thiện **resilience** của **workload** trên nhiều tài khoản và khu vực **AWS**, điều này rất quan trọng để duy trì tính liên tục của hoạt động kinh doanh và đáp ứng yêu cầu doanh nghiệp. Nó tích hợp liền mạch với các ứng dụng được triển khai thông qua **AWS CloudFormation** và **Terraform**, sử dụng mô hình **hub and spoke** cho phép các tổ chức đánh giá hiệu quả tư thế **resilience** trong khi vẫn duy trì bảo mật thông qua cơ chế kiểm soát truy cập dựa trên **IAM Role**. 

Khả năng đánh giá các **stack** được triển khai bên ngoài **AWS Region** của **Central Hub Account**, kết hợp với tích hợp **cross-account IAM roles**, nâng cao hiệu quả của dịch vụ bằng cách cho phép tổ chức có cái nhìn về các **workload** toàn cầu và đảm bảo các đánh giá an toàn, có thể mở rộng. 

Bằng cách áp dụng **AWS Resilience Hub**, các tổ chức có thể biến việc quản lý **resilience** từ một quy trình phản ứng thành một chiến lược chủ động, tận dụng các đánh giá tự động, khuyến nghị chi tiết và các chỉ số **resilience** rõ ràng để xây dựng các ứng dụng có khả năng chịu lỗi cao, sẵn sàng khôi phục, phù hợp với các thực hành tốt nhất về phục hồi sau thảm họa và **resilience** vận hành, biến nó thành công cụ thiết yếu để duy trì một môi trường **AWS** **resilient** và được thiết kế tốt khi cơ sở hạ tầng đám mây ngày càng phức tạp. 

Để bắt đầu triển khai giải pháp này trong tổ chức của bạn, hãy tải xuống các **CloudFormation templates** được cung cấp trong bài viết này và làm theo hướng dẫn triển khai từng bước trong tài liệu của **AWS Resilience Hub**. Bạn cũng có thể khám phá thêm các chiến lược đánh giá **resilience** khác thông qua **AWS Well-Architected Framework**.

## **Tiểu Sử Tác Giả**

**TAGS:** **AWS Resilience Hub**, **Resiliency**

### **Venkata Kommuri**
**Venkata Kommuri** là **Kiến trúc sư Hạ tầng (Infrastructure Architect)** tại **AWS**, chuyên thiết kế và triển khai các giải pháp đám mây phức tạp trong cả môi trường thương mại và **GovCloud**. Ông có chuyên môn sâu trong các lĩnh vực như di chuyển hệ thống lên đám mây (**cloud migration**), **container hóa**, **mạng (networking)** và triển khai **AI tạo sinh (Generative AI)**. Với khả năng xây dựng các kiến trúc doanh nghiệp có tính mở rộng và bảo mật cao, ông giúp thúc đẩy quá trình chuyển đổi số đồng thời duy trì hiệu quả vận hành vượt trội.
![Authors](/images/3-BlogsTranslated/blog1/17.png)
### **Venkata Moparthi**
**Venkata Moparthi** là **Kiến trúc sư Giải pháp Cấp cao (Senior Solutions Architect)** tại **AWS**, chuyên về di chuyển hệ thống lên đám mây, **AI tạo sinh** và khả năng phục hồi (**resilience**). Với vai trò là một nhà lãnh đạo công nghệ đáng tin cậy, ông thiết kế các giải pháp đám mây mang tính đột phá cho lĩnh vực dịch vụ tài chính và nhiều ngành công nghiệp khác, luôn mang lại kết quả tối ưu bằng cách kết hợp đổi mới kỹ thuật với mục tiêu kinh doanh.
![Authors](/images/3-BlogsTranslated/blog1/18.png)
### **Santosh Vallurupalli**
**Santosh Vallurupalli** là **Kiến trúc sư Hạ tầng Đám mây Cấp cao (Senior Cloud Infrastructure Architect)** trong nhóm **Dịch vụ Chuyên nghiệp AWS (AWS ProServ Team)**. Anh đam mê hỗ trợ người dùng trong hành trình chuyển đổi lên đám mây và xây dựng các giải pháp **Cloud Native** để giải quyết những thách thức phức tạp. **Santosh** có chuyên môn về **Mạng AWS** và **Container (EKS)**. Ngoài công việc, anh thích du lịch và xem lại bộ phim "The Office" nhiều lần.
![Authors](/images/3-BlogsTranslated/blog1/19.png)
### **Tracy Honeycutt**
**Tracy Honeycutt** là **Quản lý Kiến trúc Giải pháp (Solutions Architecture Manager)** tại Atlanta, bang Georgia. **Tracy** tập trung vào việc hỗ trợ các khách hàng trong ngành **Dịch vụ Tài chính (FSI)** trên hành trình lên đám mây của họ — từ tăng tốc quá trình di chuyển, hiện đại hóa khối lượng công việc, đến áp dụng các phương thức làm việc mới. Bà có chuyên môn đặc biệt trong lĩnh vực **mạng** và **DNS**, đồng thời rất đam mê giúp đỡ các khách hàng mới bắt đầu hành trình điện toán đám mây.
![Authors](/images/3-BlogsTranslated/blog1/20.png)
