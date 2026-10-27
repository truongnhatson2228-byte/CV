# Báo cáo kiểm thử

- **Dự án:** Portfolio CV - Trương Nhất Sơn
- **Phiên bản:** v1.0
- **Ngày kiểm thử:** 27/10/2026
- **Phạm vi:** Kiểm tra trang tĩnh trên Microsoft Edge, kiểm tra nội dung/ảnh/điều hướng và bố cục ở các viewport 390 px, 768 px, 1280 px.
- **Lưu ý:** Đây là kiểm thử thủ công và kiểm tra trực tiếp trên trình duyệt; chưa có bộ kiểm thử tự động hoặc kiểm thử đa trình duyệt.

## Kết quả theo tiêu chí

| Tiêu chí | Kết quả | Kiểm tra và minh chứng |
|---|---|---|
| **Tính đúng đắn** | **Đạt một phần** | Trang mở được; tiêu đề đúng, 5/5 ảnh tải thành công và 4/4 liên kết điều hướng nội bộ trỏ tới mục tồn tại. Phát hiện đường dẫn LinkedIn (`/in/tru`) không khớp với địa chỉ hiển thị (`/in/truongnhatson`); chưa xác minh đích đến trên LinkedIn. Xem [ảnh desktop](screenshots/portfolio-desktop.png). |
| **UI/UX** | **Không đạt trên mobile** | Lưới dự án chuyển 1 cột ở 390 px, 2 cột ở 768 px và 3 cột ở 1280 px. Tuy nhiên, ảnh chụp ở 390 px cho thấy nội dung phần giới thiệu/ảnh đại diện bị cắt theo chiều ngang; cần sửa bố cục trước khi đánh giá giao diện mobile đạt. Giao diện desktop thể hiện đầy đủ các mục chính. Xem [ảnh mobile](screenshots/portfolio-mobile.png) và [ảnh desktop](screenshots/portfolio-desktop.png). |
| **Khả năng vận hành - xử lý lỗi** | **Đạt một phần** | Trang tĩnh và tài nguyên cục bộ hiển thị được khi mở trong trình duyệt; dự án không có backend hoặc xử lý lỗi ứng dụng riêng. Chưa kiểm thử qua máy chủ HTTP. Python và Docker không khả dụng trong môi trường kiểm thử nên chưa chạy được hướng dẫn máy chủ/Docker. |
| **Bảo mật** | **Đạt một phần** | Không phát hiện JavaScript hoặc backend xử lý dữ liệu trong phạm vi kiểm tra trang. Biểu mẫu đăng nhập chỉ là giao diện, không có `action`, trường nhập không bắt buộc và không triển khai xác thực; không nhập thông tin thật. Chưa thực hiện quét bảo mật, kiểm thử máy chủ hoặc đánh giá header bảo mật. |
| **Chất lượng mã nguồn** | **Đạt một phần** | HTML và CSS được tách thành các tệp, có cấu trúc khu vực và media query. Một số kiểu dáng vẫn được nhúng trực tiếp trong HTML; chưa có linter, validator HTML/CSS hay bộ kiểm thử tự động để xác nhận chất lượng toàn diện. |
| **Khả năng triển khai** | **Đạt một phần** | Website không cần bước build hay thư viện ngoài; có thể triển khai như nội dung tĩnh. Hướng dẫn Docker có trong README nhưng chưa chạy xác minh được vì Docker không được cài đặt trong môi trường kiểm thử. |

## Ảnh minh chứng

- [Giao diện desktop](screenshots/portfolio-desktop.png)
- [Giao diện mobile - ghi nhận lỗi nội dung bị cắt](screenshots/portfolio-mobile.png)

## Hạn chế và đề xuất

1. Điều chỉnh bố cục phần giới thiệu để nội dung và ảnh không bị cắt trên màn hình hẹp.
2. Sửa URL LinkedIn cho khớp với hồ sơ thực tế.
3. Nếu cần chức năng đăng nhập, cần có backend và cơ chế xác thực phù hợp; không dùng giao diện hiện tại để thu thập mật khẩu.
4. Chạy lại kiểm thử qua máy chủ HTTP và Docker, đồng thời bổ sung kiểm tra tự động và thử trên nhiều trình duyệt trước khi phát hành.