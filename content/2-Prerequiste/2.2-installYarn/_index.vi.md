---
title : "Cài đặt Yarn"
date : 2023-10-25
weight : 4
chapter : false
pre : " <b> 2.2 </b> "
---

Yarn là một trình quản lý gói (package manager) cho JavaScript, được sử dụng rộng rãi trong các dự án frontend để giúp quản lý các thư viện và gói phần mềm một cách hiệu quả. Yarn giúp giải quyết các vấn đề về tốc độ cài đặt, sự nhất quán và bảo mật khi quản lý các thư viện cho dự án.


### Bước 1: Clone dự án về máy

1. **Clone mã nguồn dự án từ Github:**
   - Mở terminal và chạy lệnh sau để tải source code về:
   ```sh
   git clone https://github.com/thuan120710/Fcjwebfashionthuan_2025
     ```

### Bước 2: Cài đặt Yarn
#### Cách 1: Cài đặt Yarn tự động thông qua npm
1. **Di chuyển vào thư mục frontend của dự án:**
   ```sh
   cd Fcjwebfashionthuan_2025/frontend
     ```
2. **Cài đặt các dependency (Yarn sẽ tự động được sử dụng nếu dự án có file yarn.lock):**
   - Chạy lệnh: 
   ```sh
   npm install
     ```
   - Nếu dự án có file `yarn.lock`, nên dùng: 
   ```sh
   yarn install
     ```  
   - Lệnh này sẽ cài đặt đầy đủ các thư viện cần thiết cho frontend dự án, bao gồm cả Yarn nếu có trong dependency.

#### Cách 2: Cài đặt Yarn thủ công (nếu cần)
Nếu máy tính bạn chưa có Yarn hoặc muốn cài đặt mới hoàn toàn, làm theo hướng dẫn sau:
1. **Cài đặt Yarn thông qua npm:**
   - Yarn có thể được cài đặt thông qua npm. Đảm bảo rằng bạn đã cài đặt NodeJS và npm trước khi tiếp tục.
   - Mở terminal và chạy lệnh sau để cài đặt Yarn:
   ```sh
   npm install -g yarn
     ```  
2. **Cài đặt Yarn trên macOS (qua Homebrew):**
Nếu bạn đang sử dụng macOS, có thể dùng lệnh:  
     ```sh
     brew install yarn
     ```
     
1. **Cài đặt Yarn trên Linux (Ubuntu):**
   - Trên Linux, bạn có thể sử dụng `apt` để cài đặt Yarn:
   ```sh
   sudo apt update && sudo apt install yarn
     ```

{{% notice tip %}}
Yarn đã được cài đặt thành công! Bạn có thể bắt đầu quản lý các thư viện frontend cho dự án của mình.
{{% /notice %}}

### Bước 2: Kiểm tra cài đặt Yarn

1. **Kiểm tra phiên bản Yarn:**
   - Sau khi cài đặt thành công, bạn có thể kiểm tra phiên bản Yarn bằng lệnh:

         yarn --version

   - Nếu hiển thị ra phiên bản yarn, bạn đã cài đặt yarn thành công:

          C:\Users\thuan>yarn --version
            1.22.22


2. **Kiểm tra cài đặt Yarn:**
   - Để đảm bảo rằng Yarn đã được cài đặt chính xác, bạn có thể chạy lệnh sau để kiểm tra trạng thái:
  
          yarn   

     ![Error image]( /images/check_yarn.png )