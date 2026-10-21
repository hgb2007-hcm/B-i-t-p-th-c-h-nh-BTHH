# Terminal Nâng Cao & Tiền Đề Scripting

***Phần 1 – Đọc và định vị tệp tin***

- **Lệnh in nội dung server.log:** Get-Content logs\server.log


- **Vì sao Notepad dễ treo máy với file 500 MB còn Terminal thì không** 
    - Notepad: Nạp toàn bộ nội dung file 500 MB vào RAM ngay khi mở để hiển thị giao diện, nên nếu file quá lớn sẽ làm cạn kiệt RAM và treo máy.
    - Terminal (PowerShell): Chỉ đọc và xuất dữ liệu từng dòng theo nhu cầu (stream/đọc tuần tự) mà không cần nạp toàn bộ vào bộ nhớ, giúp máy chạy mượt mà, tốn rất ít RAM.

- **Lệnh tìm tất cả file .log trong project:**
  
  - Get-ChildItem -Recurse -Filter *.log

***Phần 2 – Lọc dữ liệu và Pipe***

- **Lệnh lọc các dòng chứa chữ ERROR:** Get-Content logs\server.log | Select-String "ERROR"

- **Lệnh kết hợp Pipe (|) đọc và lọc 404:** Get-Content logs\server.log | Select-String "404"

- **Lệnh tìm file .log rồi lọc bỏ dòng chứa INFO:** Get-ChildItem -Recurse -Filter *.log | Get-Content | Select-String -NotMatch "INFO"

***Phần 3 – Toán tử chuyển hướng > và >>***

- **Lệnh ghi đè kết quả lọc 404 vào báo cáo:** Get-Content logs\server.log | Select-String "404" > reports\daily_report.txt

- **Thêm lỗi mới & giải thích toán tử:** Get-Content logs\server.log | Select-String "404" >> reports\daily_report.txt

***Phần 4 – Shell Script và lệnh echo***

- **Lệnh thông báo và tạo dòng tiêu đề:** Write-Output "Dang loc log..."

Write-Output "=== LOG REPORT ===" > reports\daily_report.txt

- **Nội dung file scripts\auto_report.ps1:** 

 Script tu dong loc loi 404 tu server log va ghi vao bao cao hang ngay
Write-Output "Bat dau chay tien trinh loc log..."
Write-Output "=== LOG REPORT ===" > reports\daily_report.txt
Get-Content logs\server.log | Select-String "404" >> reports\daily_report.txt

***Phần 5 – Viết, chạy và thẩm định Script AI***
- **Quy trình 3 bước thực thi Script:**
  - (a) Lệnh chạy file script: .\scripts\auto_report.ps1
  - (b) Lệnh kiểm tra nội dung file kết quả: Get-Content reports\daily_report.txt

- **Thẩm định đoạn script AI (cleanup.ps1):**
  
  - (a) Dòng nguy hiểm & hậu quả:  
     - Dòng lệnh: Remove-Item -Recurse -Force C:\*
     - Hậu quả: Lệnh này sẽ xóa vĩnh viễn toàn bộ file và thư mục gốc nằm trong ổ đĩa C:\ (bao gồm cả hệ điều hành Windows), khiến máy tính sập nguồn và hỏng hoàn toàn.
  
  - **(b) Sửa lại đường dẫn an toàn:** Remove-Item -Recurse -Force temp\*