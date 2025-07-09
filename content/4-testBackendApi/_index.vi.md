---
title : "Kiểm thử API backend với Postman"
date : 2023-10-25
weight : 4
chapter : false
pre : " <b> 4 </b> "
---

#### Kiểm thử API backend với Postman

Sau khi triển khai backend thành công với **API Gateway** và **Lambda**, bước tiếp theo là kiểm thử các API để xác nhận hệ thống backend hoạt động đúng trước khi kết nối với frontend.

**Postman** là công cụ mạnh mẽ và phổ biến nhất giúp bạn gửi các request (GET, POST, PUT, DELETE, ...) đến endpoint API, xem kết quả trả về, kiểm tra logic xử lý cũng như debug lỗi.

Bạn có thể tải Postman tại: [**Download Postman**](https://www.postman.com/downloads/)

**Mục tiêu phần này:**
- Hướng dẫn cách lấy **endpoint API Gateway** vừa deploy trên AWS để làm việc với Postman.
- Thực hành gửi các request **GET/POST** tới API, phân tích kết quả trả về để kiểm tra tính đúng đắn của backend.
- Nhận biết và xử lý một số lỗi phổ biến trong quá trình test API.

**Nội dung phần này bao gồm:**
1. **Lấy endpoint API Gateway:**  
   Hướng dẫn tìm, copy URL endpoint trên AWS Console dùng cho việc kiểm thử API.
2. **Gửi request GET/POST để kiểm tra response backend:**  
   Hướng dẫn chi tiết cách gửi các request GET/POST với Postman, nhập dữ liệu, kiểm tra kết quả response từ backend.

{{% notice info %}}
**Lưu ý:**  
Trước khi test API bằng Postman, hãy chắc chắn rằng backend đã deploy thành công và không có lỗi ở các bước trước đó (CloudFormation/Lambda đều trạng thái thành công).
{{% /notice %}}

**Kết thúc phần này, bạn sẽ:**
- Biết cách lấy endpoint API Gateway để dùng cho kiểm thử.
- Sử dụng thành thạo Postman gửi các request GET/POST tới backend.
- Phân tích, kiểm tra kết quả trả về, và sẵn sàng kết nối frontend với backend đã kiểm thử thành công.


### Nội dung
- [Lấy endpoint API Gateway](4.1-endpoint-api-gateway/)
- [Gửi request GET/POST để kiểm tra response backend](4.2-get-post-response/)