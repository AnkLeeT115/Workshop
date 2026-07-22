---
title: "Kiến trúc Hệ thống"
date: 2026-07-17 
weight: 2
chapter: false
pre: " <b> 5.2. </b> "
---

#### Tổng quan Dự án

**MoMoPay AWS** là nền tảng thanh toán an toàn, khả mở, tích hợp với MoMo, được thiết kế dành cho các merchant và doanh nghiệp tại Việt Nam. Hệ thống hỗ trợ tạo Payment URL, xử lý webhook, quản lý giao dịch, thông báo thời gian thực và dashboard quản trị.

Thay vì sử dụng mô hình server truyền thống, MoMoPay AWS sử dụng hoàn toàn **kiến trúc Serverless** trên Amazon Web Services (AWS). Cách tiếp cận này giúp giảm chi phí vận hành, tự động scale theo khối lượng giao dịch và đảm bảo tính sẵn sàng cao mà không cần quản lý hạ tầng vật lý.

#### Kiến trúc Hệ thống

MoMoPay AWS được thiết kế theo mô hình **Frontend – API – Serverless Backend – Database**, trong đó mỗi dịch vụ AWS đảm nhận một vai trò cụ thể trong luồng thanh toán.

+ **Frontend (React / Electron)** được host trên **Amazon S3** và phân phối toàn cầu qua **Amazon CloudFront** để tăng tốc độ tải trang.
+ **Amazon API Gateway** nhận và định tuyến các request API đến **AWS Lambda Functions**.
+ **Amazon Cognito** chịu trách nhiệm xác thực và ủy quyền người dùng (Merchant & Admin).
+ **AWS Lambda** xử lý logic thanh toán cốt lõi: tạo Payment URL, xử lý webhook MoMo, cập nhật trạng thái giao dịch…
+ **Amazon DynamoDB** lưu trữ thông tin giao dịch, log webhook và dữ liệu audit với khả năng scale tự động.
+ **Amazon S3** lưu trữ biên lai thanh toán, hóa đơn và các tài liệu liên quan.
+ **Amazon SQS** quản lý xử lý bất đồng bộ và cơ chế retry.
+ **Amazon SNS** gửi thông báo thời gian thực (Email / SMS) cho merchant và khách hàng.
+ **Amazon CloudWatch + X-Ray** giám sát hiệu suất hệ thống, thu thập log và cảnh báo lỗi.
+ **AWS Serverless Application Model (SAM)** được sử dụng để định nghĩa và triển khai toàn bộ hạ tầng theo Infrastructure as Code.

#### Luồng Hoạt động Hệ thống

1. Merchant truy cập dashboard qua **Amazon CloudFront**.
2. Người dùng (Merchant) xác thực qua **Amazon Cognito** và nhận JWT Token.
3. Frontend gửi request đến **Amazon API Gateway**.
4. API Gateway kiểm tra token và gọi **AWS Lambda Function** tương ứng.
5. Lambda tương tác với **Amazon DynamoDB** để ghi nhận giao dịch.
6. Khi khách hàng khởi tạo thanh toán, Lambda tạo Payment URL và trả về cho frontend.
7. MoMo gửi Webhook IPN → Lambda xử lý và lưu vào DynamoDB.
8. **Amazon SQS** đảm nhận cơ chế retry khi webhook thất bại.
9. **Amazon SNS** gửi thông báo xác nhận cho merchant và khách hàng.
10. Toàn bộ hoạt động được giám sát thời gian thực bởi **Amazon CloudWatch**.

#### Mục tiêu Workshop

Trong workshop này, bạn sẽ xây dựng và triển khai một hệ thống thanh toán Serverless tích hợp MoMo trên AWS:

+ Triển khai frontend bằng **Amazon S3** và **Amazon CloudFront**.
+ Xây dựng REST API bằng **Amazon API Gateway** và **AWS Lambda**.
+ Lưu trữ dữ liệu giao dịch bằng **Amazon DynamoDB**.
+ Cấu hình xác thực và ủy quyền bằng **Amazon Cognito**.
+ Xử lý Webhook MoMo an toàn với kiểm tra chữ ký.
+ Triển khai cơ chế