---
title: "Blog 3"
date: 2025-09-09
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---



# **Tăng cường bảo mật lưu trữ đám mây AWS của bạn với Superna Defender**

Bởi **Andrew Peng** và **Andrew MacKay** | Ngày 7 tháng 7 năm 2025 | trong **Amazon FSx**, **Amazon FSx for Windows File Server**, **Amazon Simple Storage Service (S3)**, **AWS Marketplace**, **Partner solutions**, **Software**, **Storage**

*By **Andrew MacKay**, **CTO and Strategy Officer** – **Superna***  
*By **Andrew Peng**, **Sr. Specialist SA**, **FSx for Windows File Server** – **AWS***

![Superna Logo](/images/3-BlogsTranslated/blog3/1.png)
![Superna Logo](/images/3-BlogsTranslated/blog3/2.png)
## **Giới thiệu**

Khi khách hàng di chuyển lưu trữ vào **Amazon Web Services (AWS)**, việc bảo vệ lưu trữ tệp và đối tượng trên đám mây là một mối quan tâm về bảo mật. Hiểu và triển khai một khung lưu trữ bao gồm các biện pháp bảo mật mạnh mẽ là rất quan trọng để bảo vệ dữ liệu khỏi **ransomware**, truy cập trái phép và rò rỉ dữ liệu. Các tổ chức liên tục tìm kiếm một giải pháp có thể cung cấp khả năng bảo vệ và giám sát lưu trữ dựa trên đám mây của họ.

Trong bài viết này, chúng ta sẽ khám phá cách **Superna Defender** có thể giúp giám sát và bảo vệ tài nguyên lưu trữ **AWS** ở cấp độ đối tượng hoặc tệp trong thời gian thực, bằng cách cung cấp thông tin "**ai, cái gì và ở đâu**" của mọi sự kiện. **Superna Defender** có thể cung cấp một giải pháp giúp duy trì sự phù hợp với các tiêu chuẩn **Cyberstorage** cho lưu trữ tệp và đối tượng, đồng thời cũng có thể giúp bảo vệ, giám sát và khôi phục hệ thống lưu trữ.

## **Các mối đe dọa malware và ransomware đối với lưu trữ**

Mối đe dọa của **ransomware** và **phần mềm độc hại** đối với lưu trữ đám mây ngày càng trở nên phức tạp và tinh vi. Các thiết bị đầu cuối bị ảnh hưởng với quyền truy cập hợp lệ vào các chia sẻ mạng có thể mở ra một bề mặt tấn công lớn. Mất dữ liệu, **ransomware** và rò rỉ dữ liệu có thể xảy ra nếu các **bucket Amazon Simple Storage Service (Amazon S3)** bị cấu hình sai chính sách bảo mật hoặc các thiết bị bị nhiễm truy cập vào chia sẻ **Amazon FSx for Windows File Server**.

Thiệt hại từ **ransomware** vượt xa những tổn thất hoạt động và dữ liệu ngay lập tức; nó ảnh hưởng nghiêm trọng đến danh tiếng lâu dài. Việc một công ty không bảo vệ được dữ liệu khách hàng có thể làm xói mòn niềm tin, gây mất khách hàng và ảnh hưởng đến việc thu hút kinh doanh mới.

## **Tiến xa hơn lưu trữ đám mây để hướng tới Cyberstorage**

Các sự kiện **phần mềm độc hại** tiếp tục là mối đe dọa thường trực—**ransomware**, **zero-day exploits** và các mối đe dọa truy cập ngoài ý muốn đang rình rập khắp nơi. Mặc dù đã có các phương pháp và công cụ sao lưu truyền thống, các tổ chức vẫn trở thành nạn nhân. Đây chính là lúc khái niệm **Cyberstorage** xuất hiện.

**Gartner** đã tạo ra một danh mục mới gọi là **Cyberstorage** để phân loại các sản phẩm chủ động bảo vệ lưu trữ và dữ liệu chống lại các sự kiện mạng thông qua phòng ngừa, phát hiện sớm và chặn sự kiện. **Superna** đã được công nhận là một nhà lãnh đạo trong danh mục này, xuất hiện trong các báo cáo chu kỳ công nghệ của **Gartner** về lưu trữ dữ liệu phi cấu trúc và bảo vệ điểm cuối.

Các tổ chức dựa vào nhiều công cụ bảo mật khác nhau từ bảo vệ điểm cuối, tường lửa, quản lý truy cập danh tính và phát hiện mối đe dọa. Họ cũng triển khai các chiến lược quản lý dữ liệu như **backups**, **snapshots** và tính năng **bất biến**. Nhưng với **Cyberstorage**, bảo mật có thể được nâng lên một bước xa hơn.

