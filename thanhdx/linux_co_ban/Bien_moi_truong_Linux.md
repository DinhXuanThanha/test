## 1. Biến môi trườngtrường:
* Biến môi trường là các giá trị được lưu trữ trong hệ điều hành để cấu hình môi trường chạy của ứng dụng hoặc dịch vụ. Chúng cung cấp thông tin như thư mục hệ thống, thông số cấu hình ứng dụng, hoặc trạng thái môi trường.
## 2. Các biến môi trường:
* env: Lệnh cho phép bạn chạy chương trình khác trong môi trường tùy chỉnh mà không cần sửa đổi chương trình hiện tại. Khi được sử dụng mà không có đối số, nó sẽ in ra danh sách các biến môi trường hiện tại.
* printenv: Lệnh in ra tất cả hoặc các biến môi trường được chỉ định.
* set: Lệnh đặt hoặc bỏ thiết lập các biến shell. Khi được sử dụng mà không có đối số, nó sẽ in ra danh sách tất cả các biến bao gồm các biến môi trường và biến shell và các hàm shell.
* unset: Lệnh xóa các biến shell và môi trường.
* export: Lệnh thiết lập các biến môi trường.
### 2.1 Một số biến môi trường phổ biến:
* USER: Người dùng đăng nhập hiện tại.
* HOME: Thư mục chính của người dùng hiện tại.
* EDITOR: Trình chỉnh sửa tệp mặc định được sử dụng. Đây là trình chỉnh sửa sẽ được sử dụng khi bạn nhập chỉnh sửa trong thiết bị đầu cuối của mình.
* SHEEL: Đường dẫn của shell người dùng hiện tại.
* LOGNAME: Tên của người dùng hiện tại
* PATH: Danh sách các thư mục được tìm kiếm khi thực hiện các lệnh. Khi bạn chạy một lệnh, hệ thống sẽ tìm kiếm các thư mục đó theo thứ tự này và sử dụng tệp thực thi được tìm thấy đầu tiên.
* LANG: Cài đặt ngôn ngữ hiện tại.
* TERM: Mô phỏng thiết bị đầu cuối hiện tại.
* MAIL: Vị trí nơi lưu trữ của người dùng hiện tại.
## 3. Đặt biến môi trường
* Tạo một shell với tên MY_VAR: MY_VAR='Hello'
* Hiển thị giá trị của biến môi trưởng: echo $MY_VAR
* Dùng printenv để kiểm tra xem biến này có phải biến môi trường không: printenv MY_VAR => Đầu ra trống cho biết không phải là biến môi trường.
* Dùng lệnh export để thiết lập biến môi trường: export MY_VAR
* Kiểm tra lại bằng printenv MY_VAR
* * Có thể đặt biến môi trường bằng một dòng: export NAME="value"
## 4. Biến môi trường cố định
* /etc/environment: Sử dụng tệp này để thiết lập các biến môi trường trên toàn hệ thống. Các biến trong tệp này được đặt ở định dạng:
* * FOO=bar
* * VAR_TEST="Test Var"
* /etc/profile: Các biến được đặt trong tệp này được tải bất cứ khi nào đăng nhập bash shell được nhập. Khi khai báo các biến môi trường trong tệp này cần sử dụng export.
* * export JAVA_HOME="/path/to/java/home"
* * export PATH=$PATH:$JAVA_HOME/bin
* Các tệp cấu hình cụ thể shell cho mỗi người dùng: export PATH="$HOME/bin:$PATH"
## 5. Xóa biến môi trường:
* Bỏ đặt biến môi trường dùng lệnh unset: unset MY_VAR hoặc MY_VAR=''