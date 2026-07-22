---
title: "Đề xuất dự án"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# CloudPay - Hệ thống thanh toán trên AWS
## Kiến trúc thanh toán Serverless sử dụng AWS

### 1. Tổng quan dự án

CloudPay xây dựng một hệ thống thanh toán trực tuyến an toàn, có khả năng mở rộng và hoạt động theo kiến trúc Serverless trên nền tảng AWS. Hệ thống được tích hợp với cổng thanh toán MoMo nhằm xử lý các giao dịch thanh toán của khách hàng một cách nhanh chóng và đáng tin cậy.

Kiến trúc sử dụng Amazon Cognito để xác thực người dùng, Amazon API Gateway và AWS Lambda để xử lý nghiệp vụ, Amazon SQS để xử lý bất đồng bộ, Amazon SNS để gửi thông báo, Amazon RDS để lưu trữ dữ liệu giao dịch và Amazon CloudWatch cùng AWS X-Ray để giám sát toàn bộ hệ thống.

Nhờ tận dụng các dịch vụ Serverless của AWS, hệ thống có thể tự động mở rộng khi lượng giao dịch tăng cao, giảm chi phí vận hành và đảm bảo tính sẵn sàng của dịch vụ.

---

## 2. Bài toán đặt ra

### Thực trạng

Các hệ thống thanh toán truyền thống thường gặp những vấn đề như:

- Giao dịch dễ bị gián đoạn khi lượng truy cập tăng cao.
- Callback từ cổng thanh toán có thể bị mất do lỗi mạng.
- Thiếu cơ chế tự động xử lý lại các giao dịch thất bại.
- Khó theo dõi trạng thái giao dịch và phát hiện lỗi.
- Chi phí đầu tư và vận hành máy chủ lớn khi cần mở rộng hệ thống.

### Giải pháp

PrimeScale áp dụng kiến trúc thanh toán theo mô hình **Event-Driven Serverless** trên AWS.

Người dùng đăng nhập thông qua Amazon Cognito trước khi thực hiện thanh toán. Sau khi được xác thực, yêu cầu thanh toán sẽ được gửi đến Amazon API Gateway, nơi AWS Lambda tạo liên kết thanh toán và chuyển hướng người dùng sang cổng thanh toán MoMo.

Sau khi khách hàng hoàn tất thanh toán, MoMo gửi kết quả về Webhook Lambda. Lambda sẽ xác thực chữ ký số của giao dịch và đưa thông tin vào Amazon SQS. Worker Lambda tiếp tục xử lý dữ liệu, cập nhật trạng thái thanh toán vào Amazon RDS và gửi thông báo xác nhận thông qua Amazon SNS.

Nếu xảy ra lỗi trong quá trình xử lý, dữ liệu sẽ được chuyển sang Dead Letter Queue (DLQ) để quản trị viên có thể xử lý hoặc thực hiện lại giao dịch.

### Lợi ích

- Xử lý thanh toán nhanh và ổn định.
- Bảo mật bằng JWT Token và Amazon Cognito.
- Xử lý bất đồng bộ giúp tăng hiệu năng.
- Tự động xử lý lại các giao dịch lỗi.
- Dễ dàng mở rộng khi số lượng giao dịch tăng.
- Theo dõi và giám sát hệ thống theo thời gian thực.
- Tiết kiệm chi phí nhờ kiến trúc Serverless.

---

## 3. Kiến trúc giải pháp

Hệ thống thanh toán được triển khai hoàn toàn trên nền tảng AWS theo kiến trúc Serverless kết hợp xử lý sự kiện (Event-Driven Architecture).

Quy trình hoạt động của hệ thống gồm các bước:

1. Người dùng đăng nhập bằng Amazon Cognito.
2. API Gateway xác thực JWT Token.
3. AWS Lambda tạo liên kết thanh toán.
4. Người dùng được chuyển sang cổng thanh toán MoMo.
5. Sau khi thanh toán thành công, MoMo gửi Webhook về hệ thống.
6. Webhook Lambda kiểm tra chữ ký số và xác thực giao dịch.
7. Thông tin giao dịch được đưa vào Amazon SQS.
8. Worker Lambda đọc dữ liệu từ SQS và xử lý giao dịch.
9. Kết quả thanh toán được lưu vào Amazon RDS thông qua RDS Proxy.
10. Amazon SNS gửi Email hoặc SMS xác nhận cho khách hàng.
11. Amazon CloudWatch và AWS X-Ray theo dõi hiệu suất, ghi log và cảnh báo khi xảy ra lỗi.

![Kiến trúc hệ thống thanh toán](/images/2-Proposal/payment_architecture.png)

---

## Các dịch vụ AWS sử dụng

| Dịch vụ | Chức năng |
|----------|-----------|
| Amazon Cognito | Xác thực người dùng và quản lý JWT Token |
| Amazon API Gateway | Cung cấp API cho hệ thống |
| AWS Lambda | Xử lý nghiệp vụ thanh toán |
| Amazon SQS | Hàng đợi xử lý giao dịch |
| Amazon SQS Dead Letter Queue | Lưu các giao dịch xử lý thất bại |
| Amazon SNS | Gửi Email và SMS thông báo |
| Amazon RDS | Lưu trữ dữ liệu giao dịch |
| Amazon RDS Proxy | Quản lý kết nối cơ sở dữ liệu |
| Amazon S3 | Lưu trữ giao diện web tĩnh |
| Amazon CloudFront | Phân phối nội dung tốc độ cao |
| AWS WAF | Bảo vệ ứng dụng trước các cuộc tấn công |
| Amazon CloudWatch | Giám sát hệ thống |
| AWS X-Ray | Theo dõi luồng xử lý và phân tích lỗi |
| MoMo | Cổng thanh toán trực tuyến |

---

## 4. Triển khai kỹ thuật

### Giai đoạn 1: Xác thực người dùng

- Người dùng đăng nhập bằng Amazon Cognito.
- Cognito cấp JWT Token.
- API Gateway kiểm tra Token trước khi cho phép truy cập API.

### Giai đoạn 2: Khởi tạo thanh toán

- AWS Lambda tạo yêu cầu thanh toán.
- Sinh Payment URL.
- Trả URL về giao diện.
- Người dùng được chuyển sang MoMo để thanh toán.

### Giai đoạn 3: Xác thực giao dịch

- MoMo gửi Webhook sau khi thanh toán.
- Lambda xác minh chữ ký HMAC.
- Kiểm tra trạng thái giao dịch.
- Đưa dữ liệu vào Amazon SQS.

### Giai đoạn 4: Xử lý bất đồng bộ

Worker Lambda sẽ:

- Đọc dữ liệu từ Amazon SQS.
- Cập nhật trạng thái thanh toán.
- Ghi dữ liệu vào Amazon RDS.
- Gửi thông báo thông qua Amazon SNS.
- Gửi Email hoặc SMS xác nhận cho khách hàng.

Nếu xảy ra lỗi:

- Thông điệp sẽ được chuyển sang Amazon SQS Dead Letter Queue.
- Quản trị viên có thể sử dụng chức năng Retry để xử lý lại giao dịch.

---

## 5. Lộ trình triển khai

| Giai đoạn | Nội dung |
|------------|----------|
| Tuần 1 | Phân tích yêu cầu và thiết kế kiến trúc |
| Tuần 2 | Cấu hình Amazon Cognito và API Gateway |
| Tuần 3 | Xây dựng Lambda tạo Payment URL |
| Tuần 4 | Tích hợp cổng thanh toán MoMo |
| Tuần 5 | Xây dựng Webhook xác thực giao dịch |
| Tuần 6 | Triển khai Amazon SQS và Worker Lambda |
| Tuần 7 | Tích hợp Amazon SNS gửi Email và SMS |
| Tuần 8 | Cấu hình CloudWatch và AWS X-Ray |
| Tuần 9 | Kiểm thử hiệu năng và tối ưu hệ thống |
| Tuần 10 | Triển khai và đánh giá hệ thống |

---

## 6. Ước tính chi phí

### Chi phí hạ tầng hàng tháng

| Dịch vụ | Chi phí ước tính |
|----------|------------------|
| Amazon API Gateway | 5 USD |
| AWS Lambda | 8 USD |
| Amazon SQS | 2 USD |
| Amazon SNS | 2 USD |
| Amazon Cognito | 3 USD |
| Amazon RDS | 20 USD |
| Amazon CloudWatch | 5 USD |
| Amazon S3 | 2 USD |
| Amazon CloudFront | 5 USD |
| AWS WAF | 5 USD |

**Tổng chi phí dự kiến:** khoảng **50–60 USD/tháng**.

Trong giai đoạn phát triển và thử nghiệm có thể tận dụng AWS Free Tier để giảm chi phí gần như bằng 0.

---

## 7. Đánh giá rủi ro

| Rủi ro | Mức độ ảnh hưởng | Biện pháp giảm thiểu |
|----------|-----------------|----------------------|
| Callback từ MoMo thất bại | Cao | Retry thông qua Amazon SQS DLQ |
| Cơ sở dữ liệu gặp sự cố | Cao | Triển khai Amazon RDS Multi-AZ |
| Truy cập trái phép | Cao | Xác thực JWT bằng Amazon Cognito |
| Lượng giao dịch tăng đột biến | Trung bình | AWS Lambda tự động mở rộng |
| Gian lận thanh toán | Cao | Xác thực chữ ký HMAC của MoMo |
| Khó phát hiện lỗi hệ thống | Trung bình | CloudWatch Alarm và AWS X-Ray |

---

## 8. Kết quả mong đợi

Hệ thống thanh toán của PrimeScale hướng tới một nền tảng thanh toán trực tuyến an toàn, ổn định và có khả năng mở rộng cao.

Sau khi hoàn thành, hệ thống sẽ đạt được các mục tiêu:

- Xác thực người dùng an toàn bằng Amazon Cognito.
- Tích hợp thành công cổng thanh toán MoMo.
- Xử lý giao dịch theo kiến trúc bất đồng bộ sử dụng Amazon SQS.
- Lưu trữ dữ liệu thanh toán trên Amazon RDS.
- Gửi Email và SMS xác nhận tự động bằng Amazon SNS.
- Giám sát toàn bộ hệ thống bằng Amazon CloudWatch và AWS X-Ray.
- Tự động xử lý và khôi phục các giao dịch thất bại thông qua Dead Letter Queue.
- Đảm bảo khả năng mở rộng, tính sẵn sàng cao và tối ưu chi phí nhờ kiến trúc Serverless trên AWS.