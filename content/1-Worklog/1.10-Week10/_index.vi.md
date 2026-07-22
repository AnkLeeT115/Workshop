---
title: "Worklog Tuần 10"
date: 2024-01-01
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

# Worklog Tuần 10

## Mục tiêu tuần 10

- Xây dựng nền tảng backend cho hệ thống **MoMoPay AWS** sử dụng các dịch vụ Serverless.
- Thiết kế mô hình dữ liệu DynamoDB và triển khai các hàm backend bằng AWS Lambda.
- Phát triển các tính năng cốt lõi: Tạo thanh toán, xử lý webhook, quản lý giao dịch.

## Các công việc đã thực hiện trong tuần này

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --------- | ------------ | --------------- | ------------------ |
| 2   | - Thiết kế cấu trúc database NoSQL bằng **Amazon DynamoDB**.<br>- Tạo data model cho:<br>&emsp;+ Transactions<br>&emsp;+ Webhook Logs<br>&emsp;+ Users/Merchants<br>&emsp;+ Audit Logs<br>- Xác định partition keys và access patterns. | 22/06/2026 | 22/06/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 3   | - Tạo và cấu hình các bảng DynamoDB.<br>- Chèn dữ liệu giao dịch mẫu.<br>- Test các thao tác database (CRUD). | 23/06/2026 | 23/06/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 4   | - Xây dựng backend service bằng **AWS Lambda**.<br>- Phát triển các hàm Lambda cho:<br>&emsp;+ Tạo Payment URL<br>&emsp;+ Xử lý MoMo IPN Webhook<br>&emsp;+ Cập nhật trạng thái giao dịch<br>&emsp;+ Truy vấn giao dịch | 24/06/2026 | 24/06/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 5   | - Cấu hình **Amazon API Gateway** và kết nối với Lambda functions.<br>- Tạo REST API endpoints cho các chức năng thanh toán.<br>- Test request và response API. | 25/06/2026 | 25/06/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 6   | - Triển khai lưu trữ biên lai bằng **Amazon S3**.<br>- Cấu hình workflow upload tài liệu thanh toán.<br>- Test tích hợp toàn bộ giữa S3, Lambda, DynamoDB và MoMo Webhook. | 26/06/2026 | 26/06/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |

## Kết quả đạt được tuần 10

- Thiết kế thành công cấu trúc DynamoDB cho hệ thống thanh toán.
- Tạo và cấu hình các bảng DynamoDB, chèn dữ liệu mẫu.
- Xây dựng logic backend chính bằng **AWS Lambda** (Tạo Payment URL, Xử lý Webhook, Quản lý giao dịch).
- Xây dựng REST APIs qua **Amazon API Gateway** và test thành công.
- Tích hợp **Amazon S3** để lưu trữ biên lai thanh toán.
- Nâng cao hiểu biết về phát triển backend Serverless cho hệ thống thanh toán:
  - Mô hình dữ liệu DynamoDB.
  - Logic business với Lambda.
  - Tích hợp API Gateway.
  - Xử lý webhook an toàn.
