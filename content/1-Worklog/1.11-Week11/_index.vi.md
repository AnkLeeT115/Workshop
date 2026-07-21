---
title: "Worklog Tuần 11"
date: 2024-01-01
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

# Nhật ký công việc tuần 11

## Mục tiêu tuần 11

- Triển khai cơ chế xác thực và phân quyền người dùng bằng **Amazon Cognito và JWT**.
- Xây dựng chức năng xử lý đơn hàng và kiểm tra tồn kho cho hệ thống thương mại điện tử.
- Kiểm thử API và cải thiện quy trình CI phục vụ triển khai Serverless Backend.

## Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Cấu hình **Amazon Cognito User Pool** cho khách hàng và quản trị viên.<br>- Xây dựng luồng đăng ký và đăng nhập người dùng.<br>- Triển khai tạo và xác thực JWT token cho các request cần xác thực. | 06/07/2026 | 06/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 3 | - Xây dựng cơ chế phân quyền sử dụng JWT và Cognito Groups.<br>- Cấu hình quyền truy cập cho chức năng khách hàng và quản trị viên.<br>- Kiểm tra các API được bảo vệ thông qua API Gateway. | 07/07/2026 | 07/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 4 | - Xây dựng quy trình xử lý đơn hàng bằng AWS Lambda.<br>- Triển khai các chức năng:<br>&emsp;+ Tạo đơn hàng<br>&emsp;+ Kiểm tra số lượng sản phẩm<br>&emsp;+ Cập nhật tồn kho<br>&emsp;+ Cập nhật trạng thái đơn hàng | 08/07/2026 | 08/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 5 | - Viết kiểm thử API cho các chức năng sản phẩm, tồn kho và đơn hàng.<br>- Kiểm tra các trường hợp xác thực:<br>&emsp;+ Người dùng hợp lệ<br>&emsp;+ Token không hợp lệ<br>&emsp;+ Truy cập không có quyền | 09/07/2026 | 09/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 6 | - Cải thiện quy trình CI cho ứng dụng Serverless.<br>- Cấu hình tự động chạy kiểm thử trước khi triển khai.<br>- Rà soát Lambda Function, API Gateway và hoạt động với DynamoDB. | 10/07/2026 | 10/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |

## Kết quả đạt được tuần 11

- Hoàn thiện cơ chế xác thực bằng **Amazon Cognito**:
  - Xây dựng luồng đăng ký và đăng nhập cho khách hàng, quản trị viên.
  - Tích hợp xác thực JWT token.
  - Bảo vệ các API backend bằng cơ chế phân quyền.

- Hoàn thiện chức năng quản lý quyền truy cập:
  - Sử dụng Cognito Groups để quản lý vai trò.
  - Phân biệt quyền giữa khách hàng và quản trị viên.

- Xây dựng chức năng xử lý đơn hàng:
  - Tạo workflow đặt hàng bằng AWS Lambda.
  - Kiểm tra tình trạng sản phẩm trước khi đặt hàng.
  - Cập nhật số lượng tồn kho sau khi giao dịch thành công.
  - Quản lý trạng thái đơn hàng.

- Hoàn thành kiểm thử backend:
  - Kiểm thử Product API.
  - Kiểm thử Inventory API.
  - Kiểm thử Order API.
  - Kiểm tra các trường hợp xác thực và phân quyền.

- Cải thiện quy trình phát triển:
  - Tích hợp kiểm thử tự động vào CI pipeline.
  - Nâng cao độ ổn định khi triển khai Serverless Backend.
  - Kiểm tra sự kết nối giữa Lambda, API Gateway và DynamoDB.