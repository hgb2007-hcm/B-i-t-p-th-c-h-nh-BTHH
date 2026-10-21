# Dựng README.md cho Dự Án CLB SmartCampus

***Phần 1 – Khung sườn README***

# SmartCampus :rocket:

Ứng dụng di động **chính thức** giúp sinh viên PTIT tra cứu lịch học, phòng trống và nhận *thông báo* mới nhất từ nhà trường.

- Tra cứu lịch học theo mã sinh viên
  - Hỗ trợ xem chi tiết theo tuần và học kỳ
- Xem danh sách phòng trống theo tòa nhà

[Trang chủ CLB Lập trình](https://ptithcm.edu.vn/)

![Logo SmartCampus](https://tracuuvanbang.ptit.edu.vn/_next/static/media/ptit-logo.fd21b9bd.png)


***Phần 2 – Phần kỹ thuật của README***

### :package: Cài đặt và Chạy dự án

```bash
git clone [https://github.com/clb-lap-trinh/smartcampus.git](https://github.com/clb-lap-trinh/smartcampus.git)
npm install
npm start

Trạng thái tính năng[x] Tra cứu lịch học theo mã sinh viên[x] Xem danh sách phòng trống theo tòa nhà[ ] Thông báo đẩy (push notification)[ ] Đăng nhập bằng tài khoản trườngThư viện sử dụngThư việnPhiên bảnMục đíchReact Native0.74Xây giao diện đa nền tảng iOS/AndroidAxios1.6Gọi API lấy dữ liệu lịch học.


## Phần 3 – Hỏi AI đúng cách và lưu tài liệu

### 1. Prompt theo Công thức 3 Phần
```markdown
## Tôi là ai / Bối cảnh
Tôi là sinh viên năm nhất ngành CNTT, mới tham gia dự án SmartCampus của CLB Lập trình.

## Chủ đề / Nội dung cần xử lý
Giải thích khái niệm "API" trong lập trình ứng dụng di động cho người mới bắt đầu.

## Yêu cầu
- Định nghĩa API bằng ngôn ngữ đơn giản, dễ hiểu.
- Lấy ví dụ thực tế quen thuộc (như nhân viên phục vụ quán ăn).
- Nêu rõ vai trò của API trong việc kết nối app SmartCampus với máy chủ của trường.

## Không cần
- Không giải thích quá sâu về mã nguồn, cấu trúc HTTP request phức tạp hoặc các giao thức mạng nâng cao. 

Chỉ ra 2 lỗi cú pháp trong đoạn code mẫu:

- Lỗi ở Bảng (Table): Thiếu dòng phân cách giữa tiêu đề và nội dung bảng (thiếu dòng |---|---|).

- Lỗi ở Danh sách công việc (Task List): Thiếu khoảng trắng giữa dấu gạch ngang và cặp ngoặc vuông (-[x] thay vì đúng chuẩn là - [x]).

## sửa lại 
| Tính năng | Trạng thái |
| :--- | :--- |
| Tra cứu lịch học | Xong |
| Push notification | Đang làm |

- [x] Tra cứu lịch học
- [ ] Push notification