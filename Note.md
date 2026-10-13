###### &#x20;**Cách sử dụng RAM**

Notepad cần nạp và quản lý nội dung để hiển thị, chỉnh sửa nên file 500 MB có thể làm ứng dụng chậm hoặc không phản hồi. PowerShell có thể đọc từng dòng và chuyển qua Pipeline để xử lý, giúp hạn chế việc giữ toàn bộ nội dung trong RAM. Tuy nhiên, in toàn bộ file lớn ra màn hình vẫn có thể chậm.

###### &#x20;**Phân biệt tìm file và tìm nội dung**

Tìm file là xác định vị trí của file trong các thư mục, sử dụng Get-ChildItem. Tìm nội dung là kiểm tra các dòng bên trong file, sử dụng Select-String.

###### &#x20;**Phân biệt > và >>**

Toán tử >> thêm nội dung vào cuối file và giữ lại dữ liệu cũ. Nếu dùng nhầm >, báo cáo cũ sẽ bị ghi đè bởi nội dung mới.

###### &#x20;**Khái niệm Shell Script**

Shell Script là file chứa các lệnh để tự động thực hiện một công việc. Script PowerShell được lưu với phần mở rộng .ps1. Muốn script tự chạy hằng ngày cần đặt lịch bằng Task Scheduler.

###### &#x20;**Quy trình Viết – Chạy – Kiểm tra**

Bước 1 – Viết: Nhập nội dung script vào Notepad và lưu thành auto\_report.ps1 trong thư mục scripts.

Bước 2 – Chạy: Mở PowerShell tại thư mục project và chạy script.

Bước 3 – Kiểm tra: Đọc báo cáo, kiểm tra tiêu đề và những dòng chứa lỗi 404.

###### &#x20;**Thẩm định script AI**

Ba nguyên tắc cần thực hiện:

1\. Đọc và hiểu từng lệnh trước khi chạy.

2\. Kiểm tra đường dẫn và các thao tác xóa, ghi đè dữ liệu.

3\. Chạy thử trên dữ liệu mẫu hoặc dùng chế độ xem trước; sao lưu dữ liệu quan trọng.

Dòng nguy hiểm là Remove-Item -Recurse -Force C:\\\*. Lệnh này cố xóa các file, thư mục và nội dung bên trong trên ổ C, có thể gây mất dữ liệu hoặc làm hỏng hệ điều hành. Nó không vượt qua được quyền bảo vệ của hệ thống.

Cần giới hạn việc xóa trong thư mục temp của project và dùng -WhatIf để xem trước.

