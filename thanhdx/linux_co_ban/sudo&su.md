# sudo và su
## sudo 
* Chạy một lệnh cụ thể với quyền quản trị mà không cần chuyển đổi người dùng.
* Cách hoạt động:
* * Người dùng hiện tại tạm thời được nâng quyền (dựa trên thiết lập trong file /etc/sudoers).
* * Chỉ yêu cầu mật khẩu của người dùng hiện tại, không phải mật khẩu root.
### Ưu điểm:
* Tăng bảo mật vì không cần đăng nhập root trực tiếp.
* Hạn chế quyền chỉ cho những lệnh cụ thể.
## su
* Chuyển đổi hoàn toàn sang người dùng khác, thường là root.
* Cách hoạt động
* * Khi chạy su (không tham số), bạn sẽ chuyển sang tài khoản root và cần nhập mật khẩu root.
* * Bạn cũng có thể dùng su <username> để chuyển sang người dùng khác.
### Ưu điểm:
* Dùng trong môi trường cần thao tác lâu dài dưới quyền root.