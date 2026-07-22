---
title: "Worklog Tuần 6"
date: 2024-01-01
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

# Worklog Tuần 6

## Mục tiêu tuần 6

- Hiểu quy trình đóng gói, triển khai và quản lý ứng dụng Container trên AWS.
- Thực hành triển khai các Microservices cho backend hệ thống thanh toán MoMo.
- Xây dựng CI/CD workflow và giám sát môi trường ứng dụng Container.

## Các công việc đã thực hiện trong tuần này

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --------- | ------------ | --------------- | ------------------ |
| 2   | - Học Docker và quy trình đóng gói ứng dụng.<br>- Build Docker Images cho các thành phần hệ thống:<br>&emsp;+ Payment Service<br>&emsp;+ Webhook Service<br>&emsp;+ Transaction Service<br>- Quản lý Docker Images để triển khai trên AWS. | 25/05/2026 | 25/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 3   | - Triển khai ứng dụng Container trên AWS.<br>- Tìm hiểu Amazon ECS, Amazon EKS và quản lý Container Cluster.<br>- Cấu hình tài nguyên hệ thống và kiểm tra hoạt động service. | 26/05/2026 | 26/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 4   | - Triển khai Microservices sử dụng Docker và AWS Fargate.<br>- Đóng gói và triển khai các service độc lập:<br>&emsp;+ Payment Initiation Service<br>&emsp;+ Webhook Processing Service<br>&emsp;+ Transaction Management Service<br>- Đánh giá khả năng scale của hệ thống. | 27/05/2026 | 27/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 5   | - Xây dựng CI/CD pipeline sử dụng AWS CodePipeline và GitHub.<br>- Tự động hóa:<br>&emsp;+ Build Docker Image<br>&emsp;+ Kiểm thử ứng dụng<br>&emsp;+ Triển khai Microservices lên AWS. | 28/05/2026 | 28/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 6   | - Cấu hình giám sát và quản lý tài nguyên Container.<br>- Giám sát trạng thái và hiệu suất service.<br>- Áp dụng các best practices về bảo mật để tăng tính ổn định và đáng tin cậy của hệ thống. | 29/05/2026 | 29/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |

## Kết quả đạt được tuần 6

- Hiểu cách đóng gói ứng dụng bằng **Docker**:
  - Build Docker Images.
  - Quản lý Images để triển khai.
  - Hiểu vai trò của Container trong phát triển ứng dụng Cloud.

- Thực hành triển khai ứng dụng Container trên AWS:
  - Amazon ECS.
  - Amazon EKS.
  - AWS Fargate.

- Áp dụng công nghệ Container vào kiến trúc Microservices của hệ thống thanh toán MoMoPay:
  - Payment Service
  - Webhook Processing Service
  - Transaction Management Service

- Nắm cách xây dựng hệ thống Microservices scalable:
  - Tách biệt chức năng kinh doanh thành các service độc lập.
  - Scale từng service theo nhu cầu traffic.
  - Quản lý tài nguyên Cloud hiệu quả.

- Xây dựng workflow CI/CD sử dụng:
  - AWS CodePipeline.
  - GitHub.

- Tự động hóa:
  - Build ứng dụng.
  - Testing.
  - Triển khai Container.

- Học các thực hành giám sát và bảo mật Container:
  - Giám sát trạng thái service.
  - Quản lý sử dụng tài nguyên.
  - Tăng cường tính ổn định và bảo mật hệ thống.

- Có kinh nghiệm thực tế về:
  - Docker Containerization.
  - Microservices Deployment.
  - AWS ECS/EKS/Fargate.
  - CI/CD Automation.
  - Cloud Monitoring & Security.