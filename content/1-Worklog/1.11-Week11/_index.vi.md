---
title: "Worklog Tuần 11"
date: 2024-01-01
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

# Worklog Tuần 11

## Mục tiêu tuần 11

- Triển khai xác thực và ủy quyền người dùng bằng **Amazon Cognito và JWT**.
- Phát triển tính năng xử lý thanh toán, webhook và xác thực giao dịch.
- Thực hiện kiểm thử API và cải thiện CI workflow cho backend thanh toán.

## Các công việc đã thực hiện trong tuần này

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --------- | ------------ | --------------- | ------------------ |
| 2   | - Cấu hình **Amazon Cognito User Pool** cho Merchant và Administrator.<br>- Triển khai luồng đăng ký và đăng nhập.<br>- Tạo và validate JWT token. | 06/07/2026 | 06/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 3   | - Triển khai ủy quyền bằng JWT và Cognito groups.<br>- Cấu hình kiểm soát truy cập cho Merchant và Admin.<br>- Test protected API endpoints qua API Gateway. | 07/07/2026 | 07/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 4   | - Phát triển workflow xử lý thanh toán bằng AWS Lambda.<br>- Triển khai:<br>&emsp;+ Tạo Payment URL<br>&emsp;+ Xử lý MoMo IPN Webhook<br>&emsp;+ Validate giao dịch<br>&emsp;+ Cập nhật trạng thái giao dịch | 08/07/2026 | 08/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 5   | - Viết test cho các API thanh toán, webhook và transaction.<br>- Test các kịch bản xác thực (valid user, invalid token, unauthorized). | 09/07/2026 | 09/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 6   | - Cải thiện CI workflow cho ứng dụng thanh toán Serverless.<br>- Cấu hình test tự động trước khi deploy.<br>- Review Lambda, API Gateway và DynamoDB. | 10/07/2026 | 10/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |

## Kết quả đạt được tuần 11

- Triển khai thành công xác thực bằng **Amazon Cognito** với JWT.
- Xây dựng cơ chế ủy quyền theo role (Merchant & Admin).
- Hoàn thành các chức năng xử lý thanh toán cốt lõi (Tạo Payment URL, Xử lý Webhook, Quản lý giao dịch).
- Thực hiện kiểm thử API toàn diện và các kịch bản bảo mật.
- Cải thiện quy trình CI/CD với automated testing.
- Nâng cao độ tin cậy của backend thanh toán Serverless.
