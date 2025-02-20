# Phân quyền trong Linux
## 1. Các quyền cơ bản (Permissions):
* r (read): Quyền đọc nội dung (đối với tệp) hoặc liệt kê danh sách (đối với thư mục).
* w (write): Quyền ghi, chỉnh sửa nội dung (đối với tệp) hoặc tạo, xóa tệp con (đối với thư mục).
* x (execute): Quyền thực thi (đối với tệp) hoặc truy cập vào thư mục.
## 2. Ba nhóm đối tượng sở hữu quyền:
* u (user): Người sở hữu tệp, thư mục (owner).
* g (group): Nhóm mà tệp, thư mục thuộc về.
* o (others): Tất cả những người khác.
## 3. Biểu diễn quyền:
* Dạng kí tự: Ví dụ: -rw-r--r--
* Dấu "-" đầu tiên: Loại tệp ("-": tệp thường, "d": thư mục).
* Ba cụm ký tự tiếp theo tương ứng với quyền của u, g và o.
* Dạng số (octal): Sử dụng các giá trị số tương ứng với quyền:
* r = 4, w = 2, x = 1.
* Ví dụ: chmod 755 file.txt tương đương -rwxr-xr-x.
## 4. Thư mục được gán quyền mặc định 777:
### Thư mục /tmp trong Linux được phân quyền mặc định là 777.
* Lý do: /tmp là nơi lưu trữ tạm thời cho các tệp tin mà bất kỳ người dùng hoặc ứng dụng nào cũng có thể tạo ra.
* Tuy nhiên, thư mục /tmp sử dụng sticky bit (tùy chọn bổ sung ký hiệu "t"), khiến cho chỉ chủ sở hữu tệp/thư mục con trong /tmp mới có quyền xóa chúng, dù mọi người đều có thể ghi.
## 5. Kiểm tra phân quyền:
* Sử dụng lệnh ls -l để kiểm tra
## 6. Thay đổi quyền:
* chmod: Dùng để thay đổi quyền.
  Ví dụ: chmod 755 folder.
* chown: Dùng để thay đổi chủ sở hữu.
  Ví dụ: chown user: group file.txt/
note authorise
## 7. Thêm user vào nhóm:
* sudo usermod -aG <group_name> <username>
## 8. Xóa user khỏi nhóm:
* sudo gpasswd -d <username> <groupname>
## 9. Tạo nhóm:
* sudo groupadd tên_nhóm
## 10. Kiểm tra nhóm vừa tạo:
* getent group hoặc cat /etc/group
## 11. Xóa nhóm:
* sudo groupdel tên_nhóm
## 12. Kiểm tra thành viên nhóm:
* getent group tên_nhóm
# Tạo thư mục LinuxPractice
mkdir ~/Desktop/LinuxPractice
# Tạo cấu trúc thư mục lồng nhau
mkdir -p ~/Desktop/LinuxPractice/FolderA ~/Desktop/LinuxPractice/FolderB
# Xóa thư mục FolderA
rm -r ~/Desktop/LinuxPractice/FolderA
# Liệt kê file và thư mục (bao gồm file ẩn)
ls -a ~/Desktop/LinuxPractice
