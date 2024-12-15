# Process
## Trong Linux process (quá trình) là một chương trình đang được thực thi. Mỗi process có một Process ID (PID) và các thuộc tính liên quan như trạng thái, quyền sở hữu, độ ưu tiên.
## 1. Các loại process trong Linux
### Foreground Process (Quá trình chạy nền trước):
* Đây là các process được người dùng tương tác trực tiếp qua terminal.
* Khi chạy một lệnh trong terminal, nó trở thành foreground process.
* Ví dụ: Khi bạn chạy nano, vim, cat,...
### Background Process (Quá trình chạy nền sau):
* Các process chạy trong nền mà không yêu cầu tương tác trực tiếp từ người dùng.
* Thường được dùng để thực hiện các tác vụ dài hoặc không cần giám sát liên tục.
* Ví dụ: ./script.sh & (dấu & đưa process chạy nền).
### Daemon Process (Quá trình daemon):
* Đây là các process chạy trong nền phục vụ hệ thống, không liên kết với terminal.
* Ví dụ: sshd (quản lý SSH), httpd (quản lý web server).
### Zombie Process (Quá trình zombie):
* Process đã kết thúc nhưng chưa được cha của nó thu dọn (clean up).
* Chúng không tiêu tốn tài nguyên hệ thống (chỉ chiếm PID).
### Orphan Process (Quá trình mồ côi):
* Khi một parent process kết thúc trước, các child process trở thành orphan và được hệ thống (init/systemd) nhận làm cha.
## 2. Các lệnh cơ bản quản lý process:
### ps (Process Status)
* Hiển thị danh sách các process đang chạy.
* ps: Hiển thị process thuộc terminal hiện tại.
* ps aux: Hiển thị tất cả các process.
* ps -ef: Hiển thị process theo định dạng khác.
### top và htop
* top: Hiển thị danh sách process đang chạy kèm thông tin CPU, RAM.
* htop: Giao diện tương tác trực quan hơn (nếu được cài đặt).
### kill
* Dùng để gửi tín hiệu để dừng hoặc quản lý process.
* kill <PID>: Gửi tín hiệu kết thúc (SIGTERM) cho process.
* kill -9 <PID>: Gửi tín hiệu mạnh (SIGKILL) để buộc kết thúc process.
### sleep
* Dừng thực thi một chương trình trong một khoảng thời gian.
* sleep 5: Dừng 5s.
* sleep 1m: Dừng 1p.
### bg và fg
* uản lý các process đang chạy ở foreground hoặc background.
* bg: Đưa một process từ trạng thái dừng (stopped) chạy lại ở chế độ nền.
* fg: Đưa process từ nền về foreground.
* bg %<job_id>: Tiếp tục một job ở nền.
* fg %<job_id>: Đưa job ra foreground.
### jobs
* Hiển thị danh sách các job đang chạy hoặc bị dừng trong shell.
* jobs: Liệt kê các job với trạng thái.
### nice và renice
* nice: Thiết lập mức độ ưu tiên khi bắt đầu một process (mức từ -20 đến 19).
* nice -n 10 ./script.sh: Chạy script với độ ưu tiên thấp.
* renice: Thay đổi độ ưu tiên của một process đang chạy.
* renice -n -5 <PID>: Thay đổi ưu tiên của process PID
### kill
* Gửi tín hiệu dừng đến process dựa trên tên thay vì PID.
* pkill -9 firefox: Buộc tắt tất cả process tên `firefox`
## nohup
* Chạy một process ngay cả khi đóng terminal.
* nohup ./script.sh &
## 3. Quản lý process
* Xem thông tin process: ps aux | grep <tên_process>
* Dừng process: kill <PID>
* Chạy process nền: ./app.sh &