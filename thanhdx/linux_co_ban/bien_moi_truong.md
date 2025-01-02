# Biến môi trường 
*  Biến môi trường là các đại lượng có các giá trị cụ thể. Một số biến môi trường được cung cấp các giá trị đặt trước của hệ thống và các biến khác được đặt trực tiếp bởi người dùng, tại dòng lệnh hoặc trong khi khởi động các tập lệnh khác.
* Các biến môi trường cho phép bạn tùy chỉnh cách hệ thống hoạt động và hành vi của các ứng dụng trên hệ thống.
* Biến môi trường là một chuỗi ký tự chứa thông tin được sử dụng bởi một hoặc nhiều ứng dụng.
## Các biến môi trường
### Một số lệnh có sẵn cho phép liệt kê và đặt các biến môi trường trong Linux như sau:
* env - Lệnh cho phép bạn chạy chương trình khác trong môi trường tùy chỉnh mà không cần sửa đổi chương trình hiện tại. Khi được sử dụng mà không có đối số, nó sẽ in ra danh sách các biến môi trường hiện tại.
* printenv - Lệnh in ra tất cả hoặc các biến môi trường được chỉ định.
* set - Lệnh đặt hoặc bỏ thiết lập các biến shell. Khi được sử dụng mà không có đối số, nó sẽ in ra danh sách tất cả các biến bao gồm các biến môi trường và biến shell và các hàm shell.
* unset - Lệnh xóa các biến shell và môi trường.
* export - Lệnh thiết lập các biến môi trường.
### Một số biến môi trường phổ biến nhất:
* USER - Người dùng đã đăng nhập hiện tại.
* HOME - Thư mục chính của người dùng hiện tại.
* EDITOR - Trình chỉnh sửa tệp mặc định được sử dụng. Đây là trình chỉnh sửa sẽ được sử dụng khi bạn nhập chỉnh sửa trong thiết bị đầu cuối của mình.
* SHELL - Đường dẫn của shell của người dùng hiện tại, chẳng hạn như bash hoặc zsh.
* LOGNAME - Tên của người dùng hiện tại.
* PATH - Danh sách các thư mục được tìm kiếm khi thực hiện các lệnh. Khi bạn chạy một lệnh, hệ thống sẽ tìm kiếm các thư mục đó theo thứ tự này và sử dụng tệp thực thi được tìm thấy đầu tiên.
* LANG - Cài đặt ngôn ngữ hiện tại.
### Đặt biến môi trường
* Để tạo một biến shell với tên MY_VAR và giá trị Hello, gõ lệnh: MY_VAR='Hello'
* * Sử dụng lệnh printenv để kiểm tra xem biến này có phải là biến môi trường hay không
* * Đầu ra trống cho chúng ta biết rằng biến không phải là biến môi trường.
* * Lệnh export được sử dụng để thiết lập các biến môi trường: export MY_VAR
## Biến môi trường vĩnh viễn
### Để làm cho các biến môi trường bền vững, chúng ta cần xác định các biến đó trong tệp cấu hình bash. Trong hầu hết các bản phân phối Linux khi chúng ta bắt đầu một phiên mới, các biến môi trường được đọc từ các tệp sau:
* /etc/environment - Sử dụng tệp này để thiết lập các biến môi trường trên toàn hệ thống. Các biến trong tệp này được đặt ở định dạng sau:
* * FOO=bar
* * VAR_TEST="Test Var"
* /etc/profile - Các biến được đặt trong tệp này được tải bất cứ khi nào đăng nhập bash shell được nhập. Khi khai báo các biến môi trường trong tệp này, chúng ta cần sử dụng lệnh export: export PATH=$PATH:$JAVA_HOME/bin
* Để tải các biến môi trường mới vào phiên shell hiện tại, hãy sử dụng lệnh source: source ~/.bashrc
## Xóa biến môi trường
* Để bỏ đặt biết môi trường chúng ta dùng lệnh unset như sau: unset MY_VAR hoặc MY_VAR=''