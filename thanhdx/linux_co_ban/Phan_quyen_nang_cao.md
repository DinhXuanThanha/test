# Phân quyền nâng cao
## Ngoài các quyền cơ bản (read, write, execute), Linux cung cấp các quyền nâng cao để quản lý chi tiết hơn cách người dùng và nhóm tương tác với tệp và thư mục.
## 1. SUID (Set User ID)
* Mô tả:
* * SUID hay Set user ID, được sử dụng trên các file thực thi (executable files) để cho phép việc thực thi được thực hiện dưới owner của file thay vì thực hiện như user đang loggin trong hệ thống. .
SUID cũng có thể được sử dụng để thay đổi ownership của files được tạo hoặc di chuyển nó đến một thư mục mà owner của nó sẽ là owner của thư mục chuyển đến thay vì là owner nó được tạo ra.
* * Chỉ áp dụng cho tệp thực thi, không áp dụng cho thư mục.
* Ký hiệu:
* * Ký hiệu SUID là chữ s thay thế quyền x trong phần user: -rwsr-xr-x  1 root root 12345 Dec  2 10:00 /usr/bin/passwd
* * Nếu quyền thực thi không có, ký hiệu sẽ là S (không khả dụng).
* Ứng dụng:
* * Ví dụ phổ biến là lệnh passwd. Khi chạy lệnh này, người dùng tạm thời có quyền root để thay đổi mật khẩu: ls -l /usr/bin/passwd
-rwsr-xr-x  1 root root 54256 Aug 15 12:34 /usr/bin/passwd
* * Cách thiết lập: chmod u+s filename
* * Xóa SUID: chmod u-s filename
## 2. SGID (Set Group ID):
### Mô tả: 
* Khi SGID được gắn vào:
* * Tệp thực thi: Người dùng chạy tệp sẽ kế thừa quyền của nhóm sở hữu tệp thay vì nhóm của chính họ.
* * Thư mục: Các tệp/thư mục mới tạo trong thư mục SGID sẽ kế thừa nhóm sở hữu của thư mục cha, thay vì nhóm mặc định của người tạo.
* Ký hiệu:
* * Ký hiệu SGID là s thay thế quyền x trong phần group: 
-rwxr-sr-x  1 user group 12345 Dec  2 10:00 file
drwxrwsr-x  2 user group 4096  Dec  2 10:00 directory
* * Nếu quyền thực thi không có, ký hiệu sẽ là S.
* Ứng dụng:
* * Đảm bảo rằng tất cả tệp/thư mục được tạo trong thư mục chia sẻ đều thuộc cùng một nhóm.
* * Ví dụ: Thư mục /var/www cho web server.
* Cách thiết lập: chmod g+s filename_or_directory
* Xóa SGID: chmod g-s filename_or_directory
## 3. Sticky Bit
* Mô tả: 
* * Sticky Bit được sử dụng chủ yếu trên thư mục. Nó đảm bảo rằng chỉ có chủ sở hữu tệp hoặc root mới có thể xóa hoặc sửa tệp trong thư mục đó, ngay cả khi người khác có quyền ghi vào thư mục.
* Ký hiệu:
* * Sticky Bit được biểu thị bằng chữ t trong phần others: drwxrwxrwt  2 root root 4096  Dec  2 10:00 /tmp
* Ứng dụng: 
* * Thư mục /tmp là ví dụ phổ biến, nơi mọi người dùng có thể tạo tệp nhưng chỉ chủ sở hữu tệp hoặc root có thể xóa tệp đó.
* Cách thiế lập: chmod +t directory
* Xóa Sticky Bit: chmod -t directory
## 4. Chỉ số umask
* Mô tả: 
* * umask (User Mask) là giá trị mặc định kiểm soát quyền của tệp/thư mục mới được tạo.
* * Giá trị umask xác định quyền bị loại bỏ từ quyền mặc định.
* Quyền mặc định:
* * Tệp: Quyền mặc định là 666 (đọc và ghi cho tất cả).
* * Thư mục: Quyền mặc định là 777 (đọc, ghi, thực thi cho tất cả).
* Cách tính quyền: Quyền cuối = Quyền mặc định - umask
### Ví dụ: Với umask 022: 
Tệp 666 - 022 = 644 (rw-r--r--).
Thư mục: 777 - 022 = 755 (rwxr-xr-x)
* Kiểm tra umask: umask
* Thay đổi umask: 
* * Tạm thời: umask 027
* * Vĩnh viễn: 'umask 027' >> ~/,bashrc
### Ý nghĩa một số giá trị umask:
|   umask     |   Quyền tệp    |    Quyền thư mục   |   Mô tả   |
|-------------|----------------|--------------------|----------------|
|   022       |     644        |    755             |   Chỉ chủ sở hữu có quyền ghi|
|   027       |     640        |    750             |   Hạn chế quyền nhóm và người khác|               |
|   077       |     600        |    700             |   Chỉ chủ sở hữu có quyền|

## Tóm tắt các quyền nâng cao
|   Loại    |   Ký hiệu     |   Áp dụng cho     |   Ý nghĩa     |
|-----------|---------------|-------------------|---------------|
|   SUID    |   s/S         |   Tệp thực thi    |   Người chạy tệp có quyền của chủ sở hữu tệp.|
|   SGID    |   s/S         |   Tệp/thư mục     |   Kế thừa quyền nhóm hoặc nhóm sở hữu của thư mục cha.|
|   Sticky  |   t/T         |   Thư mục         |   Chỉ chủ sở hữu hoặc root được phép xóa tệp.|