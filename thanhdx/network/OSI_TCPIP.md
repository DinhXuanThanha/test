# Mô hình OSI
## Định nghĩa: OSI là mô hình căn bản về tiến trình truyền thông, thiết lập các tiêu chuẩn kiến trúc mạng ở mức quốc tế, là cơ sở chung để các hệ thống khác nhau có thể liên kết và truyền thông được với nhau.
## Mô hình OSI gồm 7 tầng:
### 1. Tầng vật lý (Physical)
### 2. Tầng liên kết (Data Link)
### 3. Tầng mạng (Network)
### 4. Tầng vận chuyển (Transport)
### 5. Tầng phiên (Session)
### 6. Tầng trình bày (Presentation)
### 7. Tầng ứng dụng (Application)
## Các nguyên tắc phân tầng mô hình OSI
### - Mô hình OSI gồm 7 tầng. OSI là hệ thống mở, có khả năng kết nối tới các hệ thống khác nhau, tương thích với các chuẩn OSI
### - Quá trình xử lý các ứng dụng được thực hiện trong các hệ thống mở, đồng thời duy trì các hoạt động kết nối giữa các hệ thống
### -  Thiết lập kênh logic nhằm mục đích thực hiện việc trao đổi thông tin giữa các thực thể
## Các giao thức trong mô hình OSI:
### Giao thức hướng liên kết (Connected Oriented Protocols)
### - Định nghĩa: Giao thức này thiết lập một kết nối trước khi truyền dữ liệu. Dữ liệu được truyền trong một phiên làm việc đã được thiết lập, và thường có cơ chế kiếm soát lỗi và quản lý luồng
### - Đặc điểm: 
### + Đảm bảo độ tin cậy và thứ tự
### + Thích hợp cho các ứng dụng yêu cầu độ chính xác cao, như truyền tệp tin
### Giao thức không liên kết (Connections Protocols)
### - Định nghĩa: Giao thức này không yêu cầu thiết lập một kết nối trước khi truyền dữ liệu. Mỗi gói dữ liệu được gửi độc lập và không cần phải theo thứ tự
### - Đặc điểm: 
### + Thích hợp cho các ứng dụng cần tốc độ nhanh hơn và không cần độ tin cậy cao, như streamin, game
### + Không đảm bảo thứ tự hoặc tính toàn vẹn của dữ liệu
## Vai trò của các tầng
### 1. Tầng vật lý:
### - Xử lý truyền dữ liệu dưới dạng tín hiệu vật lý qua các môi trường truyền dữ liệu như cáp đồng, cáp quang hoặc sóng vô tuyến
### - Chức năng chính: 
### + Chuyển đổi bit thành các tín hiệu điện từ / sóng
### + Định nghĩa các thông số kỹ thuật như loại cáp, tần số, điện áp
### + Quản lý kết nối vật lý giữa các thiết bị
