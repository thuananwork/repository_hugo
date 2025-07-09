---
title : "Triển khai frontend"
date : 2023-10-25
weight : 5
chapter : false
pre : " <b> 5 </b> "
---

### Triển khai frontend

Sau khi backend đã sẵn sàng và đã kiểm thử thành công, bước tiếp theo là **triển khai phần frontend của website lên AWS S3** để tạo website tĩnh, giúp tối ưu chi phí và tốc độ tải trang.  
Đồng thời, bạn sẽ cấu hình hosting, cache, CORS để frontend hoạt động mượt mà, bảo mật khi kết nối với API backend.

**Mục tiêu phần này:**
- Hướng dẫn upload và triển khai code frontend lên AWS S3 Bucket.
- Bật static website hosting, cấu hình cache và CORS để frontend truy cập ổn định, bảo mật.
- **Cấp quyền public cho S3 Bucket** để website truy cập công khai.
- Kết nối frontend với endpoint API backend đã kiểm thử thành công ở các bước trước.

{{% notice info %}}
**Lưu ý:**  
Hãy đảm bảo rằng bạn đã cài **yarn** trong thư mục dự án của mình
{{% /notice %}}

**Kết thúc phần này, bạn sẽ:**
- Triển khai website frontend bài bản trên S3, đảm bảo mọi người đều có thể truy cập.
- Làm chủ việc cấu hình hosting, cache, CORS – giúp website tải nhanh, an toàn và tương thích với backend.
- **Biết cách cấp quyền public cho S3 bucket, tránh lỗi 403 khi truy cập website.**
- Sẵn sàng nâng cấp hệ thống với domain tùy chỉnh, CloudFront, hoặc các tính năng mới trong các bước tiếp theo.

### Nội dung
- [Triển khai frontend lên S3 Bucket](5.1-frontend-s3/)
- [Bật static hosting, cấu hình CORS](5.2-enable-static-hosting/)
- [Cấp quyền public cho S3 Bucket](5.3-s3-bucket-permission3/)
- [Cấu hình Google OAuth2 Client ID và Client Secret](5.4-clientid-clientserver/)
- [Kết nối frontend với API backend](5.5-connect-frontend-api-backend/)
