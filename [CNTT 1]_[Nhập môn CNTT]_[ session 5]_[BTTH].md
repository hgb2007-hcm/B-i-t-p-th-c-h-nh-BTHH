# Giao Diện Dòng Lệnh Terminal Cơ Bản

***Phần 1 – CLI vs GUI và cấu trúc câu lệnh***

**Phân tích câu lệnh ls -Force C:\Windows\Logs:**

- Command: ls (hoặc cmdlet Get-ChildItem)
- Options/Flags: -Force
- Argument: C:\Windows\Logs

**Lý do dùng Terminal với máy chủ Cloud:**

- Tiết kiệm tài nguyên (Không tốn GUI): Máy chủ Cloud tối ưu hóa toàn bộ tài nguyên (RAM, CPU) cho việc chạy ứng dụng/dịch vụ thay vì tốn kém tải giao diện đồ họa nặng nề.

***Phần 2 – Điều hướng hệ thống file***

Lệnh Relative Path để vào quan-ly-sinh-vien:
- cd .\quan-ly-sinh-vien

Absolute Path tới file main.py:

- C:\Users\student\Desktop\quan-ly-sinh-vien\src\main.py

Xem nội dung thư mục data\ từ src\ (dùng ký hiệu ..):

- ls -Force ..\data

***Phần 3 – Thao tác file và thư mục***

Tạo 2 thư mục src và data (tạo luôn thư mục cha quan-ly-sinh-vien):

- mkdir quan-ly-sinh-vien\src, quan-ly-sinh-vien\data

Tạo 3 file rỗng trong một dòng lệnh:

- New-Item quan-ly-sinh-vien\src\main.py, quan-ly-sinh-vien\src\utils.py, quan-ly-sinh-vien\README.md -ItemType File

Đổi tên và sao lưu project:

Lệnh đổi tên thư mục: mv quan-ly-sv quan-ly-sinh-vien

Lệnh copy: cp -Recurse quan-ly-sinh-vien backup-quan-ly-sinh-vien

***Phần 4 – Xử lý lỗi Terminal***

Log lỗi số 2 (cd scr - Không tìm thấy đường dẫn):

- Chẩn đoán: Lỗi gõ sai chính tả đường dẫn (gõ nhầm scr thay vì src).
- Cách kiểm tra bằng phím Tab: Gõ cd sc rồi nhấn Tab, PowerShell sẽ tự động điền nốt chữ r còn thiếu hoặc báo lỗi nếu không khớp.

Log lỗi số 3 (Access is denied):

- Chẩn đoán: Lỗi từ chối quyền thực thi script bảo mật của PowerShell (Execution Policy).
- Cách khắc phục: Chạy lệnh nới lỏng quyền: Set-ExecutionPolicy RemoteSigned -Scope Process rồi chạy lại file .\setup.ps1.

Log lỗi số 1 (rm old-version cảnh báo file có chứa thư mục con):

- Chẩn đoán: Do thư mục old-version bên trong vẫn còn các file/thư mục con, PowerShell chặn lại để tránh xóa nhầm dữ liệu quan trọng.
- Lệnh xóa: rm -Recurse -Force old-version

