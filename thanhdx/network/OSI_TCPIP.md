<!-- OSI_TCP/IP-TOC -->
# [Mô hình OSI](#mô-hình-osi)
## [1. Mô hình OSI gồm 7 tầng](#1-mô-hình-osi-gồm-7-tầng)
## [2. Các nguyên tắc phân tầng mô hình OSI](#3-các-giao-thức-trong-mô-hình-osi)
## [3. Các giao thức trong mô hình OSI](#3-các-giao-thức-trong-mô-hình-osi)
## [4. Vai trò của các tầng](#3-các-giao-thức-trong-mô-hình-osi)
## [5. TCP (Transmission Control Protocol)](#5-tcptransmission-control-protocols)
## [6. UDP (User Datagram Protocol)](#6-udpuser-datagram-protocols)
## [7. TCP/IP(Transmission Control Protocols / Internet Protocols)](#7-tcpiptransmission-control-protocols--internet-protocols-1)

# Mô hình OSI
## Định nghĩa: OSI là mô hình căn bản về tiến trình truyền thông, thiết lập các tiêu chuẩn kiến trúc mạng ở mức quốc tế, là cơ sở chung để các hệ thống khác nhau có thể liên kết và truyền thông được với nhau.
## 1. Mô hình OSI gồm 7 tầng:
### 1. Tầng vật lý (Physical)
### 2. Tầng liên kết (Data Link)
### * 3. Tầng mạng (Network)
### * 4. Tầng vận chuyển (Transport)
### 5. Tầng phiên (Session)
### 6. Tầng trình bày (Presentation)
### * 7. Tầng ứng dụng (Application)
## 2. Các nguyên tắc phân tầng mô hình OSI
### - Mô hình OSI gồm 7 tầng. OSI là hệ thống mở, có khả năng kết nối tới các hệ thống khác nhau, tương thích với các chuẩn OSI
### - Quá trình xử lý các ứng dụng được thực hiện trong các hệ thống mở, đồng thời duy trì các hoạt động kết nối giữa các hệ thống
### -  Thiết lập kênh logic nhằm mục đích thực hiện việc trao đổi thông tin giữa các thực thể
## 3. Các giao thức trong mô hình OSI:
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
## 4. Vai trò của các tầng
### 1. Tầng vật lý:
### - Xử lý truyền dữ liệu dưới dạng tín hiệu vật lý qua các môi trường truyền dữ liệu như cáp đồng, cáp quang hoặc sóng vô tuyến
### - Chức năng chính: 
### + Chuyển đổi bit thành các tín hiệu điện từ / sóng
### + Định nghĩa các thông số kỹ thuật như loại cáp, tần số, điện áp
### + Quản lý kết nối vật lý giữa các thiết bị
### 2. Tầng liên kết dữ liệu
### - Đảm bảo truyền dữ liệu giữa hai nút mạng liền kề một các chính xác và không lỗi 
### - Chức năng chính: 
### + Phát hiện và sửa lỗi trong quá trình truyền
### + Điều khiển truy cập vào quá trình truyền dẫn
### + Chia dữ liệu thành các khung (frame) và đánh số chúng
### 3. Tầng mạng
### - Chịu trách nhiệm định tuyến dữ liệu từ nguồn đến đích quan nhiều mạng trung gian
### - Chức năng chính:
### + Định địa chỉ IP cho các thiết bị trên mạng
### + Thực hiện định tuyến và chuyển tiếp gói tin
### + Phân chia hoặc ghép nối gói tin nếu cần
### 4. Tầng vận chuyển
### - Đảm bảo dữ liệu được truyền từ đầu cuối này đến đầu cuối khác một cách đáng tin cậy và theo đúng thứ tự
### - Chức năng chính:
### + Chia nhỏ dữ liệu thành các phân đoạn
### + Kiểm soát lưu lượng và xử lý tắc nghẽn
### + Cung cấp giao thức truyền tin có đảm bảo TCP hoặc không đảm bảo UDP
### 5. Tầng phiên
### - Thiết lập, duy trì và kết thúc phiên giao tiếp giữa hai thiết bị
### - Chức năng chính:
### + Quản lý giao tiếp
### + Đồng bộ hóa dữ liệu và thực hiện phục hồi khi kết nối gặp gián đoạn
### + Quản lý nhiều kết nối cùng lúc giữa các ứng dụng
### 6. Tầng trình bày
### - Đảm bảo dữ liệu truyền qua mạng được định dạng chính xác và có thể đọc được bởi ứng dụng ở đầu nhận
### - Chức năng chính:
### + Mã hóa / Giải mã dữ liệu
### + Nén dữ liệu
### + Chuyển đổi định dạng dữ liệu
### 7. Tầng ứng dụng
### - CUng cấp giao diện giữa người dùng và ứng dụng mạng
### - Chức năng chính:
### + Cung cấp các dịch vụ như email, truyền file(FTP), duyệt web(HTTP)
### + Đảm bảo tính bảo mật và xác thực trong giao tiếp (SSL/TLS)
### + Quản lý các giao thức ứng dụng như HTTP, SMTP, FTP
## 5. TCP(Transmission Control Protocols)
### Định nghĩa: TCP là giao thức truyền thông tin định hướng kết nối, đảm bảo độ tin cậy và thứ tự trong việc truyền dữ liệu giữa hai thiết bị. Nó sử dụng các cơ chế kiểm tra lỗi và xác nhận để đảm bảo rằng tất cả các gói dữ liệu được gửi và nhận chính xác
### - Định hướng kế nối: TCP thiết lập một kết nối giữa hai thiết bị trước khi truyền dữ liệu
### - Đảm bảo độ tin cậy: TCP đảm bảo rằng dữ liệu được gửi và nhận chính xác bằng cách sử dụng kiểm tra lỗi vàg xác nhận. Nếu gói tin bị mất, nó sẽ gửi lại
### - Truyền dữ liệu theo thứ tự: Dữ liệu được gửi qua TCP sẽ được nhận theo thứ tự mà nó được gửi
### - Tốc độ: Do có nhiều tính năng kiểm soát, TCP thường chậm hơn so với UDP
## TCP thích hợp cho các ứng dụng cần độ tin cậy như web, email, và truyền file
## 6. UDP(User Datagram Protocols)
### Định nghĩa: UDP là giao thức truyền thông tin không định hướng kết nối, cho phép dữ liệu mà không đảm bảo độ tin cậy hoặc thứ tự. UDP nhanh hơn TCP, nhưng không có các cơ chế để đảm bảo rằng gói dữ liệu đến nơi an toàn hoặc đúng thứ tự
### Không định hướng kết nối: UDP không thiết lập kết nối trước khi gửi dữ liệu mà gửi luôn dữ liệu
### Không đảm bảo độ tin cậy: UDP không kiểm tra lỗi hay xác nhận, nên không đảm bảo dữ liệu được nhận chính xác
### Không theo thứ tự: Các gói dữ liệu có thể đến theo thứ tự khác với thứ tự gửi
### Tốc độ: UDP nhanh hơn TCP vì không cần các bước kiểm tra lỗi và xác nhận
## UDP thích hợp cho các ứng dụng yêu cầu tốc độ nhanh hơn và có thể chấp nhận mất mát dữ liệu, chẳng hạn như video streaming, voice over IP(VoiIP), game online
# 7. TCP/IP(Transmission Control Protocols / Internet Protocols)
## Định nghĩa: TCP/IP là bộ giao thức trao đổi thông tin được sử dụng để truyền tải và kết nối các thiết bị trong mạng Internet. TCP/IP được phát triển để mạng được tin cậy hơn cùng với khả năng phục hồi tự động
## Chức năng của các tầng TCP/IP
### - Một mô hình TCP/IP tiêu chuẩn bao gồm 4 lớp được chồng lên nhau, bắt đầu từ tầng thấp nhất là tầng vật lý(Physical) -> Tầng mạng(Network) -> Tầng giao vận(Transport) và cuối cùng là tầng ứng dụng(Application)
### 1. Tầng vật lý
### - Là sự kết hợp giữa tầng vật lý và tầng liên kết dữ liệu của mô hình OSI. Chịu trách nhiệm truyền dữ liệu giữa hai thiết bị trong cùng 1 mạng
### - Tại đây các gói dữ liệu được đóng vào khung(frame) và được định tuyến đến đích đã được chỉ định ban đầu
### 2. Tầng mạng
### - Gần giống như tầng mạng của mô hình OSI. Tại đây, nó cũng được định nghĩa là một giao thức chịu trách nhiệm truyền tải dữ liệu một cách logic trong mạng
### - Các phân đoạn dữ liệu sẽ được đóng gói(package) với kích thước mỗi gói phù hợp với mạng chuyển mạch mà nó dùng để truyền dữ liệu 
### - Lúc này các gói tin được chèn thêm phàn Header chứa thông tin của tầng mạng và tiếp tục được chuyển đến tầng tiếp theo. Các giao thức hính trong tầng này là IP, ICMP và ARP
### 3. Tầng vận chuyển
### - Chức năng chính của tầng 3 là xử lý vấn đề giao tiếp giữa các máy chủ trong cùng một mạng hoặc khác mạng được kết nối với nhau thông qua bộ định tuyến. Tại đây dữ liệu sẽ được phân đoạn, mỗi đoạn sẽ không bằng nhau nhưng kích thước phải nhỏ hơn 64KB.
### - Trong tầng này còn 2 giao thức cốt lõi là TCP và UDP. Trong đó TCP đảm bảo chất lượng gói tin nhưng tiêu tốn thời gian khá lâu để kiểm tra đầy đủ thông tin từ thứ tự dữ liệu cho đến việc kiểm soát các vấn đề tắc nghẽn lưu lượng dữ liệu. Trái với điều đó, UDP cho thấy tốc độ truyền tải nhanh hơn nhưng lại không đảm bảo được chất lượng dữ liệu gói tin
### 4. Tầng ứng dụng
### - Đây là lớp giao tiếp trên cùng của mô hình. Tầng ứng dụng đảm nhận vai trò giao tiếp dữ liệu 2 máy khác nhau thông qua các dịch vụ mạng khác nhau
<!-- OSI_TCP/IP-TOC-config 
    numbering=true
    autoSave=true
    /OSI_TCP/IP-TOC-config-->
<!-- /OSI_TCP/IP-TOC -->