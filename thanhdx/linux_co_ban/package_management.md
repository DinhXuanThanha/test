# 1. Debian Package Manager (dpkg)
## Mô tả:
* Đây là công cụ quản lý gói cấp thấp trêm Ubuntu và các hệ điều hành dựa trên Debian.
* dpkg hoạt động trực tiếp với các tệp .deb (Debian Packages) và không tự động xử lý các phụ thuộc.
## Chức năng:
* Cài đặt dpkg -i package.deb.
* Gỡ bỏ: dpkg -r package-name.
* Kiểm tra trạng thái: dpkg -l (hiển thị danh sách các gói đã cài đặt).
* Kiểm tra thông tin gói: dpkg -s package-name.
# 2. Advanced Package Took (apt)
## Mô tả: 
* apt là công cụ quản lý gói cấp cao dựa trên dpkg, cung cấp nhiều tính năng hơn và thân thiện với người dùng.
* apt tích hợp khả năng làm việc với các kho lưu trữ (repositories), tự động xử lý các phụ thuộc và cập nhật gói.
## Chức năng:
* Cập nhật danh sách gói: apt update.
* Cài đặt gói: apt install package-name
* Gỡ bỏ gói: apt remove package-name hoặc apt purge package-name (xóa cả cấu hình).
* Cập nhật hệ thống: apt upgrade (cập nhật gói hiện có) hoặc apt dist-upgrade (xử lý nâng cấp lớn hơn).
# 3. Sự khác biệt giữa apt và dpkg
|   Đặc điểm    |   dpkg    |   apt     |
|---------------|-----------|-----------|
|   Cấp độ      |   Low-level|  High-level  |
|   Quản lý phụ thuộc   |   Không tự xử lý phụ thuộc    |   Tự động giải quyết phụ thuộc    |
|   Kho lưu trữ |   Không làm việc với repositories |   Tích hợp với repositories   |
|   Chức năng chính |   Làm việc trực tiếp với tệp .deb |   Làm việc với kho lưu trữ và tự động tải gói |
|   Dễ sử dụng  |   Khó hơn do cần cài từng gói phụ thuộc   |   Dễ hơn, tự động hóa nhiều bước  |
# 4. Khi nào dùng apt và dpkg
## Sử dụng apt: 
* Khi cần cài đặt hoặc quản lý gói từ kho lưu trữ của Ubuntu.
* Khi muốn quản lý hệ thống một cách tự động với ít thao tác thủ công.
## Sử dụng dpkg:
* Khi bạn làm việc với một tệp .deb cụ thể mà không có sẵn trong repository.
* Khi cần khắc phục sự cố hoặc thực hiện các tác vụ quản lý gói nâng cao.

## Cập nhật danh sách gói phần mềm: sudo apt update
## Nâng cấp hệ thống: 
* Nâng cấp tất cả gói đã cài đặt lên phiên bản mới nhất: sudo apt upgrade
* Nâng cấp toàn diện, bao gồm các thay đổi về phụ thuộc gói: sudo apt full-upgrade
## Cài đặt gói phần mềm: sudo apt install <tên_gói>
## Gỡ bỏ gói phần mềm:
* Chỉ gỡ bỏ gói, giữ lại các file cấu hình: sudo apt remove <tên_gói>
* Gỡ bỏ hoàn toàn, bao gồm các file cấu hình: sudo apt purge <tên_gói>
## Dọn dẹp hệ thống: 
* Xóa các gói không còn cần thiết: sudo apt autoremove
* Xóa các gói và cache đã tải xuống: sudo apt clean
## Tìm kiếm gói: apt search <từ_khóa>
## Hiển thị thông tin gói: apt show <tên_gói>
## Kiểm tra các gói bị lỗi hoặc hỏng: sudo apt --fix-broken install