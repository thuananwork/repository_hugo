# Hướng dẫn chạy Hugo cho dự án này

## 1. Cài đặt Hugo (Khuyến nghị phiên bản v0.148.0)

- **Yêu cầu:** Sử dụng Hugo phiên bản **v0.148.0** để đảm bảo tương thích tốt nhất với dự án.

### Cài đặt trên Windows (bằng Chocolatey)
```sh
choco install hugo-extended --version=0.148.0 -y
```

### Cài đặt trên MacOS (bằng Homebrew)
```sh
brew install hugo@0.148.0
brew link --force hugo@0.148.0
```

### Hoặc tải trực tiếp từ trang chủ
- Truy cập: https://github.com/gohugoio/hugo/releases/tag/v0.148.0
- Tải về file phù hợp với hệ điều hành và giải nén, thêm vào PATH.

### Kiểm tra phiên bản
```sh
hugo version
```
Kết quả mong muốn: `hugo v0.148.0 ...`

## 2. Cài đặt các phụ thuộc (nếu có)

Nếu theme hoặc project sử dụng npm/yarn để quản lý asset:
```sh
yarn install
# hoặc
npm install
```

## 3. Chạy website ở chế độ local

```sh
hugo server -D
```
- Truy cập: http://localhost:1313 để xem website.

## 4. Build website để xuất bản

```sh
hugo
```
- Kết quả sẽ nằm trong thư mục `public/`. Bạn có thể upload toàn bộ thư mục này lên S3 hoặc bất kỳ web server nào.

## 5. Một số lệnh Hugo hữu ích

- Xem các lệnh hỗ trợ:
  ```sh
  hugo help
  ```
- Build với baseURL tùy chỉnh:
  ```sh
  hugo --baseURL="https://your-domain.com/"
  ```

## 6. Tham khảo thêm

- [Tài liệu chính thức Hugo](https://gohugo.io/documentation/)
- [Hướng dẫn theme Learn](https://themes.gohugo.io/themes/hugo-theme-learn/) 