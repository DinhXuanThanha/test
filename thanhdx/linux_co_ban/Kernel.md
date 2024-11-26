# 1. Kernel
## Kernel là một phần cốt lõi không thể thiếu của hệ điều hành (OS), làm nhiệm vụ quản lý tài nguyên phần cứng và cung cấp giao diện cho ứng dụng tương tác với phần cứng. Nó hoạt động như một trung tâm điều khiển, giúp điều phối và quản lý các tác vụ cơ bản của hệ thống
# 2. Chức năng của kernel:
## 2.1 Đối với hệ điều hành
### Kernel thực hiện chuyển đổi những yêu cầu đầu vào / đầu ra của phần mềm một tập lệnh dành cho CPU và GPU. Nó giống như một lớp nằm ở giữa phần mềm cùng phần cứng giúp mọi thứ vận hành trơn tru.
### - Truy cập tài nguyên máy tính: Kernel có thể truy cập các tài nguyên máy tính khác nhau. Như CPU, thiết bị I/O và các tài nguyên khác. Nó hoạt động như một cầu nối giữa người dùng và tài nguyên của hệ thống.
### - Quản lý tài nguyên: Nhiệm vụ của Kernel là chia sẻ tài nguyên giữa các process khác nhau.
### - Quản lý bộ nhớ: Mỗi process cần một số không gian bộ nhớ. Vì vậy, bộ nhớ phải được phân bổ và truy cập để hoạt động. Tất cả những tác vụ quản lý bộ nhớ này được thực hiện bởi Kernel.
### - Quản lý thiết bị: Các thiết bị ngoại vi được kết nối trong hệ thống được sử dụng bởi các process. Vì vậy, việc phân bổ các thiết bị này được quản lý bởi Kernel.
## 2.2 Đối với bảo mật và bảo vệ
### Ngoài ra, Kernel cũng có chức năng bảo vệ phần cứng. Trong trường hợp không có sự bảo vệ này của Kernet thì những chương trình có thể thực hiện tác vụ trên máy tính một cách tùy ý và lộn xộn. Từ đó sẽ làm cho máy tính và dữ liệu của bạn bị hỏng.
### Trong các máy tính hiện đại, bảo mật được thực hiện ở cấp độ phần cứng. Ví dụ: Windows sẽ không tải driver từ nguồn không đáng tin cậy và được chứng nhận bằng chữ ký. Secure Boot và Trusted Boot cũng là một minh chứng cụ thể cho ví dụ này.
### - Secure Boot: 
### Khởi động an toàn là một tiêu chuẩn bảo mật do những thành viên của ngành công nghiệp máy tính PC phát triển. Nó hỗ trợ người dùng bảo vệ hệ thống tránh khỏi những chương trình độc hại, thông qua việc không cho ứng dụng trái phép nào vận hành trong thời gian khởi động hệ thống.
### Nhờ có tính năng này mà khi máy tính của bạn khởi động chỉ sử dụng những phần mềm uy tín và được nhà sản xuất tin cậy. Theo đó, khi máy tính bắt đầu khởi động, firmware tiến hành kiểm tra chữ ký của những phần mềm khởi động như firmware driver (ROM tùy chọn) cùng hệ điều hành.
### - Trusted Boot
### Trusted Boot dùng Mô-đun nền tảng tin cậy ảo (VTPM) để thực hiện xác minh chữ ký số của Kernel Windows 10 trước khi được tải xuống. Mặt khác, nó xác nhận tất cả thành phần khác nằm trong quy trình khởi động Windows, ví dụ như: Driver khởi động, tập tin khởi động và ELAM. 
### Trong trường hợp, tập tin bị thay đổi (dù ở mức độ nào) bộ nạp khởi động sẽ ngay lập tức phát hiện vàtừ chối tải nó, thông qua việc nhận ra nó là thành phần bị lỗi. Qua đó có thể thấy nó cung cấp một chuỗi tin cậy đến mọi thành tố được sử dụng khi khởi động.
# 4. Quá trình khở động trong Linux
## 4.1 Power On
### - BIOS là một phần mềm được cài sẵn vào chip ROM nằm trên bo mạch chủ.
### - Khi nhấn nút khởi động nguồn, chương trình BIOS sẽ chạy đầu tiên. BIOS sẽ thực hiện một công việc gọi là POST nhằm kiểm tra phần cứng.
### - Khi quá trình POST kết thúc thành công, BIOS sẽ tìm kiếm và khởi chạy một hệ điều hành chứa trong ổ cứng, USB…Sau đó phần còn lại của quá trình khởi động được kiểm soát bởi hệ điều hành.
## 4.2 Master Boot Record
### - Sector đầu tiên của một thiết bị lưu trữ được gọi là MBR.
### - BIOS sẽ đọc MRB của thiết bị này để nạp vào bộ nhớ một chương trình rất nhỏ. Chương trình nhỏ này sẽ định vị và khởi động boot loader – đây là chương trình chịu trách nhiệm cho việc tìm và nạp nhân (kernel) của hệ điều hành.
### - Đến giai đoạn này, máy tính sẽ không truy cập vào bất kì phương tiện lưu trữ nào. Các thông tin về ngày tháng, thời gian và các thiết bị  ngoại vi quan trọng nhất được nạp từ CMOS.
## 4.3 Boot Loader
### - Boot loader sẽ nằm trong Master Boot Record (MBR). Khi khởi động Linux, boot loader có trách nhiệm nạp kernel và Initial RAM Disk (có chứa một số tệp quan trọng và trình điều khiển thiết bị cần thiết để khởi động hệ thống) vào bộ nhớ.
### - Boot Loader gồm 2 giai đoạn:
### + Giai đoạn thứ nhất:
### * Đổi với các hệ thống sử dụng BIOS/MBR, boot loader nằm tại sector đầu tiên của bộ nhớ hay còn gọi là Master Boot Record (MBR). Kích thước của MBR vào khoảng 512 bytes. Trong giai đoạn này boot loader kiểm tra các phân vùng để tìm ra phân vùng chứa hệ điều hành. Khi tìm thấy phân vùng khởi động, nó sẽ tìm một boot loader như là GRUB và tải nó vào RAM.
### * Đối với các hệ thống sử dụng EFI/UEFI, các firmware UEFI sẽ đọc dữ liệu Boot Manager để tìm các ứng dụng UEFI. Firmware sẽ chạy ứng dụng UEFI
### + Giai đoạn thứ hai:
### Boot loader nằm trong thư mục /boot. Một màn hình hiển thị cho phép chúng ta chọn OS để khởi động. Sau đó boot loader sẽ nạp kernel của hệ điều hành đó vào bộ nhớ RAM và chuyển quyền điều khiển máy tính cho kernel này.
## 4.4 Linux kernel được nạp và khởi chạy
### Boot loader sẽ nạp hạt nhân và các file system RAM vào bộ nhớ hệ thống để kernel có thể sử dụng trực tiếp. Khi hạt nhận được nạp vào bộ nhớ RAM, nó ngay lập tức khởi tạo và cấu hình bộ nhớ máy tính hoặc tất cả các phần cứng được gắn vào.
## 4.5 Inital RAM Disk
### - Các INITRD cung cấp một giải pháp: một tập các chương trình nhỏ sẽ được thực thi khi kernel vừa mới được khởi chạy. Các chương trình nhỏ này sẽ dò quét phần cứng của hệ thống và xác định xem kernel cần được hỗ trợ thêm những gì để có thể quản lý được các phần cứng đó. Chương trình INITRD có thể nạp thêm vào kernel các module bổ trợ. Khi chương trình INITRD kết thúc thì quá trình khởi động Linux sẽ tiếp diễn.
## 4.6 Các run level và service
### - init là tiến trình đầu tiên chạy trong hệ thống Linux: ID của tiến trình này là 1.
### - File cấu hình runlevel /etc/inittab
### + Runlevel 0: tắt hệ thống
### + Runlevel 1: chế độ đơn người sử dụng
### + Runlevel 2: chế độ multi user
### + Runlevel 3: chế độ đa người dùng không có giao diện đồ họa
### + Runlevel 4: không sử dụng
### + Runlevel 5: chế độ đa người dùng có giao diện đồ họa
### + Runlevel 6: reboot hệ thống
## 4.7 Đăng nhập vào giao diện command line
### Gấn cuối của quá trình khởi động, init sẽ bắt đầu một chế độ đăng nhập text mode. Nhập tên người dùng và mật khẩu để đăng nhập, và xuất hiện dấu nhắc lệnh shell.
## 4.8 Đăng nhập với giao diện đồ họa
### Subsystem cuối cùng được init khởi động lên là X Window. Cung cấp giao diện đồ họa cho người dùng trên Linux.
# 5 INIT Levels
## 5.1 INIT System
### System V
### - System V (đọc là System Five) được phát triển bởi AT&T và được ra mắt lần đầu tiên vào năm 1983, do khá cổ và còn nhiều điểm không hoàn thiện nên SysV đang dần được thay thế bởi các Init System khác
### - Một số Linux OS sử dụng System V:
### + Debian 6 và trước nữa
### + Ubuntu 9.04 và trước đó nữa
### + CentOS 5 trở về trước
### Upstart
### - Upstart là một init system được phát triển bởi những người đã tạo nên Ubuntu nhằm thay thế cho SysV trên các distro Ubuntu. Upstart có nhiệm vụ khởi chạy các tiến trình và tác vụ khác nhau, kiểm tra các process đang hoạt động và stop những process này khi shutdown hệ thống.
### - Một số distro hỗ trợ Upstart (đa phần là Ubuntu vì Upstart vốn được phát triển cho riêng Ubuntu)
### + Từ Ubuntu 9.10 tới Ubuntu 14.04, 14.10
### + CentOS 6
### Systemd
### - Systemd là init system tiêu chuẩn cho các distro được release gần đây như CentOS 7, Ubuntu 16, 18…
### - Systemd là một init system quản lý các tiến trình trên Linux, chữ ‘d’ ở cuối có nghĩa là trình daemon. Tương tự như init, systemd là process của tất cả các process khác trong một hệ thống Linux, systemd là process đầu tiên được start lên khi boot và có PID là 1.
## 5.2 Runlevel
### - Runlevel là biểu thị một trạng thái trong Linux, mỗi runlevel sẽ biểu thị cho một trạng thái riêng của Linux server như shutdown, single-user mode, restart mode, mỗi một con số sẽ biểu thị một runlevel riêng
### - Các số runlevel này chạy từ 0 tới 6 và có ý nghĩa như sau:
### + Runlevel 0: Shutdown hệ thống
### + Runlevel 1: Chế độ rescue mode, 1 user
### + Runlevels 2, 3, 4: Chế độ nhiều user, có kết nối mạng, giao diện CLI
### + Runlevel 5: Chế độ nhiều user, có kết nối mạng, giao diện đồ họa GUI.
### + Runlevel 6: Reboot hệ thống
### https://blog.vinahost.vn/init-system-va-run-level/