# Minh chứng Buổi 1

Thư mục này dùng để nộp minh chứng thiết lập môi trường lab.

## Sinh viên điền thông tin

- Họ tên:Phạm Đình Minh Trưởng
- Mã sinh viên:1771020705
- Nhóm:A5
- Vai trò dự kiến trong nhóm: Phân tích yêu cầu, chuẩn bị minh chứng và kiểm tra môi trường lab
- Hệ điều hành:Windows
- Ghi chú: Đã ghi minh chứng trong `evidence/buoi-01/`, gồm ảnh Docker, ảnh Compose, log smoke test và tài liệu service boundary.

## Các file minh chứng nên có

- `docker-hello.png`
- `docker-compose.png`
- `smoke-test-result.txt`
- `service-boundary.md`
- `known-issues.md`

Nếu nhóm cần nộp thêm phần tự động sinh môi trường, có thể giữ lại các file text bổ sung như `tool-versions.txt`, `docker-version.txt`, `compose-version.txt`, `hello-world.txt`, `image-list.txt`, `git-log.txt`, `checklist.md`.

## Cách sinh file tự động

macOS/Linux:

```bash
./scripts/collect_session01_evidence.sh
```

Windows:

```powershell
.\scripts\collect_session01_evidence.ps1
```
