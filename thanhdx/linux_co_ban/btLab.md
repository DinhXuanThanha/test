## SUID
### Tìm Files có SUID
### Command: find / -perm -u=s -type f 2>/dev/null
* /: Tìm kiếm bắt đầu từ thư mục gốc (root) của hệ thống, việc này giúp quét toàn bộ files trong tất cả thư mục. Điều này giúp tăng phạm vi tìm kiếm.
* -perm: Tìm kiếm theo các quyền được chỉ định sau đây.
* -u=s: Tìm kiếm các file được sở hữu bởi người dùng root. Sử dụng -user [tên user] để tìm kiếm các files của user đó.
* -type: chỉ định loại file tìm kiếm.
* f: Chỉ định loại file cần tìm là các regular file, mà không là các thư mục hoặc các file đặc biệt. Hầu hết các file được sử dụng trực tiếp bởi người dùng là các regular file. Ví dụ: file thực thi, file văn bản, file hình ảnh... Điều này giúp tăng hiệu quả tìm kiếm.
* 2>: có nghĩa là redirect (kí hiệu là >) file channel số 2 tới nơi được chỉ định, file channel này ánh xạ tới stderr (standard error file channel), là nơi các chương trình thường ghi lỗi vào.
* /dev/null: Đây là nơi được redirect đến, nó là một pseudo-device (thiết bị giả) hay một special character device mà nó cho phép write (ghi) bất cứ thứ gì lên nó, nhưng khi yêu cầu đọc nó, nó không return bất cứ thứ gì.
  