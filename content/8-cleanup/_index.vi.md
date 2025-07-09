---
title: "Dọn dẹp tài nguyên"
date: 2023-10-25
weight: 8
chapter: false
pre: "<b>8. </b>"
---

### Dọn dẹp tài nguyên

Sau khi hoàn tất demo và trải nghiệm dự án, bạn cần **dọn dẹp các tài nguyên AWS** đã sử dụng để tránh phát sinh chi phí không cần thiết.  
{{% notice tip %}}
Nên xóa S3 Bucket trước khi xóa Stack CloudFormation, để đảm bảo Stack được xóa thành công!
{{% /notice %}}

#### 1. Xóa S3 Bucket chứa frontend và file upload

1. Truy cập [AWS S3 Console](https://s3.console.aws.amazon.com/s3/home).
2. Chọn từng bucket bạn đã tạo cho frontend và upload avatar (ví dụ: `fcjshop-frontend-website`, `uploads-avatars-2025`).
3. Nhấn `Empty`

     ![Delete S3 bucket](/images/empty_fcjfashioshop_S3.png)
     ![confirm_empty_fcjfashioshop_S3](/images/confirm_empty_fcjfashioshop_S3.png)

4. Chọn lại **fcjshop-frontend-website**.
5. Nhấn **Delete**

     ![select_delete_fcjfashion_shop](/images/select_delete_fcjfashion_shop.png)
    ![select_delete_fcjfashion_shop](/images/delete_fcjfashion.png)

- Bạn cũng xóa tương tự với **uploads-avatars-2025**

#### 2. Xóa Stack bằng CloudFormation

1. Truy cập [CloudFormation Console](https://console.aws.amazon.com/cloudformation/home).
2. Chọn đúng **stack** bạn đã deploy (ví dụ: `fcjfashioshop.com` hoặc tên stack của bạn).
3. Nhấn **Delete**.
     ![delete_stack](/images/delete_samap_cloudformation.png)

4. Xác nhận thao tác xóa.
     ![deletconfirm_delete_samappe_stack](/images/confirm_delete_samapp.png)
5.  Bạn cũng xóa tương tự với **Stack**còn lại.

{{% notice info %}}
**Lưu ý:**  
Sau khi xóa stack CloudFormation, tất cả resource backend như Lambda, API Gateway, DynamoDB table, IAM role... đều sẽ bị xóa tự động.
{{% /notice %}}


**Kết luận:**  
Bạn đã dọn dẹp toàn bộ tài nguyên AWS sử dụng cho dự án, đảm bảo không còn phát sinh chi phí không mong muốn. Nếu muốn thử lại, chỉ cần triển khai lại từ đầu!

{{% notice tip %}}
Nên kiểm tra lại trang **Billing** của AWS để đảm bảo không còn dịch vụ nào tính phí ngoài ý muốn.
{{% /notice %}}
