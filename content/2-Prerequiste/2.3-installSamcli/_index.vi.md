---
title : "Cài đặt SAM CLI"
date : 2023-10-25
weight : 5
chapter : false
pre : " <b> 2.3 </b> "
---


AWS SAM CLI là một công cụ dòng lệnh giúp bạn phát triển, đóng gói backend và triển khai các ứng dụng serverless sử dụng AWS Lambda, API Gateway và các dịch vụ AWS serverless khác. Trong bước này, bạn sẽ cài đặt SAM CLI để phát triển backend serverless cho website thương mại điện tử động của mình.

#### Bước 1: Cài đặt SAM CLI

1. **Cài đặt trên Windows:**
   - Truy cập vào trang [Installing the AWS SAM CLI](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/install-sam-cli.html) để tải bản cài đặt SAM CLI cho Windows.
   - Click chọn Window
   - Chạy tệp cài đặt .msi và làm theo các hướng dẫn để hoàn tất quá trình cài đặt.
   - Mở Termiral gõ `sam-version`

![Error image]( /images/install_samcli.png)
   
2. **Cài đặt trên macOS:**
   - Sử dụng **Homebrew** để cài đặt SAM CLI:

         brew tap aws/tap
         brew install aws-sam-cli

3. **Cài đặt trên Linux (Ubuntu):**
   - Trên Linux, bạn có thể sử dụng `apt` để cài đặt SAM CLI:

            sudo apt-get update
            sudo apt-get install aws-sam-cli


4. **Cài đặt SAM CLI từ nguồn (nếu cần):**
   - Nếu bạn không muốn sử dụng các phương pháp trên, bạn có thể cài đặt SAM CLI từ mã nguồn. Hướng dẫn chi tiết có tại: [Install SAM CLI from source](https://github.com/aws/aws-sam-cli/releases).

{{% notice success %}}
SAM CLI đã được cài đặt thành công! Bạn có thể bắt đầu phát triển và triển khai các ứng dụng serverless với AWS.
{{% /notice %}}

#### Bước 2: Kiểm tra cài đặt SAM CLI

1. **Kiểm tra phiên bản SAM CLI:**
   - Sau khi cài đặt thành công, mở terminal (hoặc Command Prompt trên Windows) và nhập lệnh sau để kiểm tra phiên bản SAM CLI:

          sam --version
2. **Kiểm tra cài đặt SAM CLI:**
   - Nếu lệnh trên hiển thị thông tin về phiên bản của SAM CLI, bạn đã cài đặt thành công công cụ này.

          C:\Users\thuan>sam --version
           SAM CLI, version 1.141.0