Khi một sự kiện mạng xảy ra, giải pháp của **Superna** có thể phát hiện các mối đe dọa theo thời gian thực trên **Amazon S3** và **FSx for Windows File Server**, thậm chí dừng ngay lập tức bằng cách cắt quyền truy cập của người dùng có nguy cơ. Các tệp bị ảnh hưởng trước tiên được cách ly, sau đó được khôi phục tự động. Cuối cùng, một bản ghi **kiểm toán** đầy đủ sẽ cung cấp thông tin "**ai, cái gì và ở đâu**" để hỗ trợ tuân thủ và điều tra **pháp y** sau sự cố.

## **Bối cảnh bảo mật phức tạp của Cyberstorage**

**Hình 1** minh họa cách khung **Cyberstorage** định nghĩa nhiều lớp cho một kiến trúc lưu trữ tổng thể.

*Hình 1: Superna Defender hoạt động tại lớp Dữ liệu (Data layer)*

![Cyberstorage Layers](/images/3-BlogsTranslated/blog3/3.png)

Hãy xem xét kế hoạch bảo mật doanh nghiệp điển hình bao gồm các thành phần như kiểm soát truy cập, **mã hóa**, giao thức bảo mật, **phần mềm chống virus**, **tường lửa** và ngăn ngừa mất dữ liệu. Chúng thường được bổ sung bởi **kiểm toán**, **kiểm thử xâm nhập**, cơ chế sao lưu và khôi phục, và thậm chí cả biện pháp an ninh vật lý như nhân viên bảo vệ và cửa khóa.

Mặc dù bối cảnh bảo mật này mạnh mẽ, nhưng cũng rất phức tạp. Một điểm yếu tại bất kỳ vị trí nào có thể dẫn đến hậu quả nghiêm trọng. Điều này đưa chúng ta đến một câu hỏi quan trọng: thường thì vấn đề không phải là "**nếu**" dữ liệu sẽ bị ảnh hưởng bởi một sự kiện mạng, mà là "**khi nào**". Hiệu quả của phản ứng của tổ chức là điều sống còn.

**Superna Defender** bảo vệ lưu trữ đối tượng và tệp của bạn tại **lớp Dữ liệu (Data Layer)**, cung cấp một "**tuyến phòng thủ cuối cùng**" nơi dữ liệu sản xuất tồn tại. Bằng cách tích hợp các khái niệm khung **Cyberstorage**, các tổ chức có thể củng cố tư thế bảo mật để đảm bảo rằng họ được trang bị tốt hơn để ngăn ngừa và ứng phó với truy cập ngoài ý muốn.

## **Tiêu chí cho danh sách kiểm tra Cyberstorage của NIST**

**Superna Defender** cũng có thể giúp khách hàng tuân thủ các điểm trong **National Institute of Standards and Technology (NIST) Cyberstorage Checklist**, như minh họa trong **Hình 2**.

*Hình 2: Danh sách kiểm tra Cyberstorage của NIST, một phần của Khung bảo mật mạng NIST*

![NIST Cyberstorage Checklist](/images/3-BlogsTranslated/blog3/4.png)

### **Identify (Xác định)**
Để phản ứng với hoạt động đáng ngờ, khách hàng có thể sử dụng mô hình **an ninh mạng** của **NIST** kết hợp với các kiểm soát và quy tắc riêng cho tài khoản người dùng và máy.

### **Detect (Phát hiện)**
Sử dụng **machine learning**, sản phẩm này giám sát **Cyberstorage** của khách hàng, phát hiện hoạt động đáng ngờ và tạo cảnh báo và báo cáo tương thích với phần mềm bên thứ ba. Nó cũng cung cấp khả năng mô phỏng sự kiện để kiểm tra phản ứng sự cố và tích hợp công cụ bảo mật.

### **Protect (Bảo vệ)**
**Superna Defender** cung cấp khả năng bảo vệ chống lại **xóa hàng loạt**, **sao chép hàng loạt**, và cung cấp **ngăn ngừa mất dữ liệu (DLP)** cũng như phát hiện mẫu hoạt động tùy chỉnh thông qua **Active Auditor** dành cho **AWS storage**. Các sự kiện có thể được phân tích **pháp y** để cung cấp phân tích nguyên nhân gốc "**ai, cái gì và khi nào**" của các sự kiện **Cyberstorage**. 

Hoạt động đáng ngờ vượt quá giới hạn xác định có thể kích hoạt tự động khóa tài khoản người dùng để đảm bảo an ninh ngay lập tức hoặc cảnh báo quản trị viên lưu trữ hoặc nhóm bảo mật để xem xét thủ công nhằm ngăn ngừa gián đoạn kinh doanh không cần thiết từ các **dương tính giả** tiềm ẩn. **Chế độ học (Learning mode)** tránh **dương tính giả** và tự động cấu hình dựa trên việc quan sát hoạt động.

### **Respond (Phản ứng)**
Bảng điều khiển trung tâm và cảnh báo, được hỗ trợ bởi **webhooks**, **Zero Trust API**, và tích hợp với **ServiceNow**, **Splunk**, **Palo Alto Networks**, và **AWS Security Hub**, cung cấp khả năng giám sát, báo cáo và phản ứng sự cố liền mạch. Việc tự động vô hiệu hóa tài khoản người dùng, khóa **API** và **token truy cập** có thể giảm thiểu tác động của một sự cố **Cyberstorage**. Tích hợp với bảo vệ điểm cuối có thể mở rộng phản ứng bao gồm cách ly mạng máy chủ để giảm tác động và sự lây lan.

### **Recover (Khôi phục)**
**Cyber Recovery Manager** cung cấp khôi phục thông qua phân tích một sự kiện mạng để xác định khi nào sự kiện đã xảy ra, và theo dõi tệp nào đã bị ảnh hưởng. Thông tin này cho phép khôi phục chính xác, chỉ khôi phục các tệp bị ảnh hưởng trong khi giữ nguyên các tệp khác, từ đó rút ngắn thời gian khôi phục và tăng năng suất. 

Hệ thống giám sát tiên tiến theo dõi hoạt động của người dùng trong thời gian thực và lịch sử để tăng tốc và cải thiện độ chính xác điều tra sự cố. Người dùng có thể ngay lập tức xem thông tin liên quan đến sự cố để hiểu điều gì đã xảy ra và người dùng nào có liên quan. Người dùng cũng có thể xem lại các tệp bị ảnh hưởng và ưu tiên khôi phục những tệp nào trước.

## **Tổng quan kiến trúc của Superna Defender trong AWS**

**Superna Defender** là một **native AWS Marketplace deployment** và tận dụng một số dịch vụ **AWS** như minh họa trong **Hình 3**. Các dịch vụ này chạy một công cụ xử lý sự kiện theo thời gian thực trong mô hình tiêu dùng **pay-as-you-go**, có thể dừng và khởi động lại theo yêu cầu. Giải pháp này sử dụng **Amazon EC2 Auto Scaling**, **VPCs**, và **security rules** để giám sát và bảo vệ lưu trữ **Amazon S3** và **Amazon FSx for Windows File Server**.

*Hình 3: Sơ đồ kiến trúc Superna Defender*

![Superna Defender Architecture](/images/3-BlogsTranslated/blog3/5.png)

## **Kết luận**

**Superna Defender**, tích hợp **AWS** và **Khung Cyberstorage của NIST**, cung cấp một giải pháp bảo mật lưu trữ tệp và đối tượng đám mây toàn diện cho khách hàng. **Superna Defender** sử dụng với **Amazon S3** hoặc **Amazon FSx for Windows File Server** có thể cung cấp **kiểm toán** và giám sát theo thời gian thực lưu trữ đối tượng và tệp trong **AWS**. Điều này cho phép khách hàng thấy "**ai, cái gì và ở đâu**" của các sự kiện hệ thống tệp, cho phép khôi phục dữ liệu chính xác theo thời điểm của dữ liệu bị ảnh hưởng.

Bắt đầu với **Superna Defender** trên **AWS Marketplace**, xem **video demo** của **Superna Defender**, và đọc báo cáo **Gartner Innovation Insight** về cách **Cyberstorage** giảm thiểu tác động của các cuộc tấn công mạng.

Khách hàng nên cân nhắc các dịch vụ họ chọn vì trách nhiệm của họ thay đổi tùy thuộc vào dịch vụ được sử dụng, tích hợp các dịch vụ đó vào môi trường **CNTT** của họ, và các luật và quy định áp dụng.

![Superna Partner Spotlight](/images/3-BlogsTranslated/blog3/6.png)

## **Kết nối với Superna**

### **Superna – AWS Partner Spotlight**
**Superna** cung cấp khả năng **kiểm toán** tệp và đối tượng phổ quát cùng giảm thiểu mối đe dọa cho môi trường **hybrid cloud** của bạn với nền tảng hội tụ điều phối và bảo mật.

**Contact Superna** | **Partner Overview** | **AWS Marketplace**

**TAGS:** **Amazon FSx**, **AWS Partner Solution**, **Cloud Storage Security**, **Storage**, **Superna**
