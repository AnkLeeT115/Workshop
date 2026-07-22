---
title: "Worklog Tuần 5"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

# Worklog Tuần 5

## Mục tiêu tuần 5

- Hiểu về **Microservices Architecture**, **Cloud-Native Architecture**, và mô hình **Serverless** trong hệ thống thanh toán.
- Thiết kế backend thanh toán serverless tích hợp MoMo.
- Thực hành xây dựng ứng dụng thanh toán scalable, pipeline triển khai tự động và giải pháp giám sát trên AWS.

## Các công việc đã thực hiện trong tuần này

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --------- | ------------ | --------------- | ------------------ |
| 2   | - Nghiên cứu quá trình chuyển đổi từ **Monolithic Architecture** sang **Microservices Architecture** cho hệ thống thanh toán.<br>- Phân tích cách chia hệ thống thanh toán thành các service độc lập:<br>&emsp;+ Payment Initiation Service<br>&emsp;+ Webhook Processing Service<br>&emsp;+ Transaction Management Service<br>&emsp;+ Notification Service | 18/05/2026 | 18/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 3   | - Thiết kế **Serverless Payment Backend Architecture**.<br>- Thực hành sử dụng các dịch vụ AWS chính:<br>&emsp;+ AWS Lambda xử lý logic thanh toán<br>&emsp;+ API Gateway quản lý REST API<br>&emsp;+ Amazon SQS & SNS xử lý bất đồng bộ<br>&emsp;+ DynamoDB / RDS lưu trữ giao dịch<br>&emsp;+ S3 lưu trữ biên lai thanh toán | 19/05/2026 | 19/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 4   | - Phát triển các API cốt lõi cho hệ thống thanh toán:<br>&emsp;+ Create Payment URL API<br>&emsp;+ Webhook IPN Handler API<br>&emsp;+ Transaction Query API<br>- Nghiên cứu Amazon Cognito cho xác thực Merchant & Admin. | 20/05/2026 | 20/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos<br>MoMo API Docs |
| 5   | - Triển khai tự động sử dụng **AWS SAM** và **AWS CodePipeline**.<br>- Thiết lập CI/CD pipeline cho các service thanh toán.<br>- Sử dụng Amazon CloudWatch và AWS X-Ray để giám sát Lambda và hiệu suất giao dịch. | 21/05/2026 | 21/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 6   | - Khám phá các dịch vụ AI/ML của AWS cho hệ thống thanh toán.<br>- Nghiên cứu ứng dụng AI:<br>&emsp;+ Phát hiện gian lận (Fraud Detection)<br>&emsp;+ Phát hiện bất thường giao dịch<br>&emsp;+ Xử lý biên lai thông minh | 22/05/2026 | 22/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |

## Kết quả đạt được tuần 5

- Hiểu cách chuyển đổi từ **Monolithic** sang **Microservices Architecture** và áp dụng vào hệ thống thanh toán.

- Thiết kế được các service độc lập cho MoMoPay AWS:
  - Payment Initiation Service
  - Webhook Processing Service
  - Transaction Management Service
  - Notification Service

- Nắm vững **Serverless Payment Architecture** sử dụng các dịch vụ AWS:
  - **AWS Lambda** xử lý logic thanh toán
  - **Amazon API Gateway** quản lý API
  - **Amazon SQS / SNS** xử lý bất đồng bộ và thông báo
  - **DynamoDB / RDS** lưu trữ giao dịch
  - **Amazon S3** lưu biên lai thanh toán

- Phát triển được các API thanh toán quan trọng:
  - Tạo Payment URL
  - Xử lý Webhook IPN từ MoMo
  - Truy vấn trạng thái giao dịch

- Tích hợp **Amazon Cognito** để xác thực và phân quyền (Merchant & Admin).

- Thành thạo quy trình triển khai tự động:
  - AWS SAM cho ứng dụng Serverless
  - AWS CodePipeline cho CI/CD
  - CloudWatch + X-Ray cho giám sát và troubleshooting

- Khám phá ứng dụng AI trong hệ thống thanh toán:
  - Phát hiện gian lận
  - Phát hiện bất thường giao dịch
  - Xử lý biên lai thông minh

- Nâng cao kiến thức về phát triển hệ thống thanh toán hiện đại trên AWS.
