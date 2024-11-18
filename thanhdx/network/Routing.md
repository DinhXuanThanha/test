# Routing(Định tuyến)
## Định nghĩa: Routing là kỹ thuật chọn đường đi cho dữ liệu từ mạng này đến mạng khác sao cho dữ liệu đến được đích cuối cùng một cách hiệu quả. Quá trình này diễn ra ở tầng Network (tầng 3) của mô hình OSI, sử dụng địa chỉ IP để định tuyến các gói tin.
## Vai trò của routing: Routing giúp tối ưu hóa việc truyền dữ liệu qua các mạng lớn và phức tạp bằng cách chọn đường đi phù hợp nhất, đảm bảo độ trễ thấp, băng thông tốt và an toàn cho dữ liệu. Điều này rất quan trọng khi mạng có nhiều đường dẫn khác nhau, đặc biệt là trong môi trường mạng Internet.
## Các loại routing
### 1. Static Routing (Định tuyến tĩnh): Các đường dẫn được cấu hình thủ công bởi quản trị viên mạng. Thích hợp cho mạng nhỏ và ổn định, nhưng không linh hoạt khi mạng có sự thay đổi.
### 2. Dynamic Routing (Định tuyến động): Sử dụng các giao thức định tuyến để tự động cập nhật và duy trì bảng định tuyến. Thích hợp cho mạng lớn và phức tạp vì router có thể tự động chọn đường dẫn tối ưu khi có thay đổi trong mạng.
## Giao thức routing
## - Các giao thức định tuyến là bộ quy tắc giúp router trao đổi thông tin để cập nhật bảng định tuyến và chọn đường đi.
### 1. RIP (Routing Information Protocol): Một giao thức định tuyến dựa trên khoảng cách (distance vector), sử dụng số lượng bước nhảy để xác định đường đi tốt nhất. Thường dùng cho mạng nhỏ.
### 2. OSPF (Open Shortest Path First): Giao thức định tuyến dựa trên trạng thái liên kết (link-state) và sử dụng thuật toán Dijkstra để tìm đường đi ngắn nhất. Phù hợp với mạng lớn.
### 3. BGP (Border Gateway Protocol): Giao thức định tuyến giữa các hệ thống tự trị (AS) trong mạng Internet, chịu trách nhiệm định tuyến giữa các mạng khác nhau trên toàn cầu.
## Các thành phần của routing
### 1. Routing Table (Bảng định tuyến): Lưu trữ các thông tin về các tuyến đường khả dụng và đường đi tốt nhất đến các mạng đích.
### 2. Routing Metrics (Tham số định tuyến): Là các chỉ số để đánh giá mức độ tốt của đường đi như băng thông, độ trễ, số bước nhảy.
### 3. Routing Algorithm (Thuật toán định tuyến): Các thuật toán được sử dụng để chọn đường đi tốt nhất, có thể dựa trên khoảng cách, chi phí, hoặc trạng thái liên kết.