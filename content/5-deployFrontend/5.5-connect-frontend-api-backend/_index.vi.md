---
title : "Kết nối frontend với API backend"
date : 2023-10-25
weight : 10
chapter : false
pre : " <b> 5.5 </b> "
---

#### Kết nối frontend với API backend

Sau khi đã upload website lên S3 và bật static hosting thành công, bước cuối cùng là **kết nối frontend với backend thông qua endpoint API Gateway** mà bạn đã kiểm thử trước đó. Đây là thao tác cực kỳ quan trọng để website có thể lấy/gửi dữ liệu động và thực sự hoạt động như một ứng dụng thương mại điện tử hiện đại.

**Các bước thực hiện:**

1. **Xác định endpoint API backend**

   - Sử dụng chính endpoint API Gateway đã lấy ở bước kiểm thử backend.  
     Ví dụ:
     ```
     https://ars3538v1i.execute-api.ap-southeast-1.amazonaws.com/Prod/api/users
     ```

2. **Cập nhật cấu hình endpoint vào mã nguồn frontend**

   - Mở code và tìm đến folder Frontend.
   - Mở file `.env` trong thư mục **Frontend**
   - Mở file `index.js` trong thư mục **Frontend**
   - Dán URL của API Gateway đã copy vào URL gốc trong code
    ![edit_api_env](/images/edit_api_env.png)
    ![edit_api_env](/images/edit_api_index.png)


**Kết luận:**  
Sau khi kết nối frontend với backend thành công, website đã sẵn sàng hoạt động động với dữ liệu thực tế từ AWS. Bạn có thể tiếp tục cấu hình domain, bảo mật SSL, hoặc triển khai CloudFront để tối ưu hơn.
