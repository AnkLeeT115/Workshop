---
title: "Bản đề xuất"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# PrimeScale - Nền tảng Thương mại Điện tử Mô Hình Chính Hãng
## Giải pháp AWS Serverless cho Kinh doanh Mô hình Chính Hãng

### 1. Tóm tắt điều hành  
PrimeScale được thiết kế dành cho các cửa hàng và cộng đồng yêu thích mô hình chính hãng (Gundam, Bandai, Warhammer, Figure...) tại Việt Nam. Nền tảng hỗ trợ quản lý catalog sản phẩm, xử lý đơn hàng, theo dõi inventory thời gian thực và phân phối hình ảnh chất lượng cao.

Hệ thống được xây dựng hoàn toàn trên kiến trúc **AWS Serverless**, giúp tiết kiệm chi phí, dễ dàng mở rộng và bảo trì. Frontend sử dụng React/Next.js, backend qua AWS Lambda, và giới hạn quyền truy cập thông qua Amazon Cognito.

### 2. Tuyên bố vấn đề  
**Vấn đề hiện tại**  
Thị trường mô hình chính hãng đang gặp nhiều thách thức:

* Khó phân biệt hàng chính hãng và replica.
* Quản lý inventory thủ công dễ sai sót, đặc biệt vào mùa ra mắt model mới.
* Trải nghiệm mua sắm online chưa tốt, tải hình ảnh chậm và thiếu xác thực sản phẩm.
* Chi phí vận hành server cao, khó scale khi traffic tăng.
* Chủ shop khó quản lý đơn hàng và stock thời gian thực.

**Giải pháp**  
PrimeScale sử dụng kiến trúc AWS Serverless hiện đại với S3 + CloudFront cho hình ảnh, API Gateway & Lambda xử lý logic, DynamoDB lưu trữ dữ liệu, và Cognito quản lý xác thực. Người dùng có thể duyệt sản phẩm chính hãng, đặt hàng, trong khi admin quản lý inventory dễ dàng. Các tính năng chính bao gồm tìm kiếm nhanh, thanh toán an toàn và cập nhật stock thời gian thực.

**Lợi ích và hoàn vốn đầu tư (ROI)**  
Giải pháp tạo nền tảng đáng tin cậy để kinh doanh mô hình chính hãng, nâng cao trải nghiệm khách hàng và giảm công việc thủ công. Chi phí vận hành hàng tháng ước tính dưới 50 USD. Không yêu cầu đầu tư phần cứng thêm. Thời gian hoàn vốn dự kiến 3–6 tháng nhờ tăng doanh số, giảm chi phí vận hành và xây dựng lòng tin khách hàng.

### 3. Kiến trúc giải pháp  
PrimeScale áp dụng kiến trúc AWS Serverless tối ưu cho thương mại điện tử. Hình ảnh sản phẩm được phục vụ qua CloudFront, đơn hàng và inventory được xử lý bởi Lambda, dữ liệu lưu trữ trong DynamoDB đảm bảo hiệu suất cao và khả năng mở rộng.

![Kiến trúc PrimeScale](/images/2-Proposal/primescale_architecture.png)

**Dịch vụ AWS sử dụng**  
- **Amazon S3 + CloudFront**: Lưu trữ và phân phối hình ảnh sản phẩm chất lượng cao.  
- **AWS Lambda**: Xử lý logic nghiệp vụ (sản phẩm, đơn hàng, inventory).  
- **Amazon API Gateway**: Cung cấp API cho frontend.  
- **Amazon DynamoDB**: Lưu trữ dữ liệu sản phẩm, đơn hàng, inventory.  
- **Amazon Cognito**: Xác thực và quản lý người dùng.  
- **Amazon SES/SNS**: Gửi email/SMS thông báo đơn hàng.

**Thiết kế thành phần**  
- **Frontend**: Ứng dụng web React/Next.js (tương thích mobile).  
- **Backend**: Các hàm Lambda serverless.  
- **Lưu trữ**: S3 cho hình ảnh, DynamoDB cho dữ liệu có cấu trúc.  
- **Xác thực**: Cognito cho khách hàng và admin.  
- **Luồng dữ liệu**: Người dùng truy cập qua CloudFront → Gọi API → Lambda → DynamoDB.

### 4. Triển khai kỹ thuật  
**Các giai đoạn triển khai**  
Dự án được chia thành các giai đoạn rõ ràng:  

1. **Nghiên cứu & Thiết kế kiến trúc**: Thu thập yêu cầu và vẽ architecture (1–2 tuần).  
2. **Tính toán chi phí & Kiểm tra khả thi**: Sử dụng AWS Pricing Calculator (Tháng 1).  
3. **Tối ưu kiến trúc**: Điều chỉnh để giảm chi phí và tăng hiệu suất (Tháng 1–2).  
4. **Phát triển, Kiểm thử, Triển khai**: Xây dựng frontend, backend, tích hợp, test và deploy staging (Tháng 2–3).  

**Yêu cầu kỹ thuật**  
- **Frontend**: React hoặc Next.js.  
- **Backend**: Node.js/Python với AWS SAM hoặc CDK.  
- **Database**: DynamoDB với indexing tối ưu.  
- **Tích hợp**: Signed URL cho upload ảnh, JWT từ Cognito.

### 5. Lộ trình & Mốc triển khai  
- **Chuẩn bị (Tuần 0)**: Thu thập yêu cầu và thiết kế ban đầu.  
- **Tháng 1**: Thiết lập môi trường, xác thực, quản lý sản phẩm.  
- **Tháng 2**: Quy trình đặt hàng, inventory, tích hợp frontend.  
- **Tháng 3**: Portal admin, kiểm thử, CI/CD, triển khai staging.  
- **Sau triển khai**: Giám sát, tối ưu và mở rộng tính năng.

### 6. Ước tính ngân sách  

**Chi phí hạ tầng (Hàng tháng - Staging/MVP)**  
- AWS Lambda + API Gateway: ~10–25 USD  
- Amazon S3 + CloudFront: ~5–15 USD  
- Amazon DynamoDB: ~5–15 USD  
- Amazon Cognito: ~5–10 USD  
- Khác (SES/SNS): ~2–5 USD  

**Tổng**: ~25–80 USD/tháng (tùy theo lượng sử dụng).  
**Giai đoạn phát triển**: Gần như 0 USD (sử dụng Free Tier).  

### 7. Đánh giá rủi ro  
**Ma trận rủi ro**  
- Độ trễ Lambda: Ảnh hưởng trung bình, xác suất thấp.  
- Vượt ngân sách: Ảnh hưởng trung bình, xác suất thấp.  
- Bảo mật dữ liệu: Ảnh hưởng cao, xác suất thấp.  
- Thay đổi yêu cầu: Ảnh hưởng trung bình, xác suất trung bình.

**Chiến lược giảm thiểu**  
- Tối ưu code và thêm caching.  
- Đặt cảnh báo ngân sách AWS.  
- Áp dụng nguyên tắc least privilege và best practices của Cognito.

**Kế hoạch dự phòng**  
- Quay về quy trình thủ công tạm thời nếu cần.  
- Sử dụng Infrastructure as Code để khôi phục nhanh.

### 8. Kết quả kỳ vọng  
**Cải tiến kỹ thuật**: Nền tảng thương mại điện tử serverless hoàn chỉnh với tốc độ tải hình ảnh nhanh, xác thực an toàn và quản lý inventory thời gian thực. Dễ dàng mở rộng từ MVP lên production.

**Giá trị dài hạn**: Nền tảng sẵn sàng đưa vào sử dụng thực tế cho cửa hàng mô hình chính hãng, mã nguồn chất lượng cao có thể tái sử dụng, và là dự án thực tế xuất sắc để thể hiện kỹ năng AWS Serverless.