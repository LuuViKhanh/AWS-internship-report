---
title: "Blog 2"
date: 2025-09-09
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---



# **Triển khai cầu nối USDC trên AWS**

Bởi **Corey Cooper** và **Guillaume Goutaudier** | ngày 09 tháng 6 năm 2025 | trong **Advanced (300)**, **AWS Step Functions**, **Blockchain**, **Technical How-to**

## **Giới thiệu**

**Stablecoin** mang lại những lợi thế đáng kể trong **crypto space**. Chúng cung cấp sự ổn định giá cả và có thể đóng vai trò như một phương tiện trao đổi đáng tin cậy, nơi lưu trữ giá trị hoặc cầu nối giữa hệ sinh thái **fiat** và **crypto**. Khả năng chuyển **stablecoin** trên nhiều **blockchain** khác nhau càng nâng cao tiện ích của chúng bằng cách cải thiện khả năng tương tác **chuỗi chéo** và cho phép người dùng tận dụng thế mạnh của các mạng lưới khác nhau.

**Circle** là một nền tảng tài chính cung cấp **stablecoin** được quản lý, quỹ được mã hóa, dịch vụ dành cho nhà phát triển và dịch vụ thanh khoản để giúp các doanh nghiệp triển khai tương lai của tài chính trên nhiều **blockchain**. **Circle** được biết đến rộng rãi với **stablecoin** đô la nổi bật của mình, **USDC**.

Với việc **Circle** gần đây phát hành dịch vụ khả năng tương tác của mình, **CCTP (Cross-Chain Transfer Protocol) V2**, chúng tôi muốn khám phá cách **USDC** có thể được chuyển giữa nhiều chuỗi bằng kiến trúc **serverless** trên **AWS**.

Trong bài viết này, chúng tôi mô tả và triển khai một kiến trúc như vậy. Chúng tôi tập trung vào các thành phần **backend**, sử dụng **Quickstart: Cross-Chain USDC Transfer** từ tài liệu dành cho nhà phát triển của **Circle** làm tham chiếu. Chúng tôi minh họa cách sử dụng các dịch vụ **serverless** của **AWS** như **AWS Lambda** và **AWS Step Functions** để triển khai các **workflow onchain**.

Giải pháp này đặc biệt có giá trị đối với các doanh nghiệp xây dựng nền tảng **DeFi** đa chuỗi, **marketplace NFT** hoặc hệ thống thanh toán xuyên biên giới. Bằng cách sử dụng các dịch vụ **serverless** của **AWS**, nhà phát triển có thể giảm độ phức tạp của hạ tầng, tăng tốc độ tích hợp các chuyển giao **chuỗi chéo**, đồng thời duy trì tính sẵn sàng cao và khả năng mở rộng với chi phí vận hành tối thiểu.

## **Tổng quan giải pháp**

Kiến trúc cấp cao của giải pháp được thể hiện trong sơ đồ sau.

![Architecture Overview](/images/3-BlogsTranslated/blog2/1.png)

**Workflow** được triển khai dưới dạng một **Step Functions state machine** điều phối việc thực thi của nhiều hàm **Lambda**. Các hàm **Lambda** này tương tác với mạng nguồn và mạng đích, **Circle Attestation Service** (quan sát và xác minh hoạt động **burn** trên chuỗi nguồn), và sử dụng **AWS Secrets Manager** để lưu trữ **private key** của tài khoản mà từ đó chúng ta muốn chuyển **USDC**.

**Step Functions** mang lại nhiều lợi ích, bao gồm xử lý lỗi và **timeout** tích hợp, tích hợp trực tiếp với các dịch vụ **AWS**, quản lý trạng thái và theo dõi tiến trình **workflow** tích hợp sẵn, cùng lịch sử thực thi **workflow** theo thời gian thực và có thể **audit**.

Sơ đồ dưới đây minh họa **workflow** của **CCTP V2 Fast Transfer**.

![Step Functions Workflow](/images/3-BlogsTranslated/blog2/2.png)

**Workflow** này triển khai các bước bắt buộc để sử dụng **CCTP V2** (để hiểu chi tiết, tham khảo **CCTP developer documentation**):

1. Xác thực các biến đầu vào.
2. Tạo biểu diễn **bytes32** của địa chỉ nơi **USDC** sẽ được gửi đến.
3. Chấp thuận việc chi tiêu số lượng **USDC** cần thiết trên **smart contract TokenMessengerV2**.
4. **Burn USDC** trên mạng nguồn bằng **smart contract TokenMessengerV2**.
5. Lấy **message** và **attestation** từ **Circle Attestation Service**.
6. **Mint USDC** trên mạng đích bằng **smart contract MessageTransmitterV2** (lấy **attestation** mới nếu cần).

