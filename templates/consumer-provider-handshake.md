# Consumer–Provider Handshake

## Thông tin chung

- Lab: FIT4110 Lab 03
- Ngày: 11/06/2026
- Provider team: team-iot
- Consumer team: team-analytics
- Provider service: IoT Ingestion API
- Consumer service: Analytics API

## Contract

- Contract file: contracts/iot-ingestion.openapi.yaml
- Mock base URL: http://localhost:4012
- Auth method: Bearer Token
- Endpoint được test: POST /readings

## Smoke test

### Request

```http
POST /readings
Authorization: Bearer test-token
Content-Type: application/json
{
  "device_id": "ESP32-LAB-A01",
  "metric": "temperature",
  "value": 31.5,
  "unit": "celsius",
  "timestamp": "2026-05-13T08:30:00+07:00"
}
{
  "reading_id": "R-20260513-0001",
  "device_id": "ESP32-LAB-A01",
  "metric": "temperature",
  "accepted": true,
  "created_at": "2026-05-13T08:30:01+07:00"
}

## Kết quả
[x] Consumer gọi mock thành công.

[x] Consumer parse được field cần dùng.

[x] Consumer hiểu lỗi 4xx/5xx provider trả về.

[x] Có Newman report hoặc screenshot.
Ghi chú thay đổi hợp đồng
Nội dung | Trước | Sau | Người đồng ý | 
Cổng chạy Mock API | Chạy chung cổng mặc định | Tách cổng (Analytics: 4010, IoT: 4012) để tránh conflict | A1 & A5

## Xác nhận
Provider representative: Nhóm A1 (IoT)
Consumer representative: Nhóm A5 (Analytics) 