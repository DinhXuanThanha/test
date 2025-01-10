# Hard links & Soft links
## 1. Hard links
* Hard links là các liên kết cấp thấp mà hệ thống sử dụng để tạo các thành phần của chính hệ thống file. Hard links sẽ tạo một liên kết trong cùng một hệ thống tập tin với 2 inode entry tương ứng trỏ đến cùng một nội dung vật lý.
* Tất cả các hệ thống tệp tin dựa trên thư mục phải có ít nhất một hard link (link counts từ 1 trở lên) cung cấp tên gốc cho mỗi tệp tin.
* Lệnh tạo hark link: ln [file nguồn] [file đích]
* Ví dụ: ln test.txt hardlink.txt, hai file test.txt và hardlink.txt có số inode giống nhau. Xóa file test.txt thì nội dung của file hardlink.txt vẫn còn.
* Nội dung trong hardlink.txt vẫn còn vì khi xóa file test.txt hệ thống chỉ xóa đi số link count trong inode của file đi 1.
## 2. Symbolic links
* Symbolic links là một file đặc biệt trỏ đến một file hoặc thư mục khác - được gọi là target. Khi tạo, một symbolic links có thể được sử dụng thay cho target file. Nó có thể có một tên độc nhất, và được đặt trong bất kỳ thư mục nào. Nhiều symbolic links thậm chí có thể được tạo cho cùng một target file, cho phép truy cập target bằng nhiều tên khác nhau.
* Symbolic link không chứa bản sao dữ liệu của target file. Nó tương tự như một shortcut trong Microsoft Windows: nếu xóa một symbolic link, target sẽ không bị ảnh hưởng. Vì chỉ đơn thuần là một shortcut, symbolic link không dùng đến inode entry, Nó tạo ra một inode mới và nội dung của inode này trỏ đến tên tập tin gốc.
* Ngoài ra, nếu target của một symbolic link bị xóa, di chuyển hoặc đổi tên, symbolic link không được cập nhật. Khi điều này xảy ra, liên kế tượng trưng được gọi là "broken" hoặc "orphaned" sẽ không còn hoạt động như một liên kết.
* Lệnh tạo liên kết tượng trưng: ln -s [file nguồn] [file đích].
* Ví dụ: ln -s test.txt softlink.txt, hai file test.txt và softlink.txt có số inode khác nhau. Xóa file test.txt thì nội dung của file soft.txt sẽ không còn.
* Nội dung của softlink.txt không hiển thị được vì sortlink.txt trỏ đến một tập tin khác, mà tập tin này không tồn tại.
## 3. Inode
* Trong Linux, dữ liệu của các file được chia thành các block. Có nhiều các tổ chức để liên kết các khối dữ liệu trong một file với nhau, một trong các cách đó là dùng chỉ mục. 
* Trong một inode có các metadata sau:
* * Dung lượng file tính bằng bytes.
* * Device ID: id của thiết bị lưu file.
* * User ID: id của chủ sở hữu.
* * Group ID: id nhóm của chủ sở hữu file.
* * File mode: gồm các kiểu file và cách thức truy cập file.
* * Timestamps: các mốc thời gian khi: bản thân inode bị thay đổi (ctime, inode change time), nội dung file thay đổi (mtime, modification time) và lần truy cập mới nhất (atime, access time).
* * Link count: số lượng hard links trỏ đến inode. Các con trỏ chỉ đến các blocks trên ổ cứng dùng lưu nội dung file. Các con trỏ cho biết file nằm ở đâu để đọc nội dung.
* Inode xác định file và thuộc tính của nó. Mỗi inode được xác định bởi 1 con số duy nhất trong hệ thống tệp tin.
### Inode (Index Node) là một cấu trúc dữ liệu trong các hệ thống tệp (file systems) của Unix/Linux. Nó lưu trữ thông tin về một tệp hoặc thư mục trên đĩa cứng, nhưng không lưu dữ liệu thực tế của tệp.