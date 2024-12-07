## Bài tập 1: Tạo tệp và cấp quyền cơ bản
* Tạo một tệp tên là file1.txt trong thư mục /tmp.
* Cấp quyền đọc, ghi và thực thi cho chủ sở hữu.
* Cấp quyền chỉ đọc cho nhóm.
* Không cấp quyền cho những người khác.
* Kiểm tra quyền của tệp bằng lệnh ls -l.
  
## Bài tập 2: Thay đổi chủ sở hữu và nhóm
* Tạo một tệp tên là file2.txt trong thư mục /tmp.
* Thay đổi chủ sở hữu của tệp thành một người dùng khác (ví dụ: anotheruser).
* Thay đổi nhóm của tệp thành developers.
* Kiểm tra lại quyền của tệp bằng lệnh ls -l.

## Bài tập 3: Sử dụng chmod với cách viết bằng chữ
* Tạo một tệp tên là file3.txt.
* Sử dụng cách viết bằng chữ để:
* Cấp quyền đọc và ghi cho chủ sở hữu.
* Cấp quyền đọc cho nhóm.
* Không cấp quyền cho những người khác.
* Kiểm tra quyền của tệp bằng lệnh ls -l.

## Bài tập 4: Phân quyền nâng cao (SUID, SGID, Sticky Bit)
* Tạo một tệp thực thi tên là script.sh.
* Cấp quyền SUID cho tệp này.
* Kiểm tra quyền của tệp để xác nhận SUID đã được thiết lập.
* Tạo một thư mục tên là shared_folder trong /tmp.
* Cấp quyền SGID cho thư mục này.
* Kiểm tra quyền của thư mục.
* Tạo một thư mục khác tên là sticky_folder.
* Cấp quyền Sticky Bit cho thư mục này.
* Kiểm tra quyền của thư mục.