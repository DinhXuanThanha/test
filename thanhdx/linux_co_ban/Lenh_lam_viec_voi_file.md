# Câu lệnh làm việc với tập tin
## 1. Đọc nội dung file
* cat [file]: Hiển thị nội dung file.
* less [file]: Xem nội dung file, hỗ trợ cuộn lên/xuống.
* more [file]: Xem nội dung tập tin, tương tự less nhưng ít chức năng hơn.
* tail [file]: Hiển thị phần cuối của file.
* tail -n [number][file]: Hiển thị n dòng cuối của file.
* tail -f[file]: Theo dõi nội dung của file.
* head: Hiển thị phần đầu của file.
* head -n [number][file]: Hiển thị n dòng đầu tiên của file.
## 2. Ghi nội dung vào file
* echo "text" > [file]: Ghi chuỗi vào file(ghi đè).
* echo "text" >> [file]: Ghi chuỗi vào cuối file(không ghi đè).
* cat > [file]: Tạo mới file và ghi nội dung(kết thúc bằng Ctrl + D).
* cat >> [file]: Ghi thêm vào cuối file(kết thúc bằng Ctrl + D).
## 3. Chỉnh sửa file
* nano [file]: Chỉnh sửa file với trình soạn thảo nano.
* vim [file] hoặc vi [file]: Chỉnh sửa file với vim/via.
* sed 's/old/new/g' [file]: Tìm và thay thế trong file(ghi ra stdout).
* sed -i 's/old/new/g' [file]: Thay đổi trực tiếp vào file.
* awk '{print $1}' [file]: Lấy và xử lý nội dung theo cột/dòng.
## 4. Sao chép, di chuyển, và xóa file
* cp [source] [destiantion]: Sao chép file.
* mv [source] [destination]: Di chuyển hoặc đổi tên file.
* rm [file]: Xóa file.
## 5. Kiểm tra thông tin file
* ls -l [file]: Hiển thị thông tin chi tiết về file.
* stat [file]: Xem thông tin đầy đủ của file.
* file [file]: Kiểm tra loại file.
* wc [file]: Đếm số dòng, từ, ký tự trong file.
* wc -l [file]: Đếm số dòng.
* wc -w [file]: Đếm số từ.
* wc -c [file]: Đếm số byte.
## 6. Thay đổi quyền và sở hữu.
* chmod [permissions] [file]: Thay đổi quyền file.
* chmod [owner]:[group] [file]: Thay đổi chủ sở hữu file.
## 7. So sánh và tìm kiếm trong file
* diff [file1] [file2]: So sánh hai file.
* cmp [file1] [file2]: So sánh nội dung nhị phân của hai file.
* grep "pattern" [file]: Tìm kiếm chuỗi trong file.
* grep -r "pattern" [directory]: Tìm kiếm đệ quy trong thư mục.
* find [path] -name "[pattern]": Tìm kiếm file theo tên.
## 8. Nén và giải nén file
* gzip [file]: Nén file với gzip.
* gunzip [file.gz]: Giải nén file nén gzip.
* tar -czf [archive.tar.gz] [file/folder]: Nén thành file .tar.gz.
* tar -xzf [archive.tar.gz]: Giải nén file .tar.gz.
## 9. Khác
* truncate -s [size] [file]: Cắt hoặc mở rộng kích thước file.
* dd if=[input] of=[output]: Sao chép file ở mức thấp.
* touch [file]: Tạo file mới hoặc cập nhật thời gian truy cập.
* ln -s[target] [link]: Tạo liên kết mềm(symlink).