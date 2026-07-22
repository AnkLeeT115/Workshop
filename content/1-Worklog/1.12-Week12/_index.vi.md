---
title: "Worklog Tuần 12"
date: 2024-01-01
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

# Worklog Tuần 12

## Mục tiêu tuần 12

- Hoàn thiện các tính năng backend cốt lõi cho hệ thống **CloudPay AWS**.
- Phát triển tính năng tạo thanh toán, xử lý webhook, quản lý giao dịch và thông báo.
- Thực hiện kiểm thử toàn hệ thống, tối ưu hóa và chuẩn bị triển khai cuối cùng.

## Các công việc đã thực hiện trong tuần này

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --------- | ------------ | --------------- | ------------------ |
| 2   | - Phát triển module xử lý thanh toán.<br>- Xây dựng workflow tạo Payment URL và ghi nhận giao dịch.<br>- Tích hợp Amazon S3 lưu trữ biên lai thanh toán. | 13/07/2026 | 13/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 3   | - Triển khai xử lý MoMo IPN Webhook.<br>- Xây dựng logic xác thực chữ ký và cập nhật giao dịch.<br>- Viết integration test cho các trường hợp thành công và thất bại. | 14/07/2026 | 14/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 4   | - Phát triển API truy vấn và lịch sử giao dịch.<br>- Triển khai tìm kiếm và lọc theo ngày, trạng thái, số tiền, merchant. | 15/07/2026 | 15/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 5   | - Tích hợp Amazon Cognito cho xác thực và ủy quyền.<br>- Triển khai quản lý role (Merchant & Admin).<br>- Hoàn thiện hệ thống thông báo bằng SNS (Email/SMS). | 16/07/2026 | 16/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 6   | - Thực hiện kiểm thử toàn hệ thống thanh toán.<br>- Sửa lỗi phát hiện trong quá trình test.<br>- Tối ưu hiệu suất, dọn dẹp code và chuẩn bị tài liệu + demo dự án cuối cùng. | 17/07/2026 | 17/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |

## Kết quả đạt được tuần 12

- Hoàn thành module xử lý thanh toán cốt lõi, bao gồm tạo Payment URL và ghi nhận giao dịch.
- Triển khai thành công MoMo IPN Webhook với xác thực chữ ký.
- Phát triển API truy vấn lịch sử và lọc giao dịch.
- Tích hợp Amazon Cognito cho xác thực an toàn và phân quyền.
- Xây dựng hệ thống thông báo bằng Amazon SNS (Email/SMS).
- Thực hiện kiểm thử toàn diện, sửa lỗi, tối ưu hiệu suất và chuẩn bị tài liệu + demo dự án hoàn chỉnh.