Tại thời điểm viết bài, **CCTP V2** hỗ trợ các mạng **Ethereum**, **Avalanche**, **Base**, **Linea** và **Arbitrum**. Do đó, chúng tôi tập trung triển khai trên các **blockchain** tương thích với **EVM**.

**Workflow** được triển khai trên các **testnet** sử dụng **endpoint** từ **Public Node**. Đối với môi trường **production**, cần xem xét thêm (tối thiểu):

- Quản lý **private key** cần được chú ý nhiều hơn. Tham khảo **How to sign Ethereum EIP-1559 transactions using AWS KMS** để tìm hiểu cách các dịch vụ bảo mật **AWS** như **AWS Key Management Service (AWS KMS)** có thể cải thiện mức độ bảo mật. Có thể triển khai **multi-party authorization** cho các giao dịch có giá trị cao.

- Bạn có thể muốn chạy **node** riêng. Tham khảo **AWS Blockchain Node Runners** để có **blueprint** triển khai **node** và loạt bài **AWS Nitro Enclaves for running Ethereum validators** để biết chi tiết cách ký giao dịch trong **Nitro enclave**.

- Bạn nên gắn các hàm **Lambda** vào **VPC**. Tham khảo **Giving Lambda functions access to resources in an Amazon VPC** để biết thêm chi tiết.

- Với mỗi bước trong **workflow**, bạn nên xem xét mọi loại lỗi có thể xảy ra và xác định cách xử lý. Ví dụ, **uptime** và khả năng sẵn sàng của dịch vụ **CCTP** được thiết kế tương tự như các dịch vụ **mint** hiện tại, nhưng bạn vẫn nên xác định cách xử lý các giao dịch bị trì hoãn hoặc việc tạm thời không khả dụng của **Attestation Service**.

- Giải pháp này cũng có thể được tích hợp vào một ứng dụng phi tập trung lớn hơn. Ví dụ: bạn có thể dùng **Amazon Simple Notification Service (Amazon SNS)** để gửi thông báo cho người dùng cuối, và sử dụng **Amazon EventBridge** để kích hoạt các hành động hậu chuyển giao.

Để triển khai giải pháp, chúng tôi sử dụng **AWS CloudFormation template** sau để triển khai giải pháp. **Template** yêu cầu **private key** làm tham số đầu vào, vì vậy chúng tôi tạo trước một **private key** trước khi triển khai. Sau đó, chúng tôi kiểm thử việc chuyển **USDC** từ **Ethereum** sang **Base**.

## **Yêu cầu trước**

Để triển khai giải pháp này, bạn cần có một tài khoản **AWS** với quyền thích hợp.

## **Tạo private key**

Có nhiều cách để tạo **private key**. Trong bài viết này, chúng tôi sử dụng **Python Web3 library** từ **AWS CloudShell**. Để tạo **private key** và địa chỉ liên kết, kết nối tới **CloudShell** và chạy lệnh sau:

```bash
pip install web3 && \
python -c "from web3 import Web3; w3 = Web3(); acc = w3.eth.account.create(); print(f'PRIVATE_KEY={acc._private_key.hex()}; ADDRESS={acc.address}')"
```

Thực thi **output** của lệnh trên để ghi lại **PRIVATE_KEY** và **ADDRESS**.

## **Triển khai CloudFormation template**

Từ cùng phiên **CloudShell**, chạy lệnh sau để triển khai **CloudFormation template**:

```bash
aws cloudformation create-stack --region us-east-1 --stack-name 'USDC-Bridge' --template-url 'https://aws-blogs-artifacts-public.s3.us-east-1.amazonaws.com/artifacts/WEB3-2/USDC-Bridge-CloudFormation-Template.yml' --capabilities CAPABILITY_NAMED_IAM --parameters ParameterKey=PRIVATEKEY,ParameterValue=$PRIVATE_KEY
```

## **Kiểm thử giải pháp**

Để có thể chuyển **USDC** từ một mạng sang mạng khác, bạn cần **native token** (ví dụ: **ETH** cho **Ethereum**) trên cả mạng nguồn và mạng đích (để trả **gas fee**) và **USDC** trên mạng nguồn (để có **USDC** để chuyển). Vì chúng tôi triển khai giải pháp trên **testnet**, bạn có thể nhận chúng từ các **faucet**. Sau đây là một số **faucet** bạn có thể dùng:

