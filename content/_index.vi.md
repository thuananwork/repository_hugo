---
title: "Website thương mại điện tử"
date: 2025-07-06
weight: 10
chapter: false
---

# Xây dựng website thương mại điện tử động với AWS Serverless

### Tổng quan

Trong Workshop này, bạn sẽ triển khai một **website thương mại điện tử động** sử dụng framework Hugo trên nền tảng điện toán đám mây AWS. Bạn sẽ học cách chuẩn bị môi trường, cấu hình tài khoản AWS, xây dựng website với Hugo, và triển khai toàn bộ hệ thống trên các dịch vụ chính của AWS như API Gateway, S3, Lambda, CloudFormation, DynamoDB, Route 53, CloudWatch, đồng thời sử dụng SAM CLI để tự động hoá quá trình triển khai.

Ngoài ra, bạn sẽ được hướng dẫn **thiết lập một trang website tĩnh trên S3 với SSL (HTTPS) đầy đủ** để tăng bảo mật, giúp website phục vụ tốt hơn cho khách hàng toàn cầu.

![Kiến trúc tổng thể](/images/fcjfashionshop_drawio.png)

### Mục tiêu của Workshop

- Hiểu và thao tác thành thạo các công cụ AWS cần thiết cho một dự án website động.
- Biết cách chuẩn bị, cài đặt, cấu hình môi trường phát triển cho dự án Hugo.
- Xây dựng, đóng gói và triển khai website động với Hugo kết hợp các dịch vụ serverless hiện đại của AWS.
- Thiết kế và triển khai (deploy) với API Gateway, xử lý logic động bằng Lambda, lưu trữ dữ liệu trên DynamoDB, và quản lý website động trên S3.
- Sử dụng CloudFormation để tự động tạo và cấu hình tài nguyên AWS, theo dõi và giám sát hoạt động hệ thống với CloudWatch.
- **Thiết lập website tĩnh trên S3 có tích hợp SSL (HTTPS) với AWS Certificate Manager và CloudFront.**
- Cấu hình tên miền và phân giải DNS với Route 53 để truy cập website động qua internet.
- Ứng dụng quy trình DevOps tự động hóa triển khai và vận hành website trên nền tảng AWS một cách hiệu quả.

### Kiến thức thu được sau Workshop

Sau khi hoàn thành Workshop này, bạn sẽ:

- Hiểu rõ kiến trúc và quy trình triển khai một website thương mại điện tử động trên nền tảng AWS.
- Học được cách sử dụng các dịch vụ AWS như API Gateway, S3, Lambda, CloudFormation, DynamoDB, Route 53, CloudWatch và SAM CLI trong một dự án thực tế.
- Biết cách xây dựng, đóng gói và triển khai website động với Hugo, kết nối frontend với backend qua API Gateway và Lambda.
- **Biết cách thiết lập website tĩnh trên S3, sử dụng CloudFront và AWS Certificate Manager để kích hoạt HTTPS cho website.**
- Thực hành quản lý dữ liệu động với DynamoDB, quản lý hạ tầng tự động bằng CloudFormation.
- Cấu hình tên miền với Route 53, giám sát hệ thống và log ứng dụng qua CloudWatch.
- Sẵn sàng áp dụng kiến thức vào các dự án thực tế, các bài toán về website động, serverless, hoặc DevOps trên AWS.

### Nội dung
 1. [Giới thiệu](1-introduce/)
 2. [Các bước chuẩn bị](2-Prerequiste/)
 3. [Triển khai backend](3-deployBackend/)
 4. [Kiểm thử API backend với Postman](4-testBackendApi/)
 5. [Triển khai frontend](5-deployFrontend/)
 6. [Thiết lập trang web SSL S3 Static](6-ssl-s3-static/)
 7. [Demo và chạy thử dự án](7-demo/)
 8. [Dọn dẹp tài nguyên](8-cleanup/)
