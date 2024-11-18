<!-- TOC -->
# 1. Giao thức mạng
## Định nghĩa: Giao thức mạng là tập hợp các quy tắc và quy định được sử dụng để điều chỉnh việc truyền thông dữ liệu giữa các thiết bị mạng trong máy tính. Chúng quy định cách thông tin được đóng gói, truyền tải và nhận diện trên mạng, đồng thời xác định cách các thiết bị trong mạng tương tác với nhau.
# 2. Các giao thức mạng phổ biến hiện nay
## 2.1 Giao thức Internet Protocol Suite(TCP/IP)
### Giao thức Internet Protocol Suite (hay còn gọi là TCP/IP – Transmission Control Protocol/Internet Protocol) là một bộ giao thức mạng chính thức và cơ bản được sử dụng rộng rãi trên Internet và trong hầu hết các mạng máy tính ngày nay. Nó định nghĩa một cách tiếp cận tiêu chuẩn để thiết lập và quản lý kết nối giữa các thiết bị trong mạng, đồng thời đảm bảo việc truyền tải dữ liệu.
### Bộ giao thức này gồm hai phần chính
### - Transmission Control Protocol (TCP): Được sử dụng để quản lý việc truyền tải dữ liệu từ một thiết bị tới thiết bị khác trên mạng một cách đáng tin cậy. TCP chịu trách nhiệm phân đoạn dữ liệu, đảm bảo nó được chuyển giao một cách đúng đắn và đầy đủ. Nó cũng quản lý các kết nối giữa các thiết bị.
### - Internet Protocol (IP): Là phần của TCP/IP quản lý việc định tuyến dữ liệu qua mạng. IP chịu trách nhiệm xác định địa chỉ của các thiết bị trong mạng (địa chỉ IP) và định tuyến dữ liệu từ nguồn đến đích thông qua một loạt các thiết bị mạng.
## 2.2 Giao thức Hyper Text Transfer Protocol(HTTP)
### Định nghĩa: Giao thức Hypertext Transfer Protocol (HTTP) là một trong những giao thức cơ bản nhất của Internet được sử dụng để truyền tải dữ liệu trên web. HTTP được sử dụng để truyền tải các trang web, hình ảnh, video, âm thanh và các tài nguyên khác qua Internet.
### - Nó hoạt động dựa trên mô hình yêu cầu/đáp ứng (request/response) giữa máy khách (client) và máy chủ (server). Khi bạn nhập một địa chỉ web vào trình duyệt, trình duyệt sẽ gửi yêu cầu (request) đến máy chủ web thông qua giao thức HTTP. Máy chủ sau đó sẽ đáp ứng (response) bằng cách gửi lại các dữ liệu được yêu cầu, chẳng hạn như trang web hoặc tài nguyên được yêu cầu, đến trình duyệt của bạn.
### - Các phiên bản khác nhau của HTTP (như HTTP/1.0, HTTP/1.1, HTTP/2, HTTP/3) có các cải tiến về hiệu suất, tốc độ truyền tải và khả năng tương tác. Ví dụ, HTTP/2 hỗ trợ việc tải trang web nhanh hơn thông qua việc sử dụng kỹ thuật multiplexing để truyền tải nhiều yêu cầu và đáp ứng đồng thời trên một kết nối. HTTP/3 sử dụng giao thức truyền tải dữ liệu QUIC để cải thiện hiệu suất và bảo mật.
## 2.3 Giao thức File Transfer Protocol (FTP)
### Định nghĩa: Giao thức File Transfer Protocol (FTP) là một trong những giao thức cổ điển nhất được sử dụng để truyền tải dữ liệu giữa các máy tính trên mạng. FTP cho phép người dùng truy cập và chia sẻ các tập tin từ xa giữa máy tính cá nhân và máy chủ.
### - Công việc chính của FTP là quản lý việc truyền tải các tệp tin qua mạng từ máy tính của người dùng (gọi là máy khách hoặc client) tới máy chủ (server) hoặc ngược lại. Người dùng có thể thực hiện các hoạt động như tải lên (upload) tệp tin lên máy chủ, tải xuống (download) tệp tin từ máy chủ về máy cá nhân, xóa tệp tin, tạo thư mục mới, di chuyển tệp tin giữa các thư mục trên máy chủ.
### - FTP thường sử dụng cổng 21 để thiết lập kết nối điều khiển (control connection) và một cổng khác để truyền tải dữ liệu (data connection). Mặc dù FTP đã được sử dụng rộng rãi trong quá khứ, nhưng do có một số hạn chế về bảo mật (như việc truyền dữ liệu một cách không được mã hóa), nên các phương thức truyền tải dữ liệu an toàn hơn như SFTP (Secure FTP), FTPS (FTP Secure), và các phương thức khác đã thay thế FTP trong nhiều trường hợp.
## 2.4 Giao thức Secured Shell (SSH)
### Định nghĩa: Giao thức Secured Shell (SSH) là một giao thức mạng được sử dụng để thiết lập kết nối an toàn giữa hai thiết bị, thường là giữa máy tính client và server, cho phép người dùng truy cập và điều khiển từ xa một cách bảo mật.
### - SSH cung cấp một cách thức đáng tin cậy để mã hóa thông tin được truyền tải qua mạng, ngăn chặn các mối đe dọa bảo mật như nghe trộm dữ liệu. Nó cũng xác thực danh tính của cả client và server, đảm bảo rằng người dùng kết nối với máy chủ đúng và ngược lại.
### Các ứng dụng của SSH bao gồm:
### - Điều khiển từ xa: SSH cho phép người dùng truy cập và điều khiển từ xa một máy tính hoặc máy chủ từ bất kỳ đâu có kết nối mạng.
### - Truyền tải dữ liệu an toàn: Ngoài việc cung cấp khả năng truy cập từ xa, SSH cũng cho phép truyền tải dữ liệu một cách an toàn qua mạng.
### - Mã hóa: SSH sử dụng các thuật toán mã hóa mạnh mẽ để bảo vệ thông tin truyền tải qua mạng, đảm bảo tính toàn vẹn và bảo mật của dữ liệu.
## 2.5 Giao thức Simple Mail Transfer Protocol (SMTP)
### Định nghĩa: Giao thức Simple Mail Transfer Protocol (SMTP) là một trong những giao thức chính để gửi và nhận email trên Internet. SMTP chịu trách nhiệm cho việc truyền tải email từ máy tính của người gửi đến máy chủ email của người nhận.
### Ứng dụng: 
### - Khi bạn gửi email, client email của bạn (như Gmail, Outlook, Thunderbird) sử dụng SMTP để gửi email đi. Thông thường, máy chủ SMTP của nhà cung cấp dịch vụ email sẽ xác định máy chủ email của người nhận dựa trên địa chỉ email của họ. Sau đó, nó sẽ liên lạc với máy chủ email đó thông qua giao thức SMTP để gửi email đi. Máy chủ email của người nhận sau đó sẽ nhận và lưu trữ email cho người dùng đó.
### - SMTP thường sử dụng cổng 25 hoặc 587. Mặc dù SMTP đảm bảo việc truyền tải email từ máy chủ này đến máy chủ khác, nhưng không mã hóa dữ liệu. Điều này có thể tạo ra một vấn đề về bảo mật khi thông tin nhạy cảm như mật khẩu hoặc nội dung email được truyền đi.
## 2.6 Giao thức Domain Name System (DNS)
### Định nghĩa: Giao thức Domain Name System (DNS) là một hệ thống cơ bản quản lý việc ánh xạ các tên miền (như example.com, google.com) sang địa chỉ IP (Internet Protocol) tương ứng của máy chủ trong mạng Internet.
### Ứng dụng:
### - Khi bạn nhập một tên miền vào trình duyệt web, ví dụ như “www.example.com“, trình duyệt cần biết địa chỉ IP của máy chủ để truy cập nội dung trang web. DNS giúp chuyển đổi tên miền này thành địa chỉ IP tương ứng.
### + Người dùng nhập tên miền: Người dùng nhập tên miền vào trình duyệt web.
### + Truy vấn DNS: Trình duyệt gửi yêu cầu tới máy chủ DNS (thường là máy chủ DNS của nhà cung cấp dịch vụ Internet của bạn hoặc máy chủ DNS cấu hình trên mạng của bạn).
### + Phân giải tên miền: Máy chủ DNS sẽ tìm kiếm và trả về địa chỉ IP tương ứng với tên miền được yêu cầu.
### + Trình duyệt truy cập địa chỉ IP: Trình duyệt sẽ sử dụng địa chỉ IP này để truy cập máy chủ và lấy nội dung của trang web.
## 2.7 Giao thức Post Office Protocol(POP)
### Định nghĩa: Giao thức Post Office Protocol version 3 (POP3) là một trong những giao thức chính để lấy email từ máy chủ email và lưu trữ nó trên máy tính cá nhân của người dùng.
### Ứng dụng:
### - Khi bạn sử dụng một ứng dụng email như Outlook, Thunderbird hoặc một ứng dụng email khác, POP3 được sử dụng để tải email từ máy chủ email của bạn về thiết bị cá nhân.
### - Quá trình hoạt động của POP3:
### + Kết nối với máy chủ email: Ứng dụng email sẽ thiết lập kết nối với máy chủ email của bạn thông qua giao thức POP3, thường sử dụng cổng 110 hoặc cổng 995 nếu kết nối được mã hóa (POP3S).
### + Xác thực đăng nhập: Bạn cần cung cấp thông tin xác thực (tên đăng nhập và mật khẩu) để đăng nhập vào tài khoản email của mình trên máy chủ.
### + Lấy email từ máy chủ: Sau khi xác thực thành công, giao thức POP3 sẽ cho phép bạn tải về các email từ hộp thư đến (inbox) trên máy chủ email của bạn về thiết bị cá nhân.
### + Xử lý email: Email được tải về từ máy chủ và thường được lưu trữ trên thiết bị cá nhân của bạn. Mặc định, POP3 thường cấu hình để xóa email từ máy chủ sau khi đã tải về (tuy nhiên, có thể cấu hình để không xóa email sau khi tải về).