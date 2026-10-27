# Portfolio CV - Trương Nhất Sơn

Trang portfolio cá nhân giới thiệu Trương Nhất Sơn, các kỹ năng, dự án tiêu biểu và thông tin liên hệ. Giao diện được xây dựng bằng HTML và CSS thuần, thiết kế responsive để sử dụng trên điện thoại, máy tính bảng và máy tính.

## Chức năng

- Điều hướng nhanh đến các phần Giới thiệu, Kỹ năng, Dự án và Liên hệ.
- Giới thiệu hồ sơ cá nhân, ảnh đại diện và các kỹ năng.
- Hiển thị các dự án tiêu biểu dưới dạng thẻ: Game Offline, Ứng dụng phóng to, Mod Minecraft và Đọc sách.
- Cung cấp thông tin email, GitHub và LinkedIn.
- Có giao diện đăng nhập minh họa trong phần Liên hệ.
- Bố cục tự điều chỉnh theo kích thước màn hình.

> **Lưu ý:** Đây là website tĩnh. Các liên kết “Xem chi tiết”, đăng nhập và đăng ký hiện chỉ là giao diện minh họa; dự án chưa có backend, xác thực tài khoản hay xử lý dữ liệu biểu mẫu.

## Công nghệ

- HTML5
- CSS3 (Flexbox, CSS Grid, media queries)
- Python (tùy chọn, dùng máy chủ HTTP có sẵn để chạy thử)
- Docker và Nginx (tùy chọn, dùng để chạy website trong container)

## Yêu cầu môi trường

Để xem website, bạn chỉ cần một trình duyệt hiện đại như Chrome, Firefox, Edge hoặc Safari.

Để chạy bằng máy chủ cục bộ, cài Python 3. Không cần cài Node.js, không cần tải thư viện và không có bước biên dịch.

Nếu chạy bằng Docker, cần cài Docker Engine hoặc Docker Desktop và có kết nối Internet lần đầu để tải image `nginx:alpine`.

## Cài đặt

Clone mã nguồn bằng Git:

```bash
git clone https://github.com/truongnhatson2228-byte/CV.git
cd CV
```

Hoặc tải mã nguồn dưới dạng ZIP và giải nén. Sau đó mở terminal tại thư mục dự án. Cấu trúc cần giữ nguyên:

```text
.
├── index.html
├── README.md
└── assets
    ├── css
    │   └── styles.css
    └── img
        ├── avatar.jpg
        ├── game offline.jpg
        ├── kính lúp.jpg
        ├── minecraft.jpg
        └── sách.jpg
```

Không đổi tên hoặc di chuyển các tệp ảnh nếu chưa cập nhật đường dẫn tương ứng trong `index.html`.

## Cấu hình và tùy chỉnh

Dự án không sử dụng tệp cấu hình, biến môi trường hay thông tin bí mật.

- Sửa nội dung, tiêu đề, liên kết và thông tin liên hệ trong `index.html`.
- Thay ảnh trong `assets/img/`; nếu đổi tên ảnh, cập nhật thuộc tính `src` trong `index.html`.
- Điều chỉnh màu sắc, bố cục và kiểu chữ trong `assets/css/styles.css`.
- Các địa chỉ email, GitHub và LinkedIn hiện được ghi trực tiếp trong trang; hãy thay bằng thông tin của bạn trước khi công bố.

## Chạy thử

### Windows

Mở PowerShell hoặc Command Prompt tại thư mục dự án, rồi chạy:

```powershell
py -m http.server 8000
```

Nếu lệnh `py` không có nhưng đã cài Python, thử:

```powershell
python -m http.server 8000
```

### macOS

Mở Terminal tại thư mục dự án và chạy:

```bash
python3 -m http.server 8000
```

### Linux

Mở terminal tại thư mục dự án và chạy:

```bash
python3 -m http.server 8000
```

Sau khi máy chủ khởi động, mở <http://localhost:8000> trong trình duyệt. Dừng máy chủ bằng `Ctrl+C`.

Nếu chỉ muốn xem nhanh, có thể mở `index.html` trực tiếp bằng trình duyệt; chạy qua máy chủ HTTP được khuyến nghị để kiểm tra website trong môi trường gần với triển khai thực tế hơn.

## Chạy bằng Docker

Không cần tạo Dockerfile: image Nginx sẽ phục vụ trực tiếp các tệp của dự án.

### Windows (PowerShell)

Chạy tại thư mục dự án:

```powershell
docker run --name portfolio-cv -d -p 8080:80 --mount "type=bind,source=$($PWD.Path),target=/usr/share/nginx/html,readonly" nginx:alpine
```

### macOS và Linux

Chạy tại thư mục dự án:

```bash
docker run --name portfolio-cv -d -p 8080:80 --mount "type=bind,source=$(pwd),target=/usr/share/nginx/html,readonly" nginx:alpine
```

Mở <http://localhost:8080> để xem trang. Để dừng và xóa container:

```bash
docker stop portfolio-cv
docker rm portfolio-cv
```

Nếu cổng `8080` đang được sử dụng, đổi phần `-p 8080:80` thành một cổng khác, ví dụ `-p 8081:80`, rồi truy cập cổng tương ứng. Trên Windows, nếu Docker không truy cập được thư mục dự án, hãy kiểm tra quyền chia sẻ thư mục trong Docker Desktop.

## Thông tin liên hệ

- **Email:** [truongnhatson2228@gmail.com](mailto:truongnhatson2228@gmail.com)
- **GitHub:** [github.com/truongnhatson2228](https://github.com/truongnhatson2228)
- **LinkedIn:** [linkedin.com/in/truongnhatson](https://linkedin.com/in/tru)