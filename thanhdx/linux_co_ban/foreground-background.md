## 1. Foreground 
### Đặc điểm:
* Tiến trình đang chạy trực tiếp trên terminal.
* Người dùng có thể tương tác trực tiếp với tiến trình.
* Terminal bị khóa (không thể thực hiện lệnh khác cho đến khi tiến trình hoàn thành).
* Ví dụ: Khi chạy lệnh ping google.com, nó sẽ chạy liên tục trên terminal cho đến khi bạn dừng nó (bằng cách nhấn Ctrl+C).
## 2. Background
### Đặc điểm:
* Tiến trình chạy trong nền mà không chiếm dụng terminal.
* Người dùng có thể tiếp tục thực hiện các lệnh khác trên terminal.
* Không tương tác trực tiếp với tiến trình từ terminal.
* Ví dụ: Thêm ký tự & sau lệnh để chạy tiến trình ở nền: sleep 60 &
* Tiến trình sẽ chạy trong nền và terminal sẽ trả lại quyền điều khiển ngay lập tức.
## 3. Chuyển đổi giữa Foreground và Background:
### 3.1 Chuyển tiến trình từ foreground sang background:
* Nhấn Ctrl+Z để tạm dừng tiến trình.
* Chạy lệnh bg để tiếp tục tiến trình trong nền.
### 3.2 Chuyển tiến trình từ background sang foreground:
* Sử dụng lệnh fg kèm số job (nếu có nhiều tiến trình): fg %1
* * % biểu thị rằng bạn đang đề cập đến một job.
* * 1 là ID của job mà bạn muốn thao tác.
## Kiểm tra tiến trình nền: jobsjobs
## Ví dụ:
* $ sleep 60 &
* [1] 12345
* * [1] là job ID (để dùng với fg hoặc bg).
* * 12345 là process ID (PID) (dùng với các lệnh như kill).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              