* chạy lệnh kiểm tra thiết bị lưu trữ: lsblk
* Lệnh tạo phân vùng: sudo fdisk /dev/sdb
* 1. Nhấn n để tạo phân vùng mới
* 2. Chọn kiểu phân vùng (primary or logical)
* 3. Xác định kích thước phân vùng
* 4. Nhấn w để ghi
* Định dạng phân vùng: 
* 1. Sau khi tạo phân vùng, định dạng nó với hệ thống tập tin như ext4
* 2. sudo mkfs.ext4 /dev/sdb1
* Tạo thư mục gắn kết: sudo mkdir /data
* Gắn phân vùng vào thư mục: sudo mount /dev/sdb1 /data
* Kiểm tra xem phân vùng đã được gắn chưa: df -h
  
## Tạo 1 file .txt có nội dung là "Hello" trong thư mục /data
* Kiểm tra quyền truy cập vào /data: ls -ld /data
* 1. ếu hiển thị drwxr-xr-x hoặc tương tự, bạn có quyền đọc và ghi (với sudo nếu cần).
* 2. Nếu không có quyền, gán quyền ghi với lệnh: sudo chmod -R 777 /data
* Tạo file txt trong /data: echo "Hello" | sudo tee /data/hello.txt
* Xác nhận file đã được tạo và chừa nội dung "Hello": cat /data/hello.txt
## Ví dụ về phân quyền
* Kiểm tra user hiện tại: whoami (Ví dụ: thanhdx)
* Gán quyền sở hữu thư mục /data cho user: sudo chown thanhdx:thanhdx /data
* Kiểm tra quyền sau khi thực hiện: ls -ld /data
* Kết quả: drwxr-xr-x 2 thanhdx thanhdx 4096 <ngày> /data

* Thay đổi quyền cho thư mục
* Chỉ cho phép thanhdx có quyền đọc, ghi, thực thi: sudo chmod 700 /data
* Kiểm tra lại: ls -ld /data
* Kết quả: drwx------ 2 userA userA 4096 <ngày> /data
* Tạo file hello.txt trong /data:
* 1. cd /data
* 2. echo "Hello" > hello.txt
* Phân quyền cho file hello.txt
* 1. thanhdx có toàn quyền
* 2. Các user khác chỉ có quyền đọc
* chmod 644 hello.txt
* Kiểm tra lại: ls -l hello.txt
* Kết quả: -rw-r--r-- 1 userA userA 6 <ngày> hello.txt
* 1. rw- (chủ sở hữu): thanhdx có quyền đọc, ghi.
* 2. r-- (nhóm và others): chỉ có quyền đọc.
