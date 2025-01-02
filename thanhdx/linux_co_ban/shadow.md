# Chỉnh sửa password bằng file /etc/shadow
* File /etc/shadow chứa thông tin mật khẩu của các tài khoản trên hệ thống Linux, nhưng đây là file nhạy cảm. Mọi chỉnh sửa không đúng có thể gây lỗi nghiêm trọng, ví dụ như không thể đăng nhập vào hệ thống. Hãy cẩn thận và luôn sao lưu file trước khi chỉnh sửa.
## Các bước chỉnh sửa mật khẩu qua file /etc/shadow:
### Mở file /etc/shadow: sudo vi /etc/shadow
### Cấu trúc của một dòng trong /etc/shadow: username:$id$salt$hash:other_fields
* username: Tên người dùng.
* $id$salt$hash: Phần này chứa mật khẩu mã hóa.
* * $id: Phương thức mã hóa (ví dụ: \$6\$ cho SHA-512)
* * salt: Chuỗi salt ngẫu nhiên.
* * hash: Mã băm của mật khẩu.
### Tạo hash mật khẩu mới:
* Dùng lệnh sau để tạo hash cho mật khẩu mới: openssl passwd -6
* Nhập mật khẩu mới để lấy kết quả băm.
### Cập nhật hash trong /etc/shadow:
* Tìm dòng tương ứng với tài khoản cần chỉnh sửa.
* Thay thế phần $id$salt$hash bằng hash mới vừa tạo.