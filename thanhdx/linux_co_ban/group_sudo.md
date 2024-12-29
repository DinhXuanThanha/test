# Group sudo
* Group sudo trong Linux được sử dụng để quản lý các tài khoản có quyền chạy các lệnh với quyền root.
* Khi một user thuộc group sudo, có thể thực thi các lệnh với quyền quản trị bằng cách thêm tiền tố sudo trước lệnh.
## 1. Cách kiểm tra user hiện tại có thuộc group sudo không
* Sử dụng groups, nếu thấy sudo trong danh sách, user đang có quyền sudo
## 2. Cách thêm quyền sudo cho một user
* 2.1 Kiểm tra user cần thêm quyền
* * Liệt kê tất cả các user trên hệ thống: cat /etc/passwd
* 2.2 Thêm user vào group sudo: sudo usermod -aG sudo <tên_user>
* 2.3 Kiểm tra lại quyền
* * Đăng nhập bằng user vừa thêm và chạy: sudo whoami
## 3. Thêm quyền sudo cho user mà không cần vào group sudo
* Mở file sudoers: sudo visudo
* Thêm <tên_user> ALL=(ALL:ALL) ALL dưới dòng root ALL=(ALL:ALL) ALL
* Lưu và thoát
## 4. Xóa quyền sudo của user
* sudo gpasswd -d <tên_user> sudo
## 5. Kiểm tra và quản lý file sudoerssudoers
* Luôn dùng visudo để chỉnh sửa file /etc/sudoers vì nó kiểm tra lỗi cú pháp. Tránh chỉnh sửa trực tiếp bằng trình soạn thảo như nano hay vim.