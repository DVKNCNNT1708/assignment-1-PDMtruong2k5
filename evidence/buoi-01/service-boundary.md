# Service Boundary Diagram - Product A: Analytics

## 1. Thông tin nhóm

- Tên nhóm: CNTT 17-08 Nhóm 05
- Lớp: FIT 4110
- Thành viên: Phạm Đình Minh Trưởng - 1771020705
- Service nhóm phụ trách: Analytics
- Sản phẩm tổng thể của lớp: Hệ thống dịch vụ tổng hợp và phân tích dữ liệu

Mục tiêu hệ thống: thu thập dữ liệu từ nhiều nguồn, xử lý, tổng hợp, phân tích và cung cấp báo cáo trực quan để hỗ trợ ra quyết định.

## 2. Actor

- Admin / Manager: xem dashboard, báo cáo và quản lý hệ thống.
- Data Analyst: truy vấn dữ liệu, phân tích và xuất báo cáo.
- Web / Application: gửi dữ liệu sự kiện, log hành vi người dùng.
- Mobile App: gửi dữ liệu sự kiện, log hành vi người dùng.
- External Systems: CRM, ERP, IoT và các hệ thống bên ngoài.

## 3. System Boundary

Phần nhóm kiểm soát nằm trong khối Analytics System:

- API Gateway
- Data Ingestion Service
- Data Processing Service
- Analytics Service
- Dashboard / Visualization
- User Service
- Security & Authorization

Phần nhóm chỉ tích hợp bên ngoài biên hệ thống:

- Nguồn dữ liệu từ web/app/hệ thống khác
- Cơ sở hạ tầng cloud
- Dịch vụ lưu trữ, queue, cache, monitoring
- Hệ thống CI/CD và triển khai

## 4. Service Boundary

Service của nhóm chịu trách nhiệm:

- Nhận dữ liệu từ nhiều nguồn qua API Gateway.
- Kiểm tra, chuẩn hóa và đưa dữ liệu vào pipeline xử lý.
- Thực hiện ETL/ELT, batch processing và stream processing.
- Tính toán KPI, metrics, aggregation và business logic phân tích.
- Cung cấp dashboard, biểu đồ và xuất báo cáo.
- Quản lý người dùng, vai trò và phân quyền truy cập.

Service KHÔNG làm:

- Không sở hữu trực tiếp nguồn dữ liệu bên ngoài.
- Không thay thế hoàn toàn các hệ thống CRM/ERP/IoT.
- Không tự vận hành hạ tầng cloud hay container runtime.
- Không xử lý yêu cầu ngoài phạm vi API và quyền truy cập đã định nghĩa.

## 5. Input / Output

### Input

- Dữ liệu sự kiện từ web/app/mobile.
- Dữ liệu từ external systems qua tích hợp.
- Yêu cầu truy vấn, xem dashboard, xuất báo cáo.
- Thông tin xác thực và phân quyền người dùng.

### Output

- Dữ liệu đã làm sạch và chuẩn hóa.
- Chỉ số KPI, metric, aggregation.
- Dashboard, biểu đồ và báo cáo xuất file.
- Phản hồi API cho các dịch vụ tích hợp.

## 6. API dự kiến

| Method | Endpoint | Mục đích |
|---|---|---|
| GET | /health | Kiểm tra service |
| POST | /ingest | Nhận dữ liệu đầu vào |
| GET | /analytics/summary | Lấy số liệu tổng hợp |
| GET | /dashboard | Xem dashboard |
| POST | /auth/login | Xác thực người dùng |

## 7. Phụ thuộc service khác

- Gọi đến Database PostgreSQL/MongoDB để lưu trữ dữ liệu.
- Gọi Cache Redis cho dữ liệu truy xuất nhanh.
- Gọi Queue Kafka/RabbitMQ cho xử lý bất đồng bộ.
- Có thể gọi Object Storage như AWS S3 hoặc GCP Cloud Storage.
- Tích hợp Monitoring & Logging bằng Prometheus, Grafana hoặc ELK.

Các service khác có thể gọi vào hệ thống qua API Gateway để gửi dữ liệu hoặc truy vấn kết quả.

## 8. Công nghệ nền tảng

- Backend: Node.js hoặc Python/FastAPI.
- Database: PostgreSQL hoặc MongoDB.
- Data Warehouse: BigQuery hoặc Redshift.
- Cache: Redis.
- Queue / Streaming: Kafka hoặc RabbitMQ.
- Container: Docker.
- Authentication: JWT hoặc OAuth 2.0.
- CI/CD: GitLab CI hoặc GitHub Actions.

## 9. Ghi chú minh họa

Ảnh minh họa trong bộ minh chứng nên được lưu riêng ở `evidence/buoi-01/` để dễ đối chiếu với phần mô tả boundary.