- **USDC Testnet Faucet** from **Circle**
- **Sepolia Faucets** from **Chainlink**
- **Ethereum Sepolia Faucet** from **Alchemy**
- **Multi-Chain Faucet** from **QuickNode**
- **Chainstack multi-chain faucet**
- **Free testnet faucets** from **thirdweb**

Trong phần này, chúng tôi minh họa việc chuyển **USDC** từ **Ethereum** sang **Base**, nhưng bạn có thể thử nghiệm với các mạng khác.

Để thực thi **Step Functions state machine**, chúng tôi chuẩn bị **input** như sau:

```json
{
  "source_address": "<replace_with_public_address_from_previous_step>",
  "target_address": "<replace_with_public_address_from_previous_step>",
  "amount": 10000,
  "max_fee": 100,
  "source_domain": "0",
  "target_domain": "6"
}
```

Chúng tôi sử dụng cùng một địa chỉ nguồn và đích, nhưng bạn có thể dùng địa chỉ đích khác. Ngoài ra, giải pháp này sử dụng **Fast Transfer** (tham khảo **CCTP product fee schedule** để biết thêm chi tiết).

Để thực thi **state machine**:

1. Trên **console Step Functions**, chọn **USDC_Bridge state machine**.
2. Chọn **Start execution**.
3. Dán **JSON document** đã chuẩn bị.
4. Chọn **Start execution**.

Nếu mọi thứ diễn ra suôn sẻ, bạn sẽ thấy các bước trong **state machine** được thực thi thành công cho đến cuối **workflow CCTP V2 Fast Transfer**.

![State Machine Execution](/images/3-BlogsTranslated/blog2/3.png)

Nếu có lỗi, bạn sẽ dễ dàng xác định bước nào xảy ra sự cố, kiểm tra **input** và **output** của bước đó, và xem **log** của hàm **Lambda**. **Step Functions** cũng cung cấp khả năng **resume execution** sau khi lỗi ban đầu và tích hợp với **Amazon CloudWatch** để tăng cường khả năng quan sát và cảnh báo.

Sau khi **workflow** thực thi thành công, bạn có thể xác nhận rằng **USDC** đã được chuyển thành công và kiểm tra việc thực thi **smart contract** bằng **block explorer**. Đặc biệt, bạn có thể ghi chú **transaction hash** từ **output** của bước **Mint USDC**, và xác nhận **log** của giao dịch này cho thấy **USDC** mới đã được **mint**, như minh họa trong ảnh chụp màn hình sau.



## **Dọn dẹp**

Từ **CloudShell**, chạy lệnh sau để dọn dẹp tài nguyên:

```bash
aws cloudformation delete-stack --stack-name 'USDC-Bridge'
```

## **Kết luận**

Trong bài viết này, chúng tôi đã chỉ ra cách sử dụng **CCTP V2**, **Lambda**, **Step Functions**, và **Secrets Manager** để triển khai một giải pháp **serverless** nhằm chuyển **USDC** trên **backend** của ứng dụng **onchain**. Bạn có thể mở rộng giải pháp này và tích hợp vào bộ công cụ **AWS** rộng lớn hơn, biến đây thành một nền tảng lý tưởng để chạy các **workload onchain**. Chúng tôi khuyến khích bạn thử nghiệm và chia sẻ phản hồi của mình.

## **Về các tác giả**

### **Corey Cooper**


**Corey** là một nhà phát triển tại **Circle**, người yêu thích bóng rổ và là fan trung thành của đội **Lakers** đến từ **Atlanta**. Anh có sự nghiệp gắn liền với việc xây dựng công nghệ doanh nghiệp và thanh toán. Với hơn 15 năm kinh nghiệm trong vai trò kỹ sư giải pháp, **Corey** mang đến sự kết hợp giữa chuyên môn kỹ thuật sâu sắc, hiểu biết kinh doanh và khả năng lãnh đạo thực tiễn cho các hoạt động ra mắt sản phẩm, triển khai thực tế (**go-live**) và xây dựng các nền tảng có khả năng mở rộng.
![Corey Cooper](/images/3-BlogsTranslated/blog2/4.png)
### **Guillaume Goutaudier**
**Guillaume** là **Kiến trúc sư Doanh nghiệp Cấp cao (Sr Enterprise Architect)** tại **AWS**. Anh hỗ trợ các công ty xây dựng quan hệ đối tác kỹ thuật chiến lược với **AWS**. **Guillaume** cũng có niềm đam mê với các công nghệ **blockchain** và là thành viên của **Technical Field Community for blockchain**.
![Corey Cooper](/images/3-BlogsTranslated/blog2/5.png)
