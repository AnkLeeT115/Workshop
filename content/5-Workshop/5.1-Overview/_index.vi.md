---
title: "Tổng quan Dự án"
date: 2026-07-19
weight: 1
chapter: false
pre: " <b> 5.1. </b> "
---

# Nền tảng Dự án và Các Vấn đề Thiết kế Hệ thống

## Nền tảng Dự án

Một trong những thách thức lớn nhất khi xây dựng hệ thống thanh toán là không chỉ làm sao cho giao dịch diễn ra nhanh chóng, mà còn phải đảm bảo tính an toàn, minh bạch và đáng tin cậy tuyệt đối. Người dùng (Merchant và Khách hàng) mong muốn giao dịch diễn ra mượt mà, phản hồi tức thì, nhưng phía sau là hàng loạt rủi ro: gian lận, replay attack, double spending, lỗi đồng bộ, và chi phí vận hành cloud tăng cao khi traffic đột biến.

Dự án **MoMoPay AWS** áp dụng nguyên tắc “Server is the Source of Truth” – Server phải là bên quyết định tất cả các quy tắc quan trọng (tạo payment URL, xác thực webhook, cập nhật trạng thái giao dịch, cấp reward…). Mọi hành động đều có phản hồi rõ ràng, kịp thời và có thể kiểm tra lại (audit log), giúp cả Merchant và hệ thống có lòng tin vào dữ liệu.

## Tuyên bố Vấn đề và Mục tiêu Dự án

Các hệ thống thanh toán truyền thống thường gặp phải bài toán cân bằng giữa **tốc độ – an toàn – chi phí**. Hệ thống thuần server-based có thể an toàn nhưng khó scale và chi phí cao. Hệ thống thuần client-side thì dễ bị gian lận. Do đó, dự án cần xây dựng một nền tảng thanh toán **serverless**, vừa có khả năng xử lý traffic lớn, vừa đảm bảo an toàn tuyệt đối, đồng thời kiểm soát chặt chẽ chi phí.

Dự án xây dựng hệ thống thanh toán tích hợp MoMo trên **AWS Serverless**, kết hợp **ReactJS + Electron** (hoặc Web) phía client. Mục tiêu cốt lõi là tạo ra một hệ thống thanh toán nhanh, an toàn, minh bạch và dễ mở rộng. Các mục tiêu cụ thể bao gồm:

- Xử lý nhanh việc tạo Payment URL và nhận webhook từ MoMo;
- Đảm bảo không xảy ra gian lận (double payment, replay attack, fake transaction);
- Xử lý bất đồng bộ và retry đáng tin cậy khi webhook thất bại;
- Cung cấp dashboard quản lý giao dịch thời gian thực cho Merchant;
- Xây dựng hệ thống thông báo (Email/SMS) đáng tin cậy;
- Đảm bảo chi phí vận hành tối ưu ngay cả khi traffic tăng đột biến;
- Hỗ trợ AI/ML phát hiện gian lận và phân tích hành vi giao dịch.

## Đối tượng Mục tiêu

### Merchant (Chủ cửa hàng / Doanh nghiệp)

Cần một hệ thống thanh toán ổn định, dễ tích hợp, có dashboard rõ ràng để theo dõi giao dịch thời gian thực, báo cáo doanh thu và quản lý hoàn tiền. Họ đặc biệt quan tâm đến độ tin cậy của webhook và khả năng xử lý lỗi tự động.

### Khách hàng cuối

Mong muốn quá trình thanh toán nhanh chóng, an toàn, không bị gián đoạn và có biên lai rõ ràng. Họ cần cảm giác tin tưởng rằng giao dịch của mình được xử lý đúng và có thể tra cứu dễ dàng.

### Giá trị Chung

Cả hai nhóm đều cần một hệ thống **nhanh – an toàn – minh bạch**. Dự án tập trung vào việc làm cho mọi giao dịch đều có thể kiểm tra, dễ theo dõi và có cơ chế xử lý lỗi tự động, từ đó xây dựng lòng tin lâu dài cho người dùng.

## Các Vấn đề Kỹ thuật Cốt lõi

### 1. Ngăn chặn gian lận thanh toán

Webhook IPN từ MoMo có thể bị replay, giả mạo hoặc gửi nhiều lần. Hệ thống phải kiểm tra chữ ký (signature), idempotency key, thời gian hết hạn và trạng thái giao dịch trên server trước khi cập nhật. Không cho phép cập nhật trạng thái nhiều lần hoặc double credit.

### 2. Xử lý bất đồng bộ và Retry đáng tin cậy

Webhook có thể fail do mạng hoặc lỗi tạm thời. Hệ thống phải sử dụng **SQS + DLQ + Retry mechanism** để đảm bảo mọi giao dịch cuối cùng đều được xử lý đúng, ngay cả khi có sự cố.

### 3. Tính toàn vẹn dữ liệu và Consistency

Giao dịch, số dư, biên lai, audit log phải luôn nhất quán. Sử dụng conditional update, transaction, idempotent processing và server-side validation để tránh double payment hoặc mất dữ liệu.

### 4. Hiệu suất và Chi phí Cloud

Hệ thống phải scale tự động khi traffic cao (Black Friday, sự kiện) nhưng vẫn giữ chi phí thấp khi traffic thấp. Sử dụng Serverless (Lambda, API Gateway, DynamoDB, SQS, SNS) kết hợp caching, batch processing và TTL để tối ưu chi phí.

### 5. Giám sát và Observability

Mọi giao dịch, webhook, retry và lỗi cần được theo dõi thời gian thực qua CloudWatch, X-Ray, Alarm và SNS notification để team có thể phản ứng nhanh.

## Yêu cầu Ngang (Cross-cutting Requirements)

- **Bảo mật:** Xác thực Cognito, JWT, WAF, IAM least privilege, mã hóa dữ liệu nhạy cảm.
- **Observability:** Structured logging, metrics, tracing, cost alert.
- **Khả mở & Bảo trì:** Infrastructure as Code (SAM/CDK), domain-driven design.
- **Tuân thủ:** Xử lý dữ liệu thanh toán an toàn, audit log đầy đủ.

## Giá trị Dự án Mong đợi

Dự án MoMoPay AWS là một case study thực tế về xây dựng hệ thống thanh toán serverless trên AWS, đảm bảo **an toàn – nhanh chóng – tối ưu chi phí** và có khả năng mở rộng cao. Hệ thống không chỉ xử lý thanh toán mà còn cung cấp nền tảng vững chắc cho các tính năng nâng cao sau này như Fraud Detection bằng AI, Subscription, Refund automation, v.v.
