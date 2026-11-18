# Website quản lý chuỗi trung tâm thể thao

Dự án nhóm xây dựng website quản lý chuỗi trung tâm thể thao, ưu tiên triển khai nghiệp vụ cho cơ sở Calisthenics.

## Cấu trúc project

```text
.
├── README.md                    # Hướng dẫn của repo
└── Web-trungtamthethao/         # Thư mục gốc của website
    ├── index.html               # Trang chủ và danh sách các môn
    ├── shared/
    │   └── style.css            # Kiểu hiển thị dùng chung
    └── sports/
        └── calisthenics/
            └── index.html       # Trang riêng của Calisthenics
```

## Website hoạt động như thế nào

1. Máy chủ HTTP phục vụ các tệp trong `Web-trungtamthethao/`. Khi mở địa chỉ gốc, trình duyệt tải `index.html` và hiển thị danh sách các môn.
2. Khi chọn **Calisthenics**, trình duyệt mở `sports/calisthenics/index.html`. Liên kết **Quay về trang chủ** dùng `../../index.html` để trở lại.
3. Cả hai trang tải cùng một tệp CSS. Trang chủ dùng `shared/style.css`, còn trang Calisthenics dùng `../../shared/style.css`. Các đường dẫn tương đối cho phép giữ nguyên liên kết khi website được phục vụ dưới một đường dẫn con.

Phiên bản hiện tại dùng HTML và CSS để hiển thị và điều hướng. Website chưa có JavaScript, backend, cơ sở dữ liệu hay chức năng quản lý.

## Chạy website trên Windows

Mở thư mục gốc của repo trong VS Code. Đây là thư mục chứa `README.md`. Mã website nằm trong thư mục con `Web-trungtamthethao/`. Website dùng HTML và CSS tĩnh, không cần bước build.

Trong terminal PowerShell của VS Code, chạy lệnh sau từ thư mục gốc của repo với Python đã cài đặt.

```powershell
py -m http.server 8000 --bind 127.0.0.1 --directory Web-trungtamthethao
```

Mở [trang chủ](http://127.0.0.1:8000/) rồi chọn **Calisthenics**. Dùng `Ctrl+C` trong terminal để dừng máy chủ.

## Thêm một môn thể thao

Tạo `Web-trungtamthethao/sports/ten-mon/index.html`. Đặt CSS, JavaScript và hình ảnh riêng của môn đó cùng thư mục khi cần. Đặt tài nguyên dùng ở nhiều trang trong `Web-trungtamthethao/shared/`.

Khi trang môn đã có, thêm liên kết `sports/ten-mon/index.html` vào danh sách môn trong `Web-trungtamthethao/index.html`. Ở trang môn, dùng `../../index.html` để quay về trang chủ. Dùng đường dẫn tương đối cho cả liên kết và tài nguyên.

## Quy trình làm việc nhóm

1. Cập nhật `main` trước khi sửa.

   ```powershell
   git switch main
   git pull --ff-only origin main
   ```

2. Chạy thử và kiểm tra liên kết trong menu, tài nguyên dùng chung và các luồng bị ảnh hưởng. Dùng `git status` và `git diff` để xem thay đổi trước khi chọn tệp commit.
3. Commit và push lên `main`. Ví dụ khi thêm một môn:

   ```powershell
   git add Web-trungtamthethao/sports/ten-mon Web-trungtamthethao/index.html
   git commit -m "Thêm môn thể thao"
   git push origin main
   ```
