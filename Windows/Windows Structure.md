## OS System Model

* Trong hầu hết các hệ điều hành đa người dùng thì sẽ có 2 mode là kernel mode và user mode:
  * kernel mode: Mã nguồn của kernel chạy trong một chế độ đặc quyền của bộ xử lý, nơi nó có quyền truy cập vào dữ liệu hệ thống và phần cứng
  * user mode: mã nguồn ứng dụng chạy trong một giao diện có sẵn, quyền truy cập giới hạn vào các dữ liệu hệ thống và không thể truy cập vào dữ liệu phần cứng
  * Khi chương trình ở user mode gọi một dịch vụ hệ thống system service thì bộ xử lí thực thi một lệnh đặc biệt để chuyển luồng sang kernel mode. Khi hoàn tất thì trở lại user mode và cho phép tiếp tục thực thi

## 
