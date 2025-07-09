---
title : "Chuẩn bị môi trường"
date : 2023-10-25
weight : 2
chapter : false
pre : " <b> 2 </b> "
---


Trước khi bắt đầu triển khai website thương mại điện tử động sử dụng các dịch vụ AWS như **API Gateway**, **S3**, **Lambda**, **CloudFormation**, **DynamoDB**, **Route 53**, **CloudWatch** và **SAM CLI**, bạn cần hoàn thành một số bước chuẩn bị môi trường cơ bản. Những công cụ và dịch vụ này sẽ giúp bạn triển khai ứng dụng một cách nhanh chóng, an toàn và hiệu quả.

Trong phần này, bạn sẽ thực hiện các bước cài đặt và cấu hình môi trường phát triển cho cả frontend và backend của dự án:

- **Cài đặt NodeJS và Yarn**: Để hỗ trợ việc xây dựng và quản lý frontend.
- **Cài đặt SAM CLI**: Để triển khai backend serverless trên AWS.
- **Tạo tài khoản AWS và cấu hình IAM**: Để thiết lập quyền truy cập và bảo mật cho dự án trên AWS.
- **Cấu hình Google OAuth2 Client ID và Client Secret**: Để tích hợp đăng nhập Google bảo mật cho hệ thống.

Các bước chuẩn bị này sẽ đảm bảo rằng bạn có môi trường đầy đủ và hoạt động chính xác trước khi tiến hành triển khai các dịch vụ AWS cho dự án của mình.

⚠️ **Lưu ý**: Hãy chắc chắn rằng bạn đã cài đặt đầy đủ các công cụ trước khi bắt đầu làm việc với các dịch vụ AWS. Nếu không, bạn có thể gặp phải sự cố trong quá trình triển khai.

### Nội dung
- [Cài đặt NodeJS](2.1-installNodejs/)
- [Cài đặt Yarn cho frontend](2.2-installYarn/)
- [Cài đặt SAM CLI cho backend](2.3-installSamcli/)
- [Tạo tài khoản & cấu hình IAM](2.4-createIam/)
- [Tạo Google OAuth2 Project](2.5-create-google-oauth2/)
