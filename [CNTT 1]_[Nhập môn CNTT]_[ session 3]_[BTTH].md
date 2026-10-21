# Kiến Trúc Hệ Điều Hành & Tư Duy Quản Lý File

***Phần 1 — Kiến trúc Hệ điều hành***

- ***Chức năng & cơ chế chạy cùng lúc:***

Đây là chức năng Quản lý tiến trình (Process Management) và Quản lý bộ nhớ.

Máy chạy ngon 4 app cùng lúc nhờ CPU chia thời gian xử lý cực nhanh (Time-sharing) và hệ điều hành cấp riêng cho mỗi app một vùng RAM độc lập, không va chạm nhau.

 - ***Xử lý Shell/Kernel:***

Khi click đúp file, Shell sẽ hứng lệnh đầu tiên (dịch hành động click thành lệnh máy) rồi mới gửi cho Kernel.

Mình không thao tác thẳng với Kernel vì Kernel nắm quyền quản lý phần cứng tối cao, chỉ cần người dùng nhấp nhầm một lệnh là crash hệ thống (màn hình xanh) ngay.

***Phần 2 — Cây thư mục & Ổ đĩa***

 ***Xác định các thành phần:***

- Root Directory: D:\

- Parent Directory của anh 1.jpg: Thư mục Hinh anh

- Vai trò file anh 1.jpg: Là Lá (nút cuối cùng, không chứa cái gì khác).

***Nguy cơ lưu dữ liệu ở C:\ (Desktop/Downloads):***

- (1) Ổ C chứa Windows, máy bị lỗi phải cài lại Win là mất sạch bài làm.
- (2) Desktop dễ bị vỡ phông, lỗi đường dẫn khi nén gửi đi.
- Nơi lưu đúng: Chuyển hết sang phân vùng dữ liệu D:.

***Phần 3 — Đường dẫn Path***

***Absolute Path:***

D:\Nam1\HocKy1\MonHoc\CongNgheThongTin\BaiTapLon\Session02\BaoCaoCuoiKy\Chuong1\Hinh anh\anh 1.jpg

***Relative Path & lý do dùng:***

- Cú pháp chèn từ report.html: assets/logo.png
- Lý do không bị lỗi: Đường dẫn tương đối chỉ liên kết các file bên trong thư mục dự án với nhau. Lúc gửi cho thầy, thầy mở ở ổ C, ổ D hay máy Mac thì code vẫn tự tìm đúng file logo.

***Phần 4 — Quy tắc Đặt tên chuẩn***


- bao-cao-bai-tap-lon-it101-v2.docx

***Phần 5 — Tổ chức & Dọn dẹp Ổ đĩa***

- Đường dẫn cũ lồng tận 9 cấp thư mục, vi phạm Quy tắc 3 Cấp (quá sâu, rất dễ bị lỗi dài đường dẫn trong Windows).

- Sửa lại đúng chuẩn 4 Trụ Cột (Ổ D:):

D:\01_HocTap\IT101\BaoCao\anh 1.jpg

(Cấp 1: 01_HocTap | Cấp 2: IT101 | Cấp 3: BaoCao)

***Phần 6 — Đuôi file & File ẩn***

**Nhận diện cạm bẫy mã độc:**

- Cạm bẫy: Tên thật của nó là de-thi-dap-an.pdf.exe. Do Win đang ẩn đuôi file nên nó che mất chữ .exe, làm mình tưởng file PDF rồi bấm vào là dính virus/mã độc liền.
- Cách bật hiện đuôi file: Mở File Explorer $\rightarrow$ chọn tab View $\rightarrow$ tích chọn ô File name extensions. Lúc này đuôi file thật sẽ lộ ra ngay.