---
title: "Worklog Tuần 5"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

# Nhật ký công việc tuần 5

## Mục tiêu tuần 5

- Tìm hiểu kiến trúc **Microservices**, **Cloud-Native** và mô hình **Serverless** trên AWS.
- Nghiên cứu cách xây dựng hệ thống thương mại điện tử bán mô hình chính hãng sử dụng các dịch vụ AWS.
- Thực hành xây dựng backend hiện đại với khả năng mở rộng, tự động triển khai và giám sát hệ thống.

## Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu quá trình chuyển đổi từ kiến trúc **Monolithic** sang **Microservices**.<br>- Nghiên cứu cách phân chia hệ thống bán mô hình thành các service độc lập:<br>&emsp;+ Product Service<br>&emsp;+ Order Service<br>&emsp;+ Inventory Service<br>- Tìm hiểu khả năng mở rộng và quản lý hệ thống trên AWS. | 18/05/2026 | 18/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 3 | - Xây dựng kiến trúc **Serverless Backend** cho hệ thống thương mại điện tử.<br>- Thực hành sử dụng các dịch vụ AWS:<br>&emsp;+ AWS Lambda xử lý business logic<br>&emsp;+ API Gateway xây dựng REST API<br>&emsp;+ DynamoDB lưu trữ sản phẩm, đơn hàng và tồn kho<br>&emsp;+ Amazon S3 lưu trữ hình ảnh mô hình<br>&emsp;+ SNS/SQS xử lý thông báo và tác vụ bất đồng bộ | 19/05/2026 | 19/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 4 | - Xây dựng API phục vụ hệ thống bán mô hình:<br>&emsp;+ Product API<br>&emsp;+ Order API<br>&emsp;+ Inventory API<br>- Triển khai frontend dạng SPA.<br>- Tìm hiểu Amazon Cognito để xác thực khách hàng và quản trị viên. | 20/05/2026 | 20/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 5 | - Tìm hiểu quy trình triển khai tự động bằng **AWS SAM** và **AWS CodePipeline**.<br>- Thực hành CI/CD cho Serverless Application.<br>- Sử dụng Amazon CloudWatch và AWS X-Ray để giám sát hoạt động của các Lambda Function và API. | 21/05/2026 | 21/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 6 | - Tìm hiểu các dịch vụ AI trên AWS.<br>- Nghiên cứu khả năng ứng dụng AI vào hệ thống bán mô hình:<br>&emsp;+ Gợi ý sản phẩm.<br>&emsp;+ Tìm kiếm thông minh.<br>&emsp;+ Phân loại sản phẩm mô hình. | 22/05/2026 | 22/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |

## Kết quả đạt được tuần 5

- Hiểu được cách chuyển đổi hệ thống từ kiến trúc **Monolithic** sang **Microservices** và áp dụng vào hệ thống thương mại điện tử.

- Nắm được cách thiết kế các service độc lập trong hệ thống bán mô hình:
  - Product Service quản lý thông tin sản phẩm.
  - Order Service xử lý đơn hàng.
  - Inventory Service quản lý số lượng tồn kho.

- Xây dựng kiến trúc **Serverless Backend** sử dụng các dịch vụ AWS:
  - **AWS Lambda** xử lý logic nghiệp vụ.
  - **Amazon API Gateway** cung cấp các API cho frontend.
  - **Amazon DynamoDB** lưu trữ dữ liệu sản phẩm, đơn hàng và kho hàng.
  - **Amazon S3** lưu trữ hình ảnh mô hình.
  - **Amazon SNS/SQS** hỗ trợ xử lý tác vụ bất đồng bộ.

- Hiểu cách xây dựng API cho nền tảng thương mại điện tử:
  - API quản lý sản phẩm.
  - API đặt hàng.
  - API kiểm tra tồn kho.

- Tích hợp **Amazon Cognito** để:
  - Xác thực người dùng.
  - Quản lý quyền truy cập giữa Customer và Admin.

- Hiểu quy trình triển khai tự động:
  - AWS SAM quản lý Serverless Application.
  - AWS CodePipeline hỗ trợ CI/CD.
  - CloudWatch và X-Ray giúp giám sát, phân tích lỗi hệ thống.

- Tìm hiểu khả năng ứng dụng AI trong hệ thống bán mô hình:
  - Đề xuất sản phẩm phù hợp.
  - Cải thiện tìm kiếm sản phẩm.
  - Hỗ trợ phân loại mô hình.

- Có thêm kiến thức về phát triển ứng dụng Cloud hiện đại:
  - Microservices Architecture.
  - Serverless Computing.
  - CI/CD Automation.
  - Cloud Monitoring.
  - AI Integration.