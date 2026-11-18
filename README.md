# Website quản lý chuỗi trung tâm thể thao

Dự án nhóm xây dựng website quản lý chuỗi trung tâm thể thao, ưu tiên triển khai nghiệp vụ cho cơ sở Calisthenics.

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

1. Cập nhật `main` và tạo nhánh riêng cho công việc của mình.

   ```powershell
   git switch main
   git pull --ff-only origin main
   git switch -c ten-thanh-vien/them-ten-mon
   ```

2. Chạy thử rồi kiểm tra `git status` và `git diff`. Chọn các tệp của mình để commit, sau đó push nhánh lên `origin`.

   ```powershell
   git add Web-trungtamthethao/sports/ten-mon Web-trungtamthethao/index.html
   git commit -m "Thêm môn thể thao"
   git push -u origin ten-thanh-vien/them-ten-mon
   ```

3. Mở pull request từ nhánh riêng vào `main` trên GitHub.
4. Trước khi merge, người phụ trách tích hợp kiểm tra các liên kết trong menu, việc tải tài nguyên dùng chung và các luồng đang hoạt động của website trên bản có thay đổi.
﻿# Website quản lý chuỗi trung tâm thể thao

Dự án nhóm xây dựng website quản lý chuỗi trung tâm thể thao, ưu tiên triển khai nghiệp vụ cho cơ sở Calisthenics.
