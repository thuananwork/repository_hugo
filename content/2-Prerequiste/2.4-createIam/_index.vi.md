---
title : "Tạo tài khoản và cấu hình IAM"
date : 2023-10-25
weight : 6
chapter : false
pre : " <b> 2.4 </b> "
---

#### Tạo tài khoản và cấu hình IAM

AWS Identity and Access Management (IAM) cho phép bạn quản lý quyền truy cập đến tài nguyên AWS một cách an toàn. Trong bước này, bạn sẽ tạo một IAM user, cấp quyền truy cập thích hợp và cấu hình Access Key để sử dụng trong các bước tiếp theo của workshop.

#### Tạo IAM User

   1. Truy cập trang [AWS Management Console](https://aws.amazon.com/console/) và vào dịch vụ **IAM**.

![Error image]( /images/iam_access.png)

   2. Trong thanh điều hướng bên trái, chọn **Users** và nhấn **Create users** ở menu bên trái.

![Error image]( /images/create_user.png)


   3. Tạo người dùng IAM:
      - Đặt tên User name là `AdminUser` (hoặc tên bạn muốn).
      - Tích chọn **Provide user access to the AWS Management Console - optional**
      - Tại phần **User type** chọn **I want to create an IAM user**
      - Chọn Custom password - Nhập mật khẩu của bạn
      - Bỏ chọn **Users must create a new password at next sign-in - Recommended**
      - Chọn Next
- 
![Error image]( /images/create_info_iam_user_1.png)

![Error image]( /images/create_info_iam_user_2.png)

   4. Cấp quyền truy cập cho người dùng:
      - Chọn **Attach policies directly**.
      - Tìm kiếm và chọn policy **AWSCloudFormationFullAccess, AmazonDynamoDBFullAccess, AWSLambda_FullAccess, AmazonS3FullAccess, AmazonAPIGatewayAdministrator, IAMFullAccess** và tích chọn để thêm các quyền cần thiết cho dự án.
      - Tiếp theo kéo xuống và nhấn Next

![Error image]( /images/add_user_permissions.png)

   5. Kiểm tra lại thông tin tại Permissions summary
      - Nhấn **Create user** để tạo tài khoản AWS IAM

![Error image]( /images/create_user_iam.png)

   6. Iam User đã được tạo thành công 
      - Chọn download .csv file để lưu trữ thông tin tài khoản
      - Click **view user** để xem thông tin chi tiết

![Error image]( /images/create_user_iam_success.png)


#### Tạo Access Key 

1. Hiển thị và lưu Access Key và Secret Access Key:
   - Chọn vào **Create access key** để tạo access key cho user.

![Error image]( /images/create_access_key.png)
   - Tích chọn **Command Line Interface (CLI)** và nhấn Next.
   - Click vào **Show** để hiển thị giá trị **Secret access key**.

![Error image]( /images/command_line_interface.png)

   - Click vào **Create access key**.

![Error image]( /images/create_access_key_lasted.png)

   - Click vào **Chọn Download .csv file** để lưu trữ thông tin.
   - Và bấm vào **done**

{{% notice info %}}
Hãy lưu trữ Access key và Secret access key ở nơi an toàn. Chúng sẽ cần thiết cho việc truy cập các dịch vụ AWS qua API, CLI hoặc SDK.
{{% /notice %}}

![Error image]( /images/create_access_key_success.png)

   - Kiểm tra và thấy Access Key đã được tạo thành công.

![Error image]( /images/create_user_iam_success_dashboard.png)


1. **Lưu thông tin Access Key**:
   - Hãy **lưu lại cặp giá trị Access key ID + Secret access key** này vì bạn sẽ cần nó cho các bước tiếp theo của workshop.
   - Bạn cũng có thể **click Download .csv** để tải xuống file chứa **Access key ID** và **Secret access key** dưới dạng **CSV**.