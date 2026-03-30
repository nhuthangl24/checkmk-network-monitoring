# checkmk-network-monitoring

## Tổng quan dự án

Dự án xây dựng hệ thống giám sát hạ tầng mạng và dịch vụ quy mô doanh nghiệp sử dụng **Checkmk**, phục vụ bài tập lớn cuối kỳ.

Hệ thống không chỉ giám sát thiết bị mạng mà còn theo dõi máy chủ, dịch vụ, hiệu năng và cảnh báo sự cố theo thời gian thực.

## Sơ đồ hoạt động

```text
                          +----------------------+
                          |    Người quản trị    |
                          | Dashboard / Alerts   |
                          +----------+-----------+
                                     |
                                     v
                     +-----------------------------------+
                     |          Checkmk Server           |
                     | Monitoring + Rules + Alerts       |
                     | Reports + SLA + Event Handling    |
                     +----------+------------+-----------+
                                |            |
                    ------------             -------------
                   /                                         \
                  v                                           v
        +---------------------+                    +----------------------+
        |   Thiết bị mạng     |                    |   Hệ thống dịch vụ   |
        | Router / Switch     |                    | Web / DB / DNS / SSH |
        | Firewall / AP       |                    | Mail / File Server   |
        +----------+----------+                    +----------+-----------+
                   |                                          |
                   v                                          v
        +---------------------+                    +----------------------+
        | Hiệu năng mạng      |                    | Hiệu năng hệ thống   |
        | Bandwidth / Packet  |                    | CPU / RAM / Disk     |
        | Interface Errors    |                    | Process / Service    |
        +---------------------+                    +----------------------+
                                \                /
                                 \              /
                                  v            v
                         +---------------------------+
                         |  Cảnh báo & Phân tích     |
                         | Email / Telegram / Logs   |
                         | Downtime / Root Cause     |
                         +---------------------------+
```

## Luồng triển khai

1. Kết nối thiết bị mạng và máy chủ vào hệ thống giám sát
2. Cấu hình SNMP hoặc agent cho từng node
3. Thiết lập rule theo dõi hiệu năng và trạng thái dịch vụ
4. Cấu hình ngưỡng cảnh báo
5. Hiển thị dashboard và báo cáo
6. Phân tích sự cố khi có downtime hoặc vượt ngưỡng

## Chức năng dự kiến

* Giám sát hạ tầng mạng
* Giám sát máy chủ và dịch vụ
* Theo dõi CPU / RAM / Disk / Bandwidth
* Cảnh báo sự cố
* Dashboard và báo cáo SLA

## Ghi chú

Tài liệu này là bản định hướng mở rộng cho project phục vụ bài tập lớn cuối kỳ.
