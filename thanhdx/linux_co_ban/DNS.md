# DNS Server
* DNS(Domain Name System) là hệ thống phân giải tên miền, giúp chuyển đổi tên miền để máy tính có thể giao tiếp với nhau.
## 1. Thành phần của DNS server:
* Resolver: Máy khách yêu cầu phân giải tên miền.
* Root DNS Server: Máy chủ gốc, cấp cao nhất trong hệ thống DNS.
* TLD (Top-Level Domain) Server: Máy chủ quản lý tên miền cấp cao(.com, .net, .org, .vn, ...).
* Authoritative DNS Server: Máy chủ chịu trách nhiệm cho tên miền cụ thể.
## 2. Các loại DNS Server:
* Caching DNS Server: Lưu cache kết quả truy vấn để tăng tốc độ truy cập.
* Forwading DNS Server: Chuyển tiếp yêu cầu phân giải đến DNS Server khác.
* Authoritative DNS Server: Cung cấp thông tin chính thức về tên miền.
## 3. Chức năng của DNS Server:
* Phân giải tên miền(Name Resolution): Chuyển đổi tên miền giúp máy tính giao tiếp với nhau.
* Lưu cache để tăng tốc độ truy vấn(Caching): DNS Server có thể lưu trữ tạm thời các bản ghi DNS để giảm thời gian phản hồi và tiết kiệm băng thông.
* Nếu DNS Server không có thông tin về tên miền, nó có thể chuyển tiếp yêu cầu đến DNS Server khác.
* Cung cấp thông tin về tên miền(Authoratative DNS): DNS Server có thể đóng vai trò là máy chủ quản lý tên miền, cung cấp bản ghi DNS cho các dịch vụ như website, emal.
* Cân bằng tải (Loading Balancing): DNS có thể phân phối lưu lượng truy cập giữa nhiều máy chủ bằng cách trả về các địa chỉ IP khác nhau theo từng yêu cầu.
* Chặn truy cập và bảo mật (Security & Filtering): DNS có thể được cấu hình để chặn truy cập vào các trang web độc hại hoặc áp dụng chính sách bảo mật.