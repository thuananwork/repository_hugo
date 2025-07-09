---
title : "Lấy endpoint API Gateway"
date : 2023-10-25
weight : 5
chapter : false
pre : " <b> 4.1 </b> "
---

#### Lấy endpoint API Gateway

Sau khi triển khai backend bằng SAM CLI/CloudFormation, hệ thống sẽ tự động tạo ra một địa chỉ endpoint cho API Gateway. Đây là địa chỉ bạn sẽ sử dụng để gửi các request kiểm thử bằng Postman, curl hoặc tích hợp frontend sau này.

{{% notice tip %}}
**Note:**  
Sử dụng endpoint của phần trước nếu bạn đã lưu
{{% /notice %}}
**Các bước thực hiện:**

1. **Truy cập AWS Management Console**

   - Đăng nhập vào [AWS Console](https://console.aws.amazon.com/).
   - Chọn dịch vụ **API Gateway** trong danh sách dịch vụ AWS.

2. **Chọn API vừa deploy**

   - Tại giao diện API Gateway, bạn sẽ thấy danh sách các API đã được tạo.
   - Tìm và click vào tên API mà bạn vừa triển khai.
   - ![API Gateway](/images/api_sam_app.png)

3. **Lấy endpoint ở mục Stages**

   - Ở thanh menu bên trái, chọn **Stages**.
   - Click vào stage mà bạn đã deploy.
   - Ngay phía trên, bạn sẽ thấy **Invoke URL**. Đây chính là endpoint của API Gateway mà bạn cần sử dụng cho việc kiểm thử.
   - Copy URL này
   - ![Stages Prod](/images/stages_prod.png)

4. **Kiểm tra lại endpoint**

- Bạn có thể copy endpoint này, dán vào trình duyệt hoặc Postman để kiểm tra phản hồi cơ bản.
- Thông thường, nếu chưa cấu hình resource cụ thể (ví dụ: `/products`), truy cập trực tiếp endpoint gốc sẽ báo lỗi “Missing Authentication Token” hoặc trả về HTTP 403. Điều này là bình thường, bạn chỉ cần thêm route resource đúng với API của mình khi test.

{{% notice tip %}}
**Mẹo:**  
Nên lưu lại endpoint này ở file README dự án hoặc note cá nhân, tránh phải truy cập lại AWS Console nhiều lần khi test API.
{{% /notice %}}

