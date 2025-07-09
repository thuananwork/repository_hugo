---
title : "Gửi request GET/POST để kiểm tra response backend"
date : 2023-10-25
weight : 6
chapter : false
pre : " <b> 4.2 </b> "
---

#### Gửi request GET/POST để kiểm tra response backend đăng nhập

Sau khi đã lấy được endpoint API Gateway, bạn cần gửi các request **POST** và **GET** đến API để xác nhận backend hoạt động đúng. Việc này thường thực hiện bằng **Postman** – công cụ test API phổ biến nhất hiện nay.

**Các bước thực hiện:**

1. **Kiểm thử phương thức POST bằng Postman**

   - Mở Postman, chọn **New** → **HTTP Request**.
   - Chọn method là **POST**.
   - Nhập endpoint đầy đủ vào ô URL, ví dụ:
     ```
     https://ars3538v1i.execute-api.ap-southeast-1.amazonaws.com/Prod/api/users
     ```
   - Chuyển sang tab **Body** → chọn **raw** → chọn **JSON**.
      ![Test-api-postman](/images/test_api_postman.png)

   - **Nhập dữ liệu mẫu vào ô body như sau:**
     ```json
     {
       "username": "AdminUser",
       "email": "firstcloudjourney@example.com",
       "password": "AdminUser123@",
       "firstName": "Admin",
       "lastName": "User",
       "isAdmin": true,
       "googleId": null,
       "avatar": "https://i.imgur.com/avatar.jpg",
       "phone": "0912345678",
       "address": "",
       "isDeleted": false
     }
     ```
   - Nhấn **Send** để gửi request.
   - Nếu API hoạt động đúng, bạn sẽ nhận được response xác nhận.
   - Copy lại `token` để sử dụng cho các request sau.
      ![Test-api-postman](/images/body_raw_postman_method_get.png)

  {{% notice tip %}}
  Nếu API yêu cầu xác thực (`API Key`, Bearer Token, v.v.) hoặc cần custom header, hãy bổ sung ở tab **Headers** của Postman trước khi gửi request!
  {{% /notice %}}

2. **Kiểm thử phương thức GET đăng nhập bằng Postman**

   - Truy cập vào [DynamoDB](https://ap-southeast-1.console.aws.amazon.com/dynamodbv2/home?region=ap-southeast-1) trên AWS Controller
   - Chọn **table** chọn bảng **ShopUser** 
      ![Test-api-postman](/images/select_shopuser_db.png)

   - Chọn **Explore table items** để kiểm tra dữ liệu của user vừa tạo
      ![Explore table item](/images/explore_table_item.png)

   - Cuộn xuống và chỉnh sửa quyền **isAdmin** của user vừa tạo thành `true`
      ![IsAdmin](/images/isAdmin_true.png)

   - Tạo một request mới trong Postman, chọn method `GET`.
   - Nhập Authorization đầy đủ vào ô URL, ví dụ:
     ```
     https://ars3538v1i.execute-api.ap-southeast-1.amazonaws.com/Prod/api/users
     ```
   - Tại Authorization chọn: **Bearer Token**
   - Tại ô Token: nhập token đã lưu trước đó
   - Nhấn **Send** để gửi request.
     ![Test-api-postman-get-method](/images/test_api_postman_get_method.png)
   - Nếu API hoạt động bình thường, bạn sẽ nhận được response trả về thông tin của các user đang tồn tại trong database.
   - Kiểm tra mã trạng thái HTTP (là 200 OK), nội dung body response.
      ![Test-api-backend-success](/images/test_api_backend_success.png)

  {{% notice tip %}} 
  Bạn có thể test các chức năng khác của dự án bằng cách truy cập vào code để lấy url của api
  {{% /notice %}}

3. **Phân tích kết quả và xử lý lỗi thường gặp**

   - Nếu nhận được response dữ liệu đúng → backend đã hoạt động chính xác.
   - Nếu gặp lỗi như `403 Forbidden`, `401 Unauthorized`, `Missing Authentication Token`:
     - Kiểm tra lại endpoint đã đúng route resource chưa.
     - Xem lại config API Gateway và mapping template.
     - Kiểm tra log Lambda trên CloudWatch để xác định lỗi chi tiết.
   - Nếu mã lỗi `500 Internal Server Error`:
     - Thường là do code Lambda gặp lỗi. Vào CloudWatch log để debug.

**Kết luận:**  
Việc kiểm thử API bằng POST/GET là bước xác nhận backend đã hoạt động hoàn chỉnh trước khi tích hợp với frontend hoặc triển khai lên môi trường thật. Nếu gặp lỗi, nên tra log trên CloudWatch hoặc kiểm tra lại cấu hình API Gateway và Lambda để xử lý kịp thời.
