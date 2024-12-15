# Công cụ quản lý process
## 1. ps (Process Status)
### Chức năng: Hiển thị danh sách các process đang chạy.
### Sử dụng:
* ps aux: Hiển thị thông tin tất cả các process theo dạng chi tiết.
* * a: Bao gồm tất cả các tiến trình từ mọi người dùng.
* * u: Hiển thị dưới dạng dễ đọc.
* * x: Bao gồm các tiến trình không gắn với terminal.
* ps -ef: Hiển thị thông tin các process kèm parent process (PPID).
* * e: Hiển thị tất cả các tiến trình.
* * f: Định dạng đầy đủ.
* ps -e: Hiển thị tất cả các tiến trình trên hệ thống.
* ps -f: Hiển thị chi tiết các tiến trình (bao gồm PPID, UID,...).
* ps -u \<username>: Hiển thị các tiến trình thuộc một người dùng cụ thể.
### Sắp xếp thông tin:
* ps aux --sort=-%men: Sắp xếp các tiến trình theo mức độ sử dụng RAM (cao nhất).
* ps aux --sort=-%cpu: Sắp xếp các tiến trình theo mức độ sử dụng CPU (cao nhất).
### Tìm kiếm tiến trình:
* ps aux | grep \<tên_process>: Tìm kiếm một tiến trình
* ps -C \<tên_process>: Hiển thị thông tin về tiến trình với tên cụ thể.
### Hiển thị cây tiến trình:
* ps -e --forest: Hiển thị các tiến trình trong dạng cây.
* ps -ef --forest: Tương tự với định dạng chi tiết hơn.
### Hiển thị theo thời gian:
* ps -eo pid,cmd,%cpu,%mem --sort=-%cpu: Hiển thị PID, lệnh, % CPU, % RAM và sắp xếp theo CPU sử dụng.
### Lợi ích: Hữu ích khi muốn kiểm tra trạng thái của một process cụ thể.
## 2. top
### Chức năng: Lệnh top trong Linux được sử dụng để giám sát thời gian thực các tiến trình đang chạy, mức sử dụng tài nguyên hệ thống như CPU, RAM, và swap.
### Sử dụng:
* top: Hiển thị giao diện thời gian thực của các tiến trình đang chạy.
* htop: Hiển thị giao diện đẹp hơn, dễ sử dụng.
### Các phím tương tác trong top:
### Sắp xếp:
* P: Sắp xếp theo CPU (mặc định).
* M: Sắp xếp theo mức sử dụng RAM.
* T: Sắp xếp theo thời gian hoạt động của tiến trình.
* N: Sắp xếp theo PID.
### Tìm kiếm hoặc lọc tiến trình:
* F: Tùy chỉnh các cột hiển thị.
* O hoặc o: Lọc theo trường cụ thể
* k: Dừng/kết thúc một tiến trình bằng PID (yêu cầu quyền root).
### Cài đặt hiển thị:
* 1: Hiển thị chi tiết mức sử dụng CPU cho từng nhân (core) CPU.
* Shift + 1: Chuyển đổi giữa giá trị phần trăm CPU thực tế và tổng quát.
* h: Hiển thị hướng dẫn sử dụng.
### Các tùy chọn:
* top -d <số giây>: Đặt thời gian làm mới (ví dụ: top -d 5 làm mới mỗi 5 giây).
* top -u \<username>: Hiển thị tiến trình của một người dùng cụ thể (ví dụ: top -u root).
* top -p \<PID>: Chỉ hiển thị thông tin của tiến trình với PID cụ thể.
* top -n <số>: Chỉ chạy một số lần làm mới rồi thoát (ví dụ: top -n 5).
## 3. lsof (list open files):
### Chức năngnăng: Lệnh lsof (list open files) trong Linux được sử dụng để liệt kê tất cả các file đang được mở bởi các tiến trình. Trong Linux, gần như mọi thứ đều được coi là một "file" (bao gồm file thông thường, socket, pipe, thiết bị...). Vì vậy, lsof rất hữu ích để theo dõi tài nguyên mà các tiến trình đang sử dụng.
### Sử dụng:
* lsof: Hiển thị tất cả các file đang được mở bởi mọi tiến trình.
* sudo lsof: Do lệnh này cần quyền cao hơn để xem file của các tiến trình thuộc user khác, bạn nên sử dụng sudo.
### Các tùy chọn:
* Tìm các tiến trình đang sử dụng một file cụ thể: lsof /path/to/file
* Các tiến trình đang sử dụng một cổng mạng: lsof -i:<port>
*  Tìm các tiến trình đang sử dụng một giao thức mạng: lsof -i <protocol>
*  Tìm các file được mở bởi một user cụ thể: lsof -u <username>
*  Liệt kê các tiến trình đang sử dụng thiết bị: lsof /dev/<device_name>
*  Kiểm tra các file đã bị xóa nhưng vẫn được mở: lsof | grep deleted
*  Hiển thị tất cả kết nối mạng: lsof -i
*  Kết hợp tìm kiếm với PID: lsof -p <PID>
## 4. kill
### Chức năng:Lệnh kill trong Linux được sử dụng để gửi tín hiệu đến một tiến trình nhằm điều khiển hoặc kết thúc tiến trình đó.
### Sử dụng:
* kill [tùy chọn] \<PID>
* PID: Mã định danh của tiến trình bạn muốn kiểm soát (Process ID).
* Tùy chọn: Các tín hiệu để gửi đến tiến trình (mặc định là tín hiệu SIGTERM).
### Các tín hiệu thường dùng:
* SIGTERM (15): Tín hiệu mặc định, yêu cầu tiến trình tự dừng một cách an toàn: kill \<PID>
* SIGKILL (9): Bắt buộc tiến trình dừng ngay lập tức (không an toàn, nhưng hiệu quả): kill -9 \<PID>
* SIGHUP (1): Yêu cầu tiến trình tải lại cấu hình mà không cần khởi động lại: kill -1 \<PID>
* SIGSTOP (19): Tạm dừng tiến trình (pause): kill -19 \<PID>
* SIGCONT (18): Tiếp tục tiến trình đã bị tạm dừng: \kill -18 <PID>
### Tìm PID của tiến trình:
* Sử dụng ps: ps aux | grep /<tên tiến trình>
* Sử dụng pidof: pidof /<tên tiến trình>
* Sử dụng pgrep: pgrep /<tên tiến trình>
## 5. htop
### Chức năng: Lệnh htop là một công cụ mạnh mẽ và dễ sử dụng để giám sát các tiến trình và tài nguyên hệ thống trong thời gian thực.
### Sử dụng:
* Cài đặt: sudo apt install htop
* Chạy: htop
* Thoát khỏi htop: Nhấn F10 hoặc phím q để thoát.
### Thông tin hiển thị chính trong htop
* CPU Usage: Mức sử dụng CPU theo từng nhân (core), hiển thị bằng thanh màu.
* Memory: Sử dụng RAM và swap.
* Tasks: Số lượng tiến trình đang chạy, tạm dừng, và chờ.
* Load Average: Tải hệ thống trong 1 phút, 5 phút, 15 phút.
* Uptime: Thời gian hệ thống đã chạy.
### Phím tắt trong htop
* 1. Điều hướng:
* * Phím mũi tên lên/xuống: Di chuyển qua danh sách tiến trình.
* * Phím mũi tên trái/phải: Cuộn sang trái/phải để xem thêm cột.
* 2. Lọc và tìm kiếm:
* * F3: Tìm kiếm tiến trình theo tên.
* * F4: Lọc tiến trình theo tiêu chí (ví dụ: hiển thị chỉ các tiến trình có từ khóa cụ thể).
* 3. Sắp xếp tiến trình
* * F5: Chuyển sang chế độ "Tree View" (hiển thị cây tiến trình).
* * F6: Sắp xếp theo cột (CPU, RAM, PID...).
* 4. Thao tác với tiến trình
* * F9: Gửi tín hiệu để dừng tiến trình (chọn SIGKILL hoặc tín hiệu khác).
* * F7 / F8: Giảm/tăng độ ưu tiên (nice value) của tiến trình.
* Giá trị nice nằm trong khoảng từ -20 đến 19:
* * -20: Độ ưu tiên cao nhất (CPU tập trung xử lý tiến trình này trước).
* * 19: Độ ưu tiên thấp nhất (CPU chỉ xử lý tiến trình này khi không còn gì quan trọng hơn).
Mặc định, một tiến trình sẽ khởi chạy với giá trị nice là 0.
### Tùy chỉnh giao diện
* F2: Mở menu cấu hình để tùy chỉnh hiển thị.
* Shift + H: Ẩn/hiện các tiến trình của kernel.
* Shift + I: Sắp xếp tiến trình theo người dùng.
### Các tùy chọn
* Hiển thị tiến trình của một người dùng cụ thể: htop -u <username>
* Khởi chạy ở chế độ Tree View: htop --tree
* Tùy chỉnh tốc độ làm mới: htop -d <milliseconds>
## So sánh htop và top
|   Tính năng   |   htop    |   top     |
|---------------|-----------|-----------|
|   Giao diện   |   Màu sắc, dễ sử dụng |   Đơn giản, ít thân thiện |
