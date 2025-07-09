---
title : "Kiểm tra trạng thái và log backend sau khi triển khai"
date : 2023-10-25
weight : 5
chapter : false
pre : " <b> 3.2 </b> "
---

#### Kiểm tra trạng thái và log backend sau khi triển khai

Sau khi bạn đã deploy backend lên AWS với SAM CLI và CloudFormation, bước tiếp theo cực kỳ quan trọng là **kiểm tra trạng thái tài nguyên** và **xem log backend** để đảm bảo mọi thành phần đã hoạt động đúng.

- Đảm bảo API Gateway, Lambda, DynamoDB… đều được tạo thành công và đang hoạt động.
- Phát hiện và sửa lỗi kịp thời nếu gặp sự cố deploy hoặc lỗi logic.
- Chuẩn bị sẵn sàng cho bước kiểm thử API bằng Postman hoặc frontend.

1. **Kiểm tra trạng thái Stack và tài nguyên trên CloudFormation**

   - Truy cập [AWS CloudFormation Console](https://console.aws.amazon.com/cloudformation).
   - Chọn Stack vừa deploy (`sam-app`).

![Stack-sampsamdeloy](/images/choose_sam_app.png)


   - Kiểm tra tab Status: Nếu status là `CREATE_COMPLETE` hoặc `UPDATE_COMPLETE` bạn đã deploy thành công.

![Stack-sampsamdeloy](/images/status_completele_sam_app.png)

   - Ở tab Resources, xem danh sách tài nguyên đã tạo (API Gateway, Lambda, DynamoDB, S3…).

{{% notice tip %}}
Nếu thấy status `ROLLBACK`, `FAILED`, click tab Events để xem chi tiết lỗi và xác định nguyên nhân.
{{% /notice %}}


2. **Kiểm tra log Lambda bằng CloudWatch**

   - Trong [AWS Console](https://aws.amazon.com/console/), vào Lambda → chọn hàm vừa deploy.
   ![Click-lambda-sammapp](/images/click_lambda_samapp.png)

   - Cuộn xuống và click vào tab **Monitor**, chọn vào **View CloudWatch logs** để truy cập log chi tiết.
   ![Monitor](/images/Monitor.png)

   - Cuộn xuống và click vào tab **Log streams**, chọn Log stream đầu tiên.
   ![LogSrteam](/images/log_steams.png)

   - Mỗi lần có request (GET/POST…), Lambda sẽ ghi log vào CloudWatch – tại đây bạn có thể:
     - Xem request đã nhận gì.
     - Response trả về như thế nào.
     - Debug lỗi nếu code bị crash hoặc trả về lỗi 500.

3. **Xác minh hoạt động của API Gateway**

   - Trong [AWS Console](https://aws.amazon.com/console/), vào API Gateway → chọn API bạn vừa tạo.
      ![API Gateway](/images/api_sam_app.png)

   - Vào mục **Stages** → chọn **stage** → chọn `prod`.

   - Copy Invoke URL để chuẩn bị test bằng Postman/curl ở bước tiếp theo.
      ![Stages Prod](/images/stages_prod.png)


{{% notice info %}}
Nếu bạn xác minh xong toàn bộ resource đều hoạt động tốt, log không có lỗi nghiêm trọng, bạn đã sẵn sàng test API backend bằng Postman hoặc tích hợp frontend!
{{% /notice %}}
