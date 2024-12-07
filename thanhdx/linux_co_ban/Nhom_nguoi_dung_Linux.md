## 1 Nhóm người dùng 
* Nhóm người dùng là tập hợp các tài khoản người dùng được nhóm lại với nhau để quản lý quyền truy cập vào tệp, thư mục và tài nguyên hệ thống.
* Mỗi nhóm có 1 Group ID (GID) duy nhất, tương tự như mỗi người dùng có một User ID (UID).
## 2. Lợi ích của nhóm người dùng
* Quản lý quyền dễ dàng hơn: Có thể chỉ định quyền truy cập cho nhóm thay vì từng người dùng.
* Bảo mật: Giới hạn quyền truy cập tài nguyên theo nhóm, giúp tăng cường bảo mật.
* Tính linh hoạt: Một người dùng có thể thuộc nhiều nhóm, cho phép họ có quyền trên nhiều tài nguyên khác nhau.
## 3. Phân loại nhóm
* Nhóm chính (Primary Group):
* * Mỗi người dùng đều thuộc một nhóm chính.
* * Đây là nhóm mặc định được gắn với người dùng khi họ tạo tệp hoặc thực thi lệnh
* Nhóm phụ (Secondary Group):
* * Người dùng có thể được thêm vào nhiều nhóm phụ để kế thừa quyền truy cập bổ sung.
## 4. Quản lý nhóm:
### Tệp cấu hình nhóm:
### - Danh sách nhóm dược lưu trong tệp /etc/group.
### - Mỗi dòng trong tệp biểu thị một nhóm bao gồm:
* group_name: Tên nhóm.
* x: Trường mật khẩu.
* GID: Group ID.
* user1, user2, ...: Các người dùng thuộc nhóm.
## 5. Các lệnh quản lý nhóm
* groupadd <group_name>: Tạo nhóm
* groupdel <group_name>: Xóa nhóm
* groupmod: Thay đổi thông tin nhóm
* usermod -aG <group_name> <user>: Thêm người dùng vào nhóm phụ
* groups <user>: Xem các nhóm mà một người dùng thuộc về
* id <user>: Hiển thị GID, UID và các nhóm của người dùng
* gpasswd -a <user> <group>: Thêm người dùng vào nhóm
* gpasswd -d <user> <group>: Xóa người dùng khỏi nhóm
## 6. Quản lý quyền truy cập
### Linux sử dụng cơ chế quyền tệp (file permission) để xác định người dùng hoặc nhóm nào có thể đọc (r) và ghi (w) tệp hoặc thư mục.
* -rwxrwxr-- 1 user group ...
* * user: Quyền của chủ sở hữu tệp.
* * group: Quyền của nhóm sở hữu tệp.
* * others: Quyền của tất cả người dùng khác.
* Sử dụng lệnh chown vả chgrp để thay đổ quyền và sở hữu nhóm:
* * chown user: group <file>: Đổi chủ sở hữu và nhóm của tệp.
* * chgrp <group> <file>: Đổi nhóm sở hữu tệp.
