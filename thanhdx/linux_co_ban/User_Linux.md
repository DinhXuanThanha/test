## 1. Người dùng trong Linux
* User Linux là các tài khoản được sử dụng để đăng nhập và tương tác với hệ thống.
* Mỗi người dùng được định danh bởi:
* * UID (User ID): Số định danh duy nhất cho mỗi người dùng.
* * Home Directory: Thư mục cá nhân chứa tệp và cấu hình của họ.
* * Shell: Loại giao diện dòng lệnh mà người dùng sử dụng (ví dụ: /bin/bash)
## 2. Các loại người dùng trong Linux
### Linux phân loại người dùng thành 3 loại chính, mỗi loại có quyền hạn khác nhau:
### a. Root (Người dùng quản trị hệ thống)
* Mô tả:
* * Đây là người dùng đặc biệt nhất, có quyền truy cập tuyệt đối vào toàn bộ hệ thống.
* * Root có UID = 0.
* Quyền:
* * Cài đặt/gỡ cài đặt phần mềm.
* * Thay đổi hoặc xóa mọi tệp trong hệ thống, kể cả tệp hệ thống.
* * Tạo, sửa đổi và xóa người dùng và nhóm.
* * Cấu hình hệ thống mạng và kernal.
* Lưu ý:
* * Do có quyền tối thượng, các lệnh được chạy bởi root cần được kiểm tra cẩn thận, để tránh làm hỏng hệ thống
### b. Regualar User (Người dùng thông thường)
* Mô tả:
* * Là người dùng thông thường do root tạo ra để sử dụng hệ thống.
* * Mỗi người dùng sẽ có UID từ 1000 trở lên.
* Quyền:
* * Có quyền truy cập, chỉnh sửa các tệp trong thư mục cá nhân của họ (/home/<username>).
* * Có thể chạy phần mềm nhưng không thể cài đặt hoặc thay đổi hệ thống nếu không có quyền sudo.
* * Chỉ có thể truy cập vào tệp/thư mục ngoài thư mục cá nhân nếu được cấp quyền.
### c. System User (Người dùng hệ thống)
* Mô tả: 
* * Là các tài khoản đặc biệt được tạo tự động trong quá trình cài đặt hệ điều hành hoặc dịch vụ.
* * Các tài khoản này không được dùng để đăng nhập trực tiếp.
* * UID của system user thường nằm trong khoảng 1-999.
* Quyền: 
* * Thường được sử dụng để quản lý và vận hành các dịch vụ hoặc ứng dụng.
* * Ví dụ:

    www-data: Quản lý dịch vụ web (như Apache hoặc Nginx).
    mysql: Quản lý CSDL MySQL/MariaDB.
    daemon: Điều hành các tiến trình nền.

## 3. Quyền hạn của người dùng.
### Linux sử dụng mô hình quyền truy cập Chủ sở hữu - Nhóm - Khác (Owner-Group-Others) để phân quyền cho tệp và thư mục:
   
| Quyền       | Ký hiệu     | Mô tả                     |
|-------------|-------------|---------------------------|
| Read        | r           | Cho phép đọc nội dung     |
| Write       | w           | Cho phép sửa đổi nội dung |
| Excute      | x           | Cho phép thực thi tệp     |
* Root có thể thay đổi quyền truy cập cho mọi tệp và thư mục.
* Người dùng thông thường chỉ có quyền thay đổi tệp thuộc sở hữu của mình.
## 4. Một số lệnh quản lý người dùng.
| Lệnh                      | Mô tả                                     |
|---------------------------|-------------------------------------------|
| adduser <username>        | Thêm một người dùng mới.                  |
| userdel <username>        | Xóa người dùng khỏi hệ thống.             |
| passwd <username>         | Đặt hoặc thay đổi mật khẩu của người dùng.|
| usermod -aG <group> <user>| Thêm người dùng vào một nhóm.             |
| id <username>             | Hiển thị UID, GID cà các nhóm của người dùng.|
| whoami                    | Hiển thị tên người dùng đang đăng nhập.|

