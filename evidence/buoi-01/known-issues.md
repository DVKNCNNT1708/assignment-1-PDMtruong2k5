# Known Issues · Buổi 1

Ghi lại lỗi chưa xử lý được hoặc đã xử lý xong trong quá trình chuẩn bị minh chứng.

| STT | Lỗi gặp phải | Lệnh gây lỗi | Cách đã thử | Trạng thái |
|---:|---|---|---|---|
| 1 | PowerShell chặn chạy file `.ps1` theo execution policy mặc định | `scripts/smoke_test.ps1` | Chạy lại bằng `powershell -ExecutionPolicy Bypass -File scripts/smoke_test.ps1` | Đã xử lý |
| 2 | Một số Docker image chưa có sẵn local nên smoke test chỉ cảnh báo | `scripts/smoke_test.ps1` | Chạy `scripts/pull_all.ps1` để kéo đủ image | Đang theo dõi |
| 3 | Mini-stack compose dùng port `8081` và `5000`, có thể bị trùng port nếu máy đã dùng sẵn | `compose/docker-compose.smoke.yml` | Kiểm tra tiến trình đang chiếm port hoặc đổi mapping khi cần | Đang theo dõi |
| 4 | File log sinh ra trên Windows có thể ở mã hóa UTF-16 | `scripts/smoke_test.ps1` | Mở bằng encoding Unicode hoặc đổi script sang UTF-8 nếu cần | Chấp nhận được |
