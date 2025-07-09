---
title : "Triển khai frontend lên S3 Bucket"
date : 2023-10-25
weight : 6
chapter : false
pre : " <b> 5.1 </b> "
---

### Triển khai frontend lên S3 Bucket

Để website frontend hoạt động online, bạn sẽ upload toàn bộ mã nguồn đã build lên **AWS S3 Bucket**. S3 sẽ đóng vai trò là hosting tĩnh, giúp phân phối website với chi phí thấp và tốc độ nhanh.

**Các bước thực hiện:**

#### Bước 1: Đóng gói mã nguồn frontend

   - Mở `termiral` trên Vscode và truy cập vào thư mục `frontend`.
   - Copy lệnh sau và dán vào termiral
     ```
     yarn build
     ```
   - Thư mục `build` sẽ chứa tất cả file tĩnh cần upload.
   - Bạn đợi khoảng 1 phút để build dự án

![yarn build](/images/yarn_build.png)

#### Bước 2: Tạo S3 Bucket   
1. **Tạo S3 Bucket để chứa frontend**
   - Truy cập [AWS S3 Console](https://s3.console.aws.amazon.com/s3).
   - Click **Create bucket**.
   - Đặt tên bucket, ví dụ: `fcjfashionshop.com`.
   - **Region:** Chọn cùng region với backend (nên là ap-southeast-1 cho đồng bộ).
   - **Tắt “Block all public access”**.
   - Tích chọn vào **I acknowledge that the current settings might result in this bucket and the objects within becoming public.** , xác nhận cảnh báo để website có thể public
   - Nhấn **Create bucket** để hoàn tất.

![bucket_my_frontend](/images/bucket_frontend_s3.png)

{{% notice warning %}}
**Cẩn thận:**  
Bucket chứa website tĩnh cần mở quyền public read cho tất cả mọi người. Tuy nhiên không nên upload dữ liệu nhạy cảm vào đây vì bất cứ ai có link đều truy cập được!
{{% /notice %}}

2. **Tạo S3 Bucket để lưu trữ ảnh upload/avatar**

   - Truy cập [AWS S3 Console](https://s3.console.aws.amazon.com/s3).
   - Click **Create bucket**.
   - Đặt tên bucket, ví dụ: `uploads-avatars-2025` (nên dùng tên dễ nhận biết, không dấu).
   - **Region:** Chọn cùng region với hệ thống.
   - **Tắt “Block all public access”** (bỏ tick), xác nhận cảnh báo để cho phép public file ảnh.
   - Tích chọn vào **I acknowledge that the current settings might result in this bucket and the objects within becoming public.** , xác nhận cảnh báo để website có thể public.
   - Nhấn **Create bucket** để hoàn tất.
![click_bucket_myfrontend](/images/buget_upload_avata.png)

{{% notice warning %}}
**Cẩn thận:**  
Bucket lưu trữ ảnh upload/avatar nếu mở quyền public thì bất kỳ ai có đường dẫn đều có thể xem ảnh. Không nên upload thông tin nhạy cảm vào bucket này!
{{% /notice %}}

#### Bước 3: Upload mã nguồn build Frontend lên S3 bucket bằng AWS CLI

   - Đảm bảo bạn đã cài đặt và cấu hình AWS CLI (đã chạy `aws configure`).
   - Thực hiện lệnh:
        ```
        cd frontend
        aws s3 cp build/ s3://fcjfashionshop.com/ --recursive
        ```
        ![build_s3_to_frontend](/images/build_s3_to_frontend.png)

   - Tham số --recursive giúp upload tất cả file và folder con bên trong build.

 **Kiểm tra lại nội dung bucket**

   - Vào lại bucket trên AWS Console, xác nhận toàn bộ file (index.html, main.js, CSS, ảnh…) đã được upload thành công.
   - Có thể click trực tiếp vào file (VD: `index.html`) và copy URL tại **Object URL** để kiểm tra file đã public chưa (phải xem được file HTML/raw trên trình duyệt).

   - Bạn có thể kiểm tra các file và folder đã upload lên s3 bằng cách truy cập vào Object

        ![build_s3_to_frontend](/images/file_uploaded_s3_after_build.png)


{{% notice info %}}  
Sau khi hoàn thành các bước trên, bạn đã đưa website frontend của mình lên AWS S3.
{{% /notice %}}

