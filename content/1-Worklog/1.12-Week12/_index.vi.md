---
title: "Worklog Tuần 12"
date: 2024-01-01
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

# Week 12 Worklog

## Mục tiêu tuần 12:

- Hoàn thiện các chức năng backend liên quan đến quản lý sản phẩm, đơn hàng và lưu trữ hình ảnh trên nền tảng Serverless AWS.
- Phát triển các API tìm kiếm, lọc sản phẩm và quản lý đánh giá cho hệ thống thương mại điện tử bán mô hình chính hãng.
- Hoàn thiện chức năng xác thực người dùng, phân quyền khách hàng và quản trị viên.

## Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Phát triển module quản lý đơn hàng.<br>- Xây dựng quy trình tạo đơn hàng, kiểm tra tồn kho và lưu trữ thông tin giao dịch.<br>- Tích hợp Amazon DynamoDB để quản lý dữ liệu đơn hàng và trạng thái xử lý. | 13/07/2026 | 13/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 3 | - Phát triển API quản lý đánh giá sản phẩm.<br>- Xây dựng luồng xử lý đánh giá từ khi người dùng gửi dữ liệu đến khi lưu trữ vào hệ thống.<br>- Viết integration test cho các trường hợp dữ liệu hợp lệ, không hợp lệ và lỗi hệ thống. | 14/07/2026 | 14/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 4 | - Phát triển chức năng tìm kiếm và lọc danh mục sản phẩm.<br>- Xây dựng bộ lọc theo tên mô hình, thương hiệu, danh mục, giá và trạng thái sản phẩm chính hãng.<br>- Kiểm tra kết quả trả về từ API và đảm bảo dữ liệu tìm kiếm chính xác. | 15/07/2026 | 15/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 5 | - Tích hợp Amazon Cognito cho chức năng xác thực và phân quyền người dùng.<br>- Xây dựng cơ chế quản lý quyền truy cập giữa khách hàng và quản trị viên.<br>- Hoàn thiện các giao diện chính như Home, Product Catalog, Favorites và User Profile. | 16/07/2026 | 16/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 6 | - Thực hiện kiểm thử tổng thể hệ thống thương mại điện tử.<br>- Khắc phục lỗi phát sinh trong quá trình kiểm thử.<br>- Tối ưu hiệu năng API, dọn dẹp mã nguồn và chuẩn bị phiên bản hoàn thiện của dự án. | 17/07/2026 | 17/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |

## Kết quả đạt được tuần 12:

- Hoàn thiện module quản lý đơn hàng:
  - Xây dựng chức năng tạo đơn hàng.
  - Kiểm tra tồn kho trước khi đặt hàng.
  - Lưu trữ thông tin đơn hàng và trạng thái xử lý bằng Amazon DynamoDB.

- Tích hợp Amazon S3:
  - Quản lý hình ảnh sản phẩm mô hình chính hãng.
  - Hỗ trợ lưu trữ tài nguyên phục vụ catalog sản phẩm.

- Hoàn thành phát triển API đánh giá sản phẩm:
  - Xử lý quy trình gửi và lưu đánh giá từ người dùng.
  - Kiểm thử các trường hợp dữ liệu hợp lệ và lỗi hệ thống.

- Hoàn thiện chức năng tìm kiếm và lọc sản phẩm:
  - Tìm kiếm theo tên mô hình.
  - Lọc theo thương hiệu, danh mục, giá và trạng thái chính hãng.
  - Đảm bảo API trả về dữ liệu chính xác.

- Tích hợp Amazon Cognito:
  - Xác thực tài khoản người dùng.
  - Quản lý quyền truy cập giữa khách hàng và quản trị viên.
  - Bảo vệ các API quan trọng của hệ thống.

- Hoàn thiện giao diện ứng dụng:
  - Cập nhật các màn hình Home, Product Catalog, Favorites và User Profile.
  - Điều chỉnh giao diện theo thiết kế chung.

- Thực hiện kiểm thử và tối ưu hệ thống:
  - Sửa lỗi phát sinh trong quá trình kiểm thử.
  - Cải thiện hiệu năng API.
  - Refactor và chuẩn hóa mã nguồn trước khi hoàn thành dự án.