---
title : "Triển khai backend bằng SAM CLI/CloudFormation"
date : 2023-10-25
weight : 4
chapter : false
pre : " <b> 3.1 </b> "
---

#### Triển khai Backend bằng SAM CLI/CloudFormation

Trong phần này, bạn sẽ triển khai backend cho website thương mại điện tử động của mình bằng **SAM CLI** và **CloudFormation**. Chúng ta sẽ sử dụng file **`template.yaml`** có sẵn trong dự án để tự động tạo các tài nguyên như **API Gateway**, **Lambda**, và **DynamoDB**.

#### Bước 1: Cấu hình AWS CLI

Trước khi bắt đầu sử dụng **SAM CLI** để triển khai, bạn cần phải cấu hình **AWS CLI** với các thông tin đăng nhập của tài khoản AWS. Điều này giúp **SAM CLI** có thể sử dụng các quyền truy cập đã được cấp cho IAM User của bạn.

1. **Chạy lệnh `aws configure`**:
   - Mở terminal và nhập lệnh sau để cấu hình AWS CLI:

          aws configure
   
2. **Nhập thông tin cấu hình**:
   - **AWS Access Key ID**: Nhập **Access Key ID** mà bạn đã tạo khi tạo IAM User.
   - **AWS Secret Access Key**: Nhập **Secret Access Key** tương ứng với Access Key ID.
   - **Default region name**: Nhập `ap-southeast-1` (cho Singapore).
   - **Default output format**: Bạn có thể nhập `json` , hoặc để mặc định `None`.
![Error image](/images/aws_configure.png)

   - Sau khi hoàn tất cấu hình, AWS CLI sẽ lưu thông tin cấu hình trong file `~/.aws/credentials` (Linux/macOS) hoặc `C:\Users\<username>\.aws\credentials` (Windows).


#### Bước 2: Triển khai Backend bằng SAM CLI

1. **Kiểm tra file `template.yaml`**:
   - Nếu bạn chưa có file **`template.yaml`**, hãy kiểm tra trong thư mục dự án của bạn. File này sẽ định nghĩa các tài nguyên như **API Gateway**, **Lambda**, và **DynamoDB**.
   - Nếu file này có sẵn trong dự án, đảm bảo rằng nó đã được cấu hình chính xác cho các tài nguyên bạn cần.

2. **Build dự án**:
   - Sau khi đảm bảo file **`template.yaml`** đã có trong dự án
   - Truy cập vào thư mục backend của dự án sử dụng **SAM CLI** để build dự án:

          sam build
   - Nếu bạn thấy dòng chữ **Build Succeeded** bạn đã cài đặt thành công SAM CLI
  ![Error image](/images/build_success_samcli.png)

   
3. **Validate Template**:
   - Kiểm tra lại cấu hình của file `template.yaml` để chắc chắn rằng không có lỗi cú pháp hoặc cấu hình:
   - Gõ lệnh **sam validate** để kiểm tra file template.yaml:

          sam validate

   - Nếu bạn thấy thông báo như bên dưới, thì file **template.yaml** của bạn hợp lệ.
      ![Error image](/images/sam_validate.png)

4. **Triển khai tài nguyên lên AWS**:
   - Sau khi hoàn tất build và validate, bạn có thể triển khai tài nguyên lên AWS bằng lệnh:

          sam deploy --guided

   - Khi sử dụng **SAM CLI** để triển khai, bạn sẽ được yêu cầu nhập các thông tin cấu hình. 

     - **Stack Name**: `sam-app`
     - **AWS Region**: `ap-southeast-1`
     - **Confirm changes before deploy**: `y` 
     - **Allow SAM CLI IAM role creation**: `y` 
     - **Disable rollback**: `n` (Không tắt rollback)
     - **ExpressApiFunction has no authentication. Is this okay?**: `y` 
     - **Save arguments to configuration file**: `y` 
     - **SAM configuration file**: Gõ phím **Enter** 
     - **SAM configuration environment**: Gõ phím **Enter** 

   - Khi sử dụng **SAM CLI** để triển khai, bạn sẽ được yêu cầu nhập các thông tin cấu hình. 

      ![Error image](/images/deploy_this_changeset.png)

     - **Deploy this changeset**: `y` 
     - Bạn đợi khoảng 5 phút để cấu hình serverless (API Gateway, Lambda, DynamoDB, v.v.) từ máy tính của bạn lên AWS.

      ![Error image](/images/create_sam_app_success.png)

5. **Xác nhận triển khai**:
   - Sau khi triển khai thành công, SAM CLI sẽ cung cấp thông tin về các tài nguyên đã được tạo. Bạn có thể kiểm tra **API Gateway**, **Lambda function**, **S3**, **CLOUD FOUMATION** và **DynamoDB** trong AWS Management Console để xác nhận các tài nguyên đã được tạo đúng.
{{% notice tip %}}
Backend của bạn đã được triển khai thành công! Các tài nguyên như API Gateway, Lambda function và DynamoDB đã được tự động tạo. Bạn có thể kiểm tra trên AWS Console.
{{% /notice %}}
     - Truy cập vào [API Gateway](https://ap-southeast-1.console.aws.amazon.com/apigateway/main/)  bạn sẽ thấy API Gateway đã được tạo

      ![Error image](/images/create_API_gateway.png)

     - Truy cập vào [Lambda function](https://ap-southeast-1.console.aws.amazon.com/lambda/home/)  bạn sẽ thấy Lambda function đã được tạo

      ![Error image](/images/create_auto_lambda.png)

     - Truy cập vào [Amazon S3](https://ap-southeast-1.console.aws.amazon.com/s3/home)  bạn sẽ thấy Amazon S3 đã được tạo

      ![Error image](/images/access_s3_after_setup_samcli.png)

     - Truy cập vào [Cloud Foumation](https://ap-southeast-1.console.aws.amazon.com/cloudformation/home)  bạn sẽ thấy Cloud Foumation đã được tạo

      ![Error image](/images/create_auto_cloud_foumation.png)

     - Truy cập vào [DynamoDB](hhttps://ap-southeast-1.console.aws.amazon.com/dynamodbv2/home?region=ap-southeast-1#tables)  bạn sẽ thấy DynamoDB đã được tạo

      ![Error image](/images/create_auto_dynamoDB.png)


