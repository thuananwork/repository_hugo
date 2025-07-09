---
title : "Cấp quyền public cho S3 Bucket"
date : 2023-10-25
weight : 8
chapter : false
pre : " <b> 5.3 </b> "
---

### Cấp quyền public cho S3 Bucket

Để truy cập được vào giao diện web bạn cần phải cấu hình permission cho S3 Bucket chứa frontend.

#### Bước 1: Cấp quyền public cho S3 Bucket

1. **Cấp quyền cho Bucket Frontend**
   - Truy cập **Permissions** của bucket, cuộn xuống mục **Bucket policy** → **Edit**.
   ![click_edit_bucket_policy](/images/click_edit_bucket_policy.png)
   - Thêm policy cho phép public đọc file, ví dụ:
     ```json
     {
       "Version": "2012-10-17",
       "Statement": [
         {
           "Sid": "PublicReadGetObject",
           "Effect": "Allow",
           "Principal": "*",
           "Action": "s3:GetObject",
           "Resource": "arn:aws:s3:::fcjfashionshop.com/*"
         }
       ]
     }
     ```
   - Nhấn **Save** để áp dụng.
   ![edit_permission_bucket_avata](/images/edit_permission_bucket_avata.png)

2. **Cấp quyền cho Bucket upload avatar (nếu có)**
   - Vào tab **Permissions** của bucket → **Bucket policy**.
   ![click_bucket_myfrontend](/images/permission_upload_avata.png)
   - Thêm policy cho phép public đọc file, ví dụ:
     ```json
     {
       "Version": "2012-10-17",
       "Statement": [
         {
           "Sid": "PublicReadGetObject",
           "Effect": "Allow",
           "Principal": "*",
           "Action": "s3:GetObject",
           "Resource": "arn:aws:s3:::uploads-avatars-2025/*"
         }
       ]
     }
     ```
   - Nhấn **Save** để áp dụng.
   ![edit_permission_bucket_avata](/images/edit_permission_bucket_avata.png)


#### Bước 2: Kiểm tra hoạt động website

- Dùng link **Website endpoint** truy cập thử website.
- Nếu index.html tải thành công, website đã hoạt động trên S3.
  ![front_website_s3](/images/front_s3_website.png)
- Nếu gặp lỗi 403/404:
  - Kiểm tra lại quyền bucket (bucket policy).
  - Đảm bảo đã bật static hosting.
  - Xem lại tên file index/error đúng chính tả.

{{% notice warning %}}
**Lưu ý:**  
Chỉ nên dùng `"*"` cho development/test. Khi đưa lên production, hãy cấu hình đúng domain website trong `AllowedOrigins` để tăng bảo mật.
{{% /notice %}}


