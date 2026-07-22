---
title : "AWS Operation Architecture - PrimeScale"
date : 2026-07-17
weight : 5
chapter : false
pre : " <b> 5. </b> "
---

# Kiến trúc vận hành AWS của hệ thống PrimeScale

## 1. User Authentication & Access Control

Hệ thống PrimeScale hỗ trợ ba nhóm người dùng chính:

- **Customer**: Khách hàng xem thông tin kiểm định chất lượng sản phẩm.
- **Seller**: Người bán đăng tải sản phẩm và gửi yêu cầu kiểm tra.
- **Admin**: Quản lý hệ thống, kiểm duyệt kết quả AI và giám sát hoạt động.

Hệ thống sử dụng **Amazon Cognito** để xác thực và quản lý quyền truy cập người dùng.

Luồng xác thực:

Amazon Cognito đảm nhiệm:

- Đăng nhập và đăng ký tài khoản.
- Quản lý thông tin người dùng.
- Phân quyền Customer, Seller, Admin.
- Cấp JWT Token bảo vệ các API.


## 2. Frontend Delivery Layer

PrimeScale triển khai giao diện người dùng theo mô hình Serverless với React Application.

Kiến trúc:

Amazon S3

Amazon S3 được sử dụng để lưu trữ:

- React Frontend Application.
- Hình ảnh sản phẩm.
- Hình ảnh kết quả kiểm định AI.

Amazon CloudFront

CloudFront chịu trách nhiệm:

- Phân phối nội dung với tốc độ cao.
- Giảm độ trễ truy cập.
- Hỗ trợ lượng lớn người dùng.


## 3. API Management Layer

### Amazon API Gateway

API Gateway đóng vai trò là lớp trung gian tiếp nhận request từ ứng dụng PrimeScale.

Các API chính:

```text
POST   /product/upload

POST   /inspection/start

GET    /inspection/result/{id}

GET    /product/history/{id}
```

API Gateway thực hiện:

- Xác thực JWT Token từ Amazon Cognito.
- Điều hướng request.
- Kiểm soát quyền truy cập.
- Kết nối với AWS Lambda.


## 4. Product Image Processing System

Seller upload hình ảnh sản phẩm lên hệ thống:

Ví dụ:

- Hộp Gundam.
- Model hoàn chỉnh.
- Linh kiện.
- Logo nhà sản xuất.
- Vị trí lỗi trên sản phẩm.

Luồng xử lý:


## 5. AI Quality Inspection Processing

### AWS Lambda Worker

AWS Lambda xử lý các yêu cầu kiểm định sản phẩm.

Chức năng:

- Nhận thông tin sản phẩm.
- Gửi hình ảnh đến hệ thống AI.
- Phân tích kết quả.
- Sinh báo cáo chất lượng.

Luồng xử lý:


## 6. AI Image Analysis

### Amazon Rekognition

Amazon Rekognition được sử dụng để phân tích hình ảnh sản phẩm mô hình.

### Product Detection

Hệ thống có thể:

- Nhận diện loại mô hình.
- Xác định đối tượng trong ảnh.
- Kiểm tra logo thương hiệu.

### Defect Detection

Phát hiện các lỗi:

- Trầy xước.
- Nứt gãy.
- Thiếu phụ kiện.
- Sai màu.
- Hư hỏng hộp.

Ví dụ kết quả kiểm định:

```json
{
 "productId":"GUNDAM001",
 "qualityScore":95,
 "condition":"Excellent",
 "defects":[],
 "status":"Verified"
}
```


## 7. Inspection Queue Management

### Amazon SQS

Để đảm bảo hệ thống hoạt động ổn định khi có nhiều yêu cầu kiểm định, PrimeScale sử dụng Amazon SQS để quản lý hàng đợi xử lý.

Ví dụ khi có nhiều sản phẩm:

```text
1000 Product Images Uploaded
```

Hệ thống xử lý bất đồng bộ:

Lợi ích:

- Tránh quá tải Lambda.
- Xử lý bất đồng bộ.
- Hỗ trợ Retry khi xảy ra lỗi.


## 8. Product Data Storage

### Amazon DynamoDB

DynamoDB lưu trữ thông tin sản phẩm và kết quả kiểm định.

### Product Table

```json
{
 "productId":"PS001",
 "name":"MG Gundam",
 "seller":"user001",
 "status":"Verified"
}
```

### Inspection Table

```json
{
 "inspectionId":"INS001",
 "score":95,
 "result":"Approved",
 "checkedDate":"2026-07-17"
}
```

Ưu điểm:

- Truy xuất dữ liệu nhanh.
- Tự động mở rộng.
- Không cần quản lý database server.


## 9. Notification System

### Amazon SNS

Sau khi quá trình kiểm định hoàn tất, hệ thống gửi thông báo đến người dùng.

Luồng:


## 10. Monitoring & Logging

### Amazon CloudWatch

CloudWatch giám sát toàn bộ hoạt động của hệ thống.

Theo dõi:

- Lambda Execution.
- API Request.
- AI Processing Time.
- Failed Inspection.
- System Error.

Luồng:


Ngoài ra PrimeScale có thể sử dụng:

### AWS X-Ray

Để phân tích:

- API Latency.
- Lambda Performance.
- Bottleneck trong workflow.


## 11. Complete PrimeScale AWS Operation Architecture


# Kết luận

Kiến trúc vận hành PrimeScale sử dụng mô hình **AWS Serverless Architecture** giúp hệ thống:

- Tự động kiểm định chất lượng sản phẩm bằng AI.
- Giảm thời gian kiểm tra thủ công.
- Lưu trữ lịch sử xác minh sản phẩm minh bạch.
- Đảm bảo khả năng mở rộng khi số lượng sản phẩm tăng cao.
- Cung cấp trải nghiệm mua bán mô hình đáng tin cậy cho cộng đồng yêu thích Gundam, Figure, Warhammer và Scale Model tại Việt Nam.