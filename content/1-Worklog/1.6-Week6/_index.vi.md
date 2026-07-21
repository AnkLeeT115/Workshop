---
title: "Worklog Tuần 6"
date: 2024-01-01
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

# Nhật ký công việc tuần 6

## Mục tiêu tuần 6

- Tìm hiểu quy trình đóng gói, triển khai và quản lý ứng dụng Container trên AWS.
- Thực hành triển khai các Microservices của hệ thống thương mại điện tử bán mô hình chính hãng.
- Xây dựng quy trình CI/CD và giám sát môi trường Container trên AWS.

## Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu Docker và quy trình đóng gói ứng dụng.<br>- Thực hành xây dựng Docker Image cho các thành phần của hệ thống:<br>&emsp;+ Product Service.<br>&emsp;+ Order Service.<br>&emsp;+ Inventory Service.<br>- Quản lý Docker Image phục vụ triển khai trên AWS. | 25/05/2026 | 25/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 3 | - Triển khai thử nghiệm ứng dụng Container trên AWS.<br>- Tìm hiểu Amazon ECS, Amazon EKS và cách quản lý Container Cluster.<br>- Cấu hình tài nguyên hệ thống và kiểm tra trạng thái hoạt động của các service. | 26/05/2026 | 26/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 4 | - Nghiên cứu cách triển khai Microservices bằng Docker và AWS Fargate.<br>- Đóng gói và triển khai các service độc lập:<br>&emsp;+ Product Management Service.<br>&emsp;+ Order Processing Service.<br>&emsp;+ Inventory Management Service.<br>- Đánh giá khả năng mở rộng của hệ thống. | 27/05/2026 | 27/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 5 | - Xây dựng quy trình CI/CD bằng AWS CodePipeline và GitHub.<br>- Tự động hóa quá trình:<br>&emsp;+ Build Docker Image.<br>&emsp;+ Kiểm thử ứng dụng.<br>&emsp;+ Triển khai Microservices lên AWS. | 28/05/2026 | 28/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 6 | - Cấu hình giám sát và quản lý tài nguyên Container.<br>- Sử dụng công cụ monitoring để theo dõi trạng thái service.<br>- Áp dụng các biện pháp bảo mật nhằm đảm bảo tính ổn định và an toàn của hệ thống. | 29/05/2026 | 29/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |

## Kết quả đạt được tuần 6

- Hiểu quy trình đóng gói ứng dụng bằng **Docker**:
  - Xây dựng Docker Image.
  - Quản lý Image phục vụ triển khai.
  - Hiểu vai trò của Container trong phát triển ứng dụng Cloud.

- Thực hành triển khai ứng dụng Container trên AWS:
  - Amazon ECS.
  - Amazon EKS.
  - AWS Fargate.

- Áp dụng Container vào kiến trúc Microservices của hệ thống bán mô hình:
  - Product Service quản lý sản phẩm.
  - Order Service xử lý đơn hàng.
  - Inventory Service quản lý tồn kho.

- Hiểu cách triển khai hệ thống Microservices có khả năng mở rộng:
  - Tách các chức năng thành service độc lập.
  - Dễ dàng mở rộng từng thành phần khi lượng truy cập tăng cao.
  - Quản lý tài nguyên hiệu quả trên Cloud.

- Xây dựng quy trình CI/CD với:
  - AWS CodePipeline.
  - GitHub.

- Tự động hóa các bước:
  - Build ứng dụng.
  - Kiểm thử.
  - Triển khai Container.

- Nắm được cách giám sát và bảo mật môi trường Container:
  - Theo dõi trạng thái service.
  - Quản lý tài nguyên.
  - Cải thiện tính ổn định và an toàn của hệ thống.

- Tích lũy kiến thức thực tế về:
  - Docker Containerization.
  - Microservices Deployment.
  - AWS ECS/EKS/Fargate.
  - CI/CD Automation.
  - Cloud Monitoring và Security.