## 1. awk
* Dùng để xử lý và phân tích dữ liệu từ file hoặc dòng lệnh. Nó hỗ trợ xử lý theo cột, điều kiện logic và biểu thức.
* Cú pháp: awk 'điều kiện {hành động}' file
* Ví dụ: 
* * In cột thứ 2 của file data.txt: awk '{print $2}' data.txt
* * In dòng chứa từ 'error': awk '/error/ {print} data.txt
* * Tính tổng cột thứ 3: awk '{sum += $3} END {print sum}' data.txt
## 2. cut
* Dùng để cắt dữ liệu theo cột, ký tự hoặc delimiter (ký tự phân cách)
* Cú pháp: cut [option] file
* Tùy chọn thường dùng
* * -d: Đặt delimiter.
* * -f: Chọn cột.
* * -c: Chọn ký tự cụ thể.
* Ví dụ:
* * Cắt cột thứ 2 của file data.txt với delimiter là dấy phẩy: cut -d ',' -f 2 data.txt
* * In ký tự từ vị trí 3 đến 5 trên mỗi dòng: cut -c 3-5 file.txt
## 3. sed
* Dùng để chỉnh sửa văn bản (stream editor). Nó hỗ trợ thay thế, xóa hoặc chèn dòng mới.
* Cú pháp: sed 'command' file
* Ví dụ: 
* * Thay thế từ 'hello' bằng 'hi': sed 's/hello/hi/g' file.txt
* * Xóa dòng thứ 2: sed '2d' file.txt
* * Chèn 'hello' vào đầu mỗi dòng: sed 's/^/Hello /' file.txt
## 4. grep
* Dùng để tìm kiếm dòng có chứa chuỗi hoặc biểu thức.
* Cú pháp: grep [option] pattern file 
* Tùy chọn:
* * -i: Không phân biệt chữ hoa/thường.
* * -v: Hiển thị các dòng không khớp.
* * -c: Đếm số lượng dòng khớp.
* * -n: Hiển thị số dòng.
* Ví dụ:
* Tìm dòng chứa từ "error": grep 'error' file.txt
* Tìm dòng không chứa "warning": grep -v 'warning' file.txt
* Đếm số dòng chứa "hello": grep -c 'hello' file.txt