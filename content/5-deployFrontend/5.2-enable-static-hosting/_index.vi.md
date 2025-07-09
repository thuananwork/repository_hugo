---
title : "Bật static hosting, cấu hình CORS"
date : 2023-10-25
weight : 7
chapter : false
pre : " <b> 5.2 </b> "
---

### Bật static hosting, cấu hình CORS và cấp quyền cho S3 Bucket

Sau khi đã upload mã nguồn frontend lên S3 Bucket, bạn cần **bật tính năng static website hosting**, cấu hình file index, error, thiết lập policy CORS và cấp quyền public để website chạy ổn định, truy cập được từ trình duyệt và có thể kết nối tới API backend.


#### Bước 1: Bật static hosting và cấu hình CORS

1. **Bật static website hosting cho bucket**
   - Truy cập vào bucket frontend trên [AWS S3 Console](https://s3.console.aws.amazon.com/s3/).
   - Chọn tab **Properties**.
   - Kéo xuống phần **Static website hosting**, nhấn **Edit**.
   ![static_website_hosting](/images/static_website_hosting.png)
   - Chọn **Enable**.
   - Nhập tên file `index.html` cho trường **Index document**.
   - Có thể nhập thêm `index.html` cho trường **Error document** (nên dùng nếu bạn triển khai SPA).
   - Lưu lại cài đặt.
   ![static_website_hosting](/images/enable_static_website_hosting.png)
   - AWS sẽ sinh ra một **Website endpoint** dạng:
     ```
     http://fcjfashionshop.com.s3-website-ap-southeast-1.amazonaws.com
     ```
   - Copy URL này để dùng cho bước sau.
   ![bucket_website_hosting](/images/bucket_website_hosting.png)

2. **Cấu hình CORS cho bucket**
   - Vào tab **Permissions** → cuộn xuống tìm mục **CORS configuration** → chọn **Edit**.
   ![cors](/images/cors.png)
   - Thêm cấu hình mẫu sau (JSON) để cho phép frontend truy cập tài nguyên hoặc upload ảnh lên S3 từ domain khác:
     ```json
     [
       {
         "AllowedOrigins": ["*"],
         "AllowedMethods": ["GET", "HEAD", "PUT", "POST", "DELETE"],
         "AllowedHeaders": ["*"]
       }
     ]
     ```
   - Nếu muốn giới hạn chỉ cho domain cụ thể (an toàn hơn):
     ```json
     [
       {
         "AllowedOrigins": ["https://your-domain.com"],
         "AllowedMethods": ["GET", "HEAD"],
         "AllowedHeaders": ["*"]
       }
     ]
     ```
   - Nhấn **Save** để áp dụng.
