## WINDOWS API

* Windows API (Application Programming Interface) là tập hợp các hàm, giao diện lập trình được Microsoft cung cấp để các ứng dụng có thể tương tác với hệ điều hành Windows. Nó cho phép người dùng thao tác với hệ thống tệp, quy trình, bộ nhớ, giao diện đồ họa, thiết bị mạng và nhiều thành phần khác của Windows.
* Windows API 16 bit được dùng trước Windows 95, 32 bit thì bắt đầu từ Windows 95 trở đi, windows 95, 98 vẫn sử dụng cả win32 và win16 để tương thích các ứng dụng cũ
* Từ Windows NT trở đi không còn hỗ trợ bản 16bit
* So sánh Winapi16 và Winapi32

|Tiêu chí	|WinAPI 16 (Windows 3.x)	|WinAPI 32 (Windows 95 trở đi)|
|---|---|---|
|Kiến trúc	|16-bit	|32-bit|
|Multitasking	|Cooperative (cộng tác)	|Preemptive (ưu tiên)|
|Bảo vệ bộ nhớ	|Không có (các ứng dụng có thể ghi vào bộ nhớ của nhau)	|Có (mỗi tiến trình có vùng nhớ riêng)|
|Mô hình địa chỉ	|Segmented memory (phân đoạn)	|Flat memory model (địa chỉ liên tục)|
|Tốc độ và ổn định	|Chậm, dễ crash	|Nhanh hơn, ổn định hơn|
|Hỗ trợ threading	|Không hỗ trợ	|Có hỗ trợ (multi-threading)|
|Cách gọi hàm API	|FAR PASCAL	|WINAPI (dùng __stdcall)|
|Hỗ trợ Unicode	|Không hỗ trợ	|Hỗ trợ (API có hậu tố W, ví dụ: CreateFileW)|

* Windows API lúc đầu chỉ dùng ngôn ngữ C, tuy nhiên có các nhược điểm:
  * Số lượng hàm nhiều
  * Không có quy tắc đặt tên thống nhất
  * Không có cơ chế nhóm hàm theo không gian như C++

-> Vì các lí do trên nên Microsoft cho ra đời một cơ chế mới là COM: Component Object Model

* COM được phát triển để hỗ trợ MS Office trong việc nhúng tài liệu của các ứng dụng office(Như nhúng biểu đồ excel vào Word, PowerPoint). Cơ chế này gọi là Object Linking and Embedding
  * Ban đầu OLE sử dụng cơ chế DDE (Dynamic Data Exchange), một cơ chế truyền thông dựa trên cơ chế windows messages

![ảnh](https://github.com/user-attachments/assets/04efe178-abb5-49ea-9f0c-fe18b6eb624d)

  * Lí do bị thay thế: Tốc độ chậm, không ổn định, không hỗ trợ đa luồng, bảo mật kém(Một số phần mềm office trước đây tự động mở liên kết từ mail chứa mã độc)
  * DDE đã bị thay thế bởi OLE (lúc đầu được gọi là OLE 2) năm 1993
  * COM có 2 nguyên tắc chính là:
    * Giao tiếp với các object (COM Server Object) qua các interface
      * Một COM Object là một thực thể phần mềm cung cấp một hoặc nhiều giao diện (interface) để client có thể gọi đến.
      * Mỗi object này đều thực thi một tập hợp các phương thức (methods) được định nghĩa trong giao diện của nó.
      * Có hai loại object là in-process server (dll com server) và out-of-process server

|Loại COM Server	|Định nghĩa	|Ví dụ|
|---|---|---|
|In-Process Server (DLL COM Server)	|COM Object nằm trong DLL và chạy trong cùng tiến trình với client.	|shell32.dll, msxml6.dll|
|Out-of-Process Server (EXE COM Server)	|COM Object nằm trong một chương trình EXE riêng biệt, chạy trong một tiến trình khác với client.	|Excel.Application, Word.Application|




 
