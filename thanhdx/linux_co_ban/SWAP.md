# SWAP (RAM ảo) trong Linux
## 1. SWAP là gì?
* SWAP là một không gian trên ổ cứng hoặc SSD được sử dụng như bộ nhớ ảo, hỗ trợ cho RAM khi hệ thống hết dung lượng bộ nhớ vật lý.
* Dữ liệu không hoạt động hoặc ít được truy cập sẽ được chuyển từ RAM sang SWAP để giải phóng RAM cho các tác vụ đang cần sử dụng.
## 2. Cách hoạt động của SWAP
* Khi hệ thống cần thêm bộ nhớ và RAM không đủ, nhân Linux sẽ chuyển dữ liệu ít dùng từ RAM vào phân vùng hoặc file SWAP.
* Ngược lại, nếu dữ liệu trong SWAP được yêu cầu, nó sẽ được nạp lại vào RAM.
## 3. Các loại SWAP
* Phân vùng SWAP: Một phân vùng được tạo riêng trên ổ cứng chỉ dành cho SWAP.
* File SWAP: Một file trên hệ thống được cấu hình để hoạt động như SWAP (thường dùng trên các hệ thống không có phân vùng SWAP).
## 4. SWAP có thực sự hữu ích?
### Ưu điểm:
* 1. Hỗ trợ khi RAM không đủ: SWAP rất hữu ích trên hệ thống có dung lượng RAM nhỏ, cho phép hệ điều hành xử lý nhiều ứng dụng hơn.
* 2. Ổn định hệ thống: Khi RAM bị đầy, SWAP giúp tránh việc hệ thống bị treo hoặc lỗi.
* 3. Hỗ trợ hibernate: Khi hệ thống ở chế độ ngủ đông (hibernate), dữ liệu RAM được lưu trữ vào SWAP.
### Nhược điểm:
* 1. Chậm hơn RAM: Ổ cứng hoặc SSD chậm hơn RAM rất nhiều, nên việc sử dụng SWAP sẽ làm giảm hiệu năng nếu được sử dụng quá mức.
* 2. Giảm tuổi thọ SSD: SWAP thường xuyên ghi và đọc dữ liệu, điều này có thể làm giảm tuổi thọ của SSD.
## 5. Khi nào nên sử dụng SWAP?
* Hệ thống có RAM thấp (ví dụ: < 4GB) thường cần SWAP để tránh hết bộ nhớ.
* Ứng dụng tiêu tốn nhiều bộ nhớ (như phân tích dữ liệu lớn, máy ảo, hoặc Docker) cần SWAP để tránh lỗi.
* Hệ thống dùng SSD: Nên cấu hình kích thước SWAP nhỏ và sử dụng với tần suất thấp, hoặc ưu tiên nâng cấp RAM.
## 6. Quy tắc chọn kích thước SWAP
* Hệ thống có RAM < 4GB: SWAP nên gấp đôi RAM.
* RAM từ 4GB - 8GB: SWAP nên bằng dung lượng RAM.
* RAM > 8GB: SWAP có thể là 1/2 RAM hoặc ít hơn, tuỳ thuộc vào nhu cầu.
## 7. Kiểm tra và quản lý SWAP.
* Kiểm tra SWAP: swapon --show, free -h
* Tạo file SWAP: 
* * sudo fallocate -l 1G /swapfile
* * sudo chmod 600 /swapfile
* * sudo mkswap /swapfile
* * sudo swapon /swapfile