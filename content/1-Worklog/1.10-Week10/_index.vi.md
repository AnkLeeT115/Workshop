---
title: "Worklog Tuần 10"
date: 2024-01-01
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

# Nhật ký công việc tuần 10

## Mục tiêu tuần 10

- Xây dựng nền tảng backend cho hệ thống **Genuine Scale Models E-commerce Backend** sử dụng kiến trúc Serverless trên AWS.
- Thiết kế mô hình dữ liệu NoSQL với Amazon DynamoDB và triển khai các chức năng backend bằng AWS Lambda.
- Phát triển các chức năng thương mại điện tử cơ bản bao gồm quản lý sản phẩm, quản lý tồn kho và xử lý đơn hàng.

## Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Thiết kế cấu trúc cơ sở dữ liệu NoSQL sử dụng **Amazon DynamoDB**.<br>- Xây dựng mô hình dữ liệu cho:<br>&emsp;+ Sản phẩm (Products)<br>&emsp;+ Người dùng (Users)<br>&emsp;+ Đơn hàng (Orders)<br>&emsp;+ Kho hàng (Inventory)<br>- Xác định Partition Key và Access Pattern để tối ưu truy vấn dữ liệu. | 22/06/2026 | 22/06/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 3 | - Khởi tạo và cấu hình các bảng DynamoDB.<br>- Thêm dữ liệu mẫu cho sản phẩm mô hình chính hãng bao gồm:<br>&emsp;+ Tên mô hình<br>&emsp;+ Thương hiệu<br>&emsp;+ Danh mục<br>&emsp;+ Giá sản phẩm<br>&emsp;+ Trạng thái xác minh chính hãng<br>- Kiểm tra các thao tác đọc/ghi dữ liệu. | 23/06/2026 | 23/06/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 4 | - Xây dựng backend bằng **AWS Lambda**.<br>- Phát triển các Lambda Function phục vụ:<br>&emsp;+ Lấy danh sách sản phẩm<br>&emsp;+ Thêm sản phẩm mới<br>&emsp;+ Cập nhật thông tin sản phẩm<br>&emsp;+ Kiểm tra số lượng tồn kho<br>- Tổ chức source code theo mô hình phát triển Serverless. | 24/06/2026 | 24/06/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 5 | - Cấu hình **Amazon API Gateway** kết nối với Lambda Function.<br>- Xây dựng các REST API phục vụ:<br>&emsp;+ Quản lý sản phẩm<br>&emsp;+ Quản lý tồn kho<br>&emsp;+ Xử lý đơn hàng<br>- Kiểm tra request và response của API. | 25/06/2026 | 25/06/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 6 | - Triển khai lưu trữ hình ảnh sản phẩm bằng **Amazon S3**.<br>- Xây dựng quy trình upload hình ảnh sản phẩm.<br>- Kiểm tra tích hợp giữa S3, Lambda và DynamoDB.<br>- Rà soát kiến trúc backend và cải thiện cấu trúc mã nguồn. | 26/06/2026 | 26/06/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |

## Kết quả đạt được tuần 10

- Thiết kế thành công mô hình dữ liệu DynamoDB cho hệ thống thương mại điện tử:
  - Xây dựng cấu trúc dữ liệu cho sản phẩm, người dùng, đơn hàng và kho hàng.
  - Xác định Partition Key và Access Pattern phù hợp với mô hình NoSQL.

- Hoàn thiện cấu hình các bảng DynamoDB:
  - Thêm dữ liệu mẫu cho các sản phẩm mô hình chính hãng.
  - Quản lý các thông tin:
    - Tên mô hình.
    - Thương hiệu.
    - Danh mục.
    - Giá sản phẩm.
    - Trạng thái chính hãng.
    - Số lượng tồn kho.

- Xây dựng logic backend bằng **AWS Lambda**:
  - Triển khai các chức năng quản lý sản phẩm.
  - Xây dựng chức năng kiểm tra tồn kho.
  - Chuẩn bị nền tảng xử lý đơn hàng.

- Xây dựng REST API với **Amazon API Gateway**:
  - Kết nối API endpoint với Lambda Function.
  - Kiểm tra quá trình giao tiếp giữa client và backend.

- Tích hợp **Amazon S3** để quản lý hình ảnh sản phẩm:
  - Lưu trữ hình ảnh mô hình.
  - Kết nối quy trình upload ảnh với Lambda và DynamoDB.

- Nắm được quy trình phát triển backend Serverless:
  - Thiết kế dữ liệu DynamoDB.
  - Xử lý nghiệp vụ bằng Lambda.
  - Xây dựng API với API Gateway.
  - Quản lý dữ liệu và file với Amazon S3.