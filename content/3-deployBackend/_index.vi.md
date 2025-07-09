---
title : "Triển khai backend"
date : 2023-10-25
weight : 3
chapter : false
pre : " <b> 3. </b> "
---


Triển khai backend cho website thương mại điện tử động được thực hiện bằng cách sử dụng **AWS SAM CLI** kết hợp với **CloudFormation**. Với các công cụ này, bạn sẽ dễ dàng triển khai các dịch vụ serverless như **API Gateway**, **Lambda**, và **DynamoDB**.

#### Các công cụ chính được sử dụng:
- **SAM CLI**: Công cụ dòng lệnh giúp phát triển, kiểm tra và triển khai các ứng dụng serverless. SAM CLI giúp bạn dễ dàng triển khai API Gateway, Lambda function, và các tài nguyên serverless khác trên AWS.
- **CloudFormation**: Dịch vụ quản lý hạ tầng dưới dạng mã (Infrastructure as Code), cho phép bạn tự động hóa việc triển khai và quản lý các tài nguyên AWS.

Trong phần này, bạn sẽ học cách triển khai backend serverless cho website của mình bằng SAM CLI, bao gồm việc tạo các tài nguyên như **API Gateway**, **Lambda**, và **DynamoDB**.

{{% notice info %}}
Lưu ý: Hãy đảm bảo rằng bạn đã hoàn thành các bước chuẩn bị môi trường (bao gồm cài đặt SAM CLI và cấu hình AWS IAM) trước khi bắt đầu triển khai backend.
{{% /notice %}}

### Nội dung
- [Triển khai backend bằng SAM CLI/CloudFormation](3.1-deploy-backend/)
- [Kiểm tra trạng thái và log backend sau khi triển khai](3.2-check-status-log-backend/)
