---
title : "Giới thiệu"
date : 2023-10-25 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

#### Giới thiệu hệ thống

Workshop này sẽ hướng dẫn bạn xây dựng và triển khai một **website thương mại điện tử động** trên nền tảng serverless hiện đại của AWS.  
Bạn sẽ sử dụng các thành phần chủ chốt như **API Gateway**, **AWS Certificate Manager**, **IAM**, **S3**, **Lambda**, **CloudFormation**, **CloudFront**, **DynamoDB**, **Route 53**, **CloudWatch** và **SAM CLI** để tự động hoá, mở rộng và tối ưu chi phí cho hệ thống.

#### Kiến trúc tổng thể

Dưới đây là kiến trúc tổng thể của hệ thống.  
     ![Kiến trúc tổng thể](/images/fcjfashionshop_drawio.png)

- **Frontend:** Sử dụng theme Hugo, lưu trữ tĩnh trên Amazon S3 và phân phối qua CloudFront.
- **Backend:** Giao tiếp qua RESTful API với API Gateway, xử lý nghiệp vụ bằng AWS Lambda.
- **Cơ sở dữ liệu:** Sử dụng DynamoDB để lưu trữ dữ liệu động, dễ dàng mở rộng.
- **Quản lý hạ tầng:** CloudFormation tự động tạo và cấu hình tài nguyên AWS; sử dụng SAM CLI để triển khai và tự động hóa serverless.
- **Tên miền & Quản lý hoạt động:** Route 53 quản lý tên miền/DNS; CloudWatch theo dõi, ghi nhận log và cảnh báo cho toàn bộ hệ thống; AWS Certificate Manager cấp SSL miễn phí cho website.

#### Sơ đồ luồng dữ liệu

Sơ đồ sau minh họa luồng dữ liệu chính và tương tác giữa các thành phần hệ thống.  
*(Chèn sơ đồ luồng dữ liệu hoặc sequence diagram tại đây)*

#### Danh sách dịch vụ AWS sử dụng

- **API Gateway:** Tạo REST API cho giao tiếp frontend-backend.
- **S3:** Lưu trữ website tĩnh và tài nguyên website.
- **Lambda:** Xử lý logic backend serverless.
- **DynamoDB:** Cơ sở dữ liệu NoSQL động, mở rộng dễ dàng.
- **CloudFormation:** Quản lý hạ tầng dưới dạng mã (IaC).
- **Route 53:** Đăng ký và cấu hình tên miền, DNS.
- **CloudFront:** Phân phối nội dung toàn cầu (CDN), tăng tốc truy cập và bảo mật.
- **AWS Certificate Manager:** Cấp và quản lý chứng chỉ SSL miễn phí.
- **IAM:** Quản lý tài khoản, phân quyền truy cập tài nguyên AWS.
- **CloudWatch:** Giám sát, log, cảnh báo hệ thống.
- **SAM CLI:** Tự động hóa triển khai tài nguyên serverless.

#### Tính năng chính của website

- Kiến trúc **serverless hoàn toàn trên AWS**.
- Triển khai website động, bảo mật, mở rộng tự động.
- Giao diện thân thiện với Hugo.
- Backend động sử dụng RESTful API qua API Gateway & Lambda.
- Cơ sở dữ liệu động với DynamoDB.
- Xử lý dữ liệu thời gian thực bằng Lambda & DynamoDB.
- Tích hợp giám sát, logging, cấu hình DNS, CDN & SSL tự động.
- Hạ tầng dưới dạng mã (IaC) với CloudFormation & SAM CLI.
