# 1. Cấu trúc của Kernel
## Kernel là phần lõi của hệ điều hành, chịu trách nhiệm quản lý tài nguyên phần cứng và giao tiếp giữa phần cứng và phần mềm.
## 1.1 Các loại kernel
### a. Monolithic Kernel: Kernel lớn chứa toàn bộ các chức năng hệ điều hành như quản lý bộ nhớ, quản lý tiến trình, quản lý file, và driver thiết bị.
### - Ưu điểm: Hiệu năng cao vì các thành phần giao tiếp trực tiếp.
### - Nhược điểm: Khó bảo trì và mở rộng.
### b. Microkernel: Chỉ chứa các chức năng cơ bản như quản lý bộ nhớ, quản lý tiến trình, và giao tiếp IPC. Các dịch vụ khác (như driver) hoạt động bên ngoài kernel trong không gian người dùng.
### - Ưu điểm: Dễ bảo trì, ổn định hơn.
### - Nhược điểm: Hiệu năng thấp hơn do phải giao tiếp nhiều giữa kernel và user space.
### c. Hybrid Kernel: Kết hợp ưu điểm của monolithic và microkernel. Ví dụ: Windows NT.
### d. Exokernel: Chỉ cung cấp các chức năng tối thiểu để phần mềm kiểm soát phần cứng.
## 1.2 Các thành phần chính của Kernel
### - Quản lý bộ nhớ (Memory Management): Theo dõi trạng thái bộ nhớ, phân bổ và giải phóng bộ nhớ.
### - Quản lý tiến trình (Process Management): Quản lý các tiến trình, cấp phát tài nguyên và xử lý ngữ cảnh (context switching).
### - Quản lý hệ thống file (File System Management): Cung cấp giao diện truy cập và quản lý dữ liệu trên ổ đĩa.
### - Driver thiết bị (Device Drivers): Là cầu nối giữa kernel và các thiết bị phần cứng.
### - Giao tiếp IPC (Inter-Process Communication): Giao tiếp giữa các tiến trình.
### - Bảo mật (Security): Cung cấp các cơ chế bảo vệ hệ thống và dữ liệu.
# 2. Quá trình khởi động của hệ điều hành
## Quá trình khởi động (boot process) bắt đầu khi máy tính được bật nguồn và kết thúc khi hệ điều hành sẵn sàng hoạt động.
## 2.1 Các bước trong quá trình khởi động
### a. Power-On Self-Test (POST):
### - Hệ thống kiểm tra phần cứng (RAM, CPU, thiết bị lưu trữ).
### - Thực hiện bởi firmware (BIOS hoặc UEFI).
### b. Tìm bootloader:
### - Sau khi POST hoàn tất, BIOS/UEFI tìm chương trình khởi động (bootloader) từ thiết bị khởi động chính (ổ cứng, USB...).
### - Bootloader phổ biến:
### + GRUB (Linux)
### + Windows Boot Manager (Windows)
### c. Tải bootloader:
### - Bootloader được tải vào RAM và thực thi. Bootloader sẽ tiếp tục tải kernel của hệ điều hành.
### d. Tải kernel:
### - Kernel được load từ đĩa cứng vào bộ nhớ. Trong Linux, quá trình này thường đi kèm với initramfs (hệ thống file tạm thời chứa driver thiết bị cần thiết).
### e. Khởi tạo kernel:
### - Kernel khởi chạy, kiểm tra phần cứng và nạp driver thiết bị.
### - Kernel thiết lập các thành phần cơ bản như quản lý bộ nhớ và tiến trình.
### f. Chạy trình quản lý khởi động (Init System):
### - Kernel sẽ khởi chạy một tiến trình hệ thống đầu tiên (Linux: init, systemd, hoặc upstart; Windows: wininit.exe).
### - Trình quản lý khởi động sẽ khởi chạy các dịch vụ và tiến trình nền (daemons).
### g. Giao diện người dùng (UI/CLI):
### - Sau khi tất cả dịch vụ đã được khởi chạy, giao diện người dùng (Desktop Environment hoặc Command Line Interface) sẽ sẵn sàng.
## 2.2 Chi tiết quá trình trên Linux
### - Bootloader: GRUB tải kernel và initramfs.
### - Kernel Init: Kernel thực hiện:
### + Mount initramfs.
### + Chạy tiến trình đầu tiên: /sbin/init hoặc systemd.
### - Systemd:
### + Systemd đọc các file cấu hình để khởi chạy các dịch vụ.
### + Thiết lập môi trường người dùng.