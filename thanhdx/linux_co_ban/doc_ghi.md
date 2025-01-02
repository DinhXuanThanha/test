## 1. Quyền đọc
* Cho phép người dùng xem nội dung của thư mục, nghĩa là có thể liệt kê danh sách các tệp và thư mục con bên trong thư mục đó bằng lệnh như ls.
* Lưu ý: Quyền đọc không cho phép mở tệp hoặc xem nội dung tệp bên trong thư mục nếu không có quyền đọc trên chính tệp đó.
## 2. Quyền ghi
* Cho phép người dùng thay đổi nội dung của thư mục, bao gồm
* * Tạo tệp hoặc thư mục mới.
* * Xóa tệp hoặc thư mục hiện có (nếu có quyền cần thiết).
* * Đổi tên tệp hoặc thư mục.
* * Di chuyển các tệp hoặc thư mục.
* Lưu ý: Quyền ghi không cho phép mở hoặc sửa đổi tệp bên trong thư mục nếu không có quyền ghi trên tệp đó.
## 3. Kết hợp quyền đọc và quyền ghi
* Khi một người dùng hoặc nhóm có cả quyền đọc và ghi đối với một thư mục, họ có thể:
* * Liệt kê nội dung thư mục.
* * Tạo, xóa, đổi tên, và di chuyển các tệp hoặc thư mục con bên trong.
* Thư mục có quyền đọc (r--): Chỉ có thể xem danh sách tệp/thư mục bên trong, không thể thêm, xóa, hoặc sửa đổi nội dung.
* Thư mục có quyền ghi (-w-): Có thể thêm, xóa, sửa đổi nội dung nhưng không xem được danh sách tệp/thư mục (nếu không có quyền đọc).
* Thư mục có quyền đọc và ghi (rw-): Có thể xem và thay đổi nội dung thư mục.