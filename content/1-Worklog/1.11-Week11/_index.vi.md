---
title: "Worklog Tuần 11"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.11. </b> "
---
### Mục tiêu tuần 11:

* Triển khai hệ thống Website Quản lý Phòng khám Nha khoa lên AWS.
* Cấu hình máy chủ Amazon EC2 để chạy ứng dụng.
* Tìm hiểu và tích hợp Amazon SNS để gửi thông báo.
* Giám sát hệ thống bằng Amazon CloudWatch.
* Kiểm thử và tối ưu hệ thống sau khi triển khai.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2 | - Tạo Amazon EC2 Instance <br> - Cấu hình Security Group và Key Pair <br> - Kết nối đến EC2 thông qua SSH | 29/06/2026 | 29/06/2026 | <https://docs.aws.amazon.com/ec2/> |
| 3 | - Cài đặt Java, Git và các công cụ cần thiết trên EC2 <br> - Triển khai Backend Spring Boot lên EC2 <br> - Kiểm tra ứng dụng hoạt động trên máy chủ | 30/06/2026 | 30/06/2026 | <https://spring.io/> |
| 4 | - Triển khai Frontend React <br> - Cấu hình Nginx phục vụ giao diện <br> - Kiểm tra kết nối giữa Frontend và Backend | 01/07/2026 | 01/07/2026 | <https://react.dev/> |
| 5 | - Tìm hiểu Amazon SNS <br> - Tạo SNS Topic <br> - Cấu hình gửi thông báo Email khi có sự kiện trong hệ thống | 02/07/2026 | 02/07/2026 | <https://docs.aws.amazon.com/sns/> |
| 6-7 | - Tìm hiểu Amazon CloudWatch <br> - Theo dõi trạng thái EC2 và DynamoDB <br> - Kiểm thử toàn bộ hệ thống sau khi triển khai <br> - Khắc phục các lỗi phát sinh | 03/07/2026 | 04/07/2026 | <https://docs.aws.amazon.com/cloudwatch/> |

### Kết quả đạt được tuần 11:

* Triển khai thành công Website Quản lý Phòng khám Nha khoa lên Amazon EC2.

* Hoàn thành cấu hình:
  * Amazon EC2.
  * Security Group.
  * Key Pair.

* Triển khai thành công Backend Spring Boot trên máy chủ EC2.

* Hoàn thành triển khai Frontend React và cấu hình Nginx.

* Tích hợp Amazon SNS để gửi thông báo qua Email.

* Theo dõi hoạt động của hệ thống bằng Amazon CloudWatch.

* Kiểm thử thành công luồng hoạt động giữa React, Spring Boot và Amazon DynamoDB sau khi triển khai.

* Khắc phục các lỗi phát sinh và tối ưu hiệu năng của hệ thống.

* Hoàn thiện môi trường triển khai và sẵn sàng cho giai đoạn nghiệm thu dự án.