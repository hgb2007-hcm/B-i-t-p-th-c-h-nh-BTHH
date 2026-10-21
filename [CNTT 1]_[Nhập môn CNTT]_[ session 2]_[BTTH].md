# Tech Lead của Cyber Arena

Dưới đây là bản tóm tắt ngắn gọn, đúng chất bài làm của sinh viên:

---

## Phần 1 – Lĩnh vực CNTT & Đơn vị lưu trữ

1. **Chọn Ứng viên B** (Mạng / Quản trị hệ thống).
*Giải thích:* Cyber Arena cần mạng ngon và dàn máy chạy tốt để kinh doanh và cho team tập luyện. Sự cố phần cứng, mạng giật lag cần sửa ngay, còn phần mềm đặt lịch có thể dùng sẵn app ngoài.
2. **Thứ tự tăng dần:**
$$\text{Byte} < \text{KB} < \text{MB} < \text{GB} < \text{TB}$$



---

## Phần 2 – Mô hình IPO & Lĩnh vực CNTT

### 1. Bảng IPO hệ thống quay/xem lại

* **Input:** Hình ảnh, âm thanh trực tiếp từ màn hình máy tính trận đấu.
* **Process:** Phần mềm mã hóa, nén dữ liệu thành file video.
* **Output:** File video trận đấu (~500 MB).
* **Storage:** Ổ cứng SSD 512 GB lưu file video.

### 2. Lĩnh vực CNTT liên quan

* **Mạng máy tính & Truyền thông:** Kéo đường truyền ổn định để chơi game không ping cao và livestream mượt lên YouTube.
* **Quản trị hệ thống:** Bảo trì máy móc, dọn dẹp dung lượng lưu trữ cho trung tâm vận hành trơn tru.

---

## Phần 3 – Dung lượng & Tốc độ mạng

### 1. Dung lượng lưu trữ

* **Tổng 20 trận:** $20 \times 500 \text{ MB} = 10.000 \text{ MB}$
* **Đổi sang GB:** $10.000 \div 1024 \approx 9,77 \text{ GB}$
* **SSD 512 GB:** **Đủ chứa** ($9,77 \text{ GB} < 512 \text{ GB}$). Sau 1 tháng còn trống:
$$512 - 9,77 = 502,23 \text{ GB}$$



### 2. Tốc độ mạng

* **100 Mbps đổi ra MB/s:** $100 \div 8 = 12,5 \text{ MB/s}$
* **Thời gian tối thiểu up clip 200 MB:** $200 \div 12,5 = 16 \text{ giây}$
* **Lý do thực tế lâu hơn:** Tốc độ upload thực tế thường bị nhà mạng hạ thấp hơn download, hoặc bị chia sẻ băng thông với các máy khác trong quán.

---

## Phần 4 – Phần cứng & Mô hình DIKW

### 1. Nâng cấp linh kiện

* **Chọn:** Nâng **CPU**.
* *Giải thích:* Vừa chơi game vừa mã hóa livestream khiến CPU quá tải 100% gây giật lag. Cần CPU nhiều nhân/luồng hơn để gánh đa nhiệm mượt mà.

### 2. Mô hình DIKW

| Tầng | Nội dung | Vì sao thuộc tầng này? |
| --- | --- | --- |
| **Data** | Tuyển thủ hay chết ở phút 15–20. | Chỉ là con số/sự kiện thô chưa qua xử lý. |
| **Information** | Chết ở phút 15–20 do thiếu tầm nhìn (máy thiếu mắt). | Dữ liệu thô đã được gắn bối cảnh để tìm ra nguyên nhân. |
| **Knowledge** | Rút ra kinh nghiệm: Kiểm soát tầm nhìn giữa trận giúp tránh bị bắt lẻ. | Thông tin đúc kết thành bài học chiến thuật. |
| **Wisdom** | HLV chỉ đạo mua thêm mắt (Ward) cho trận sau. | Áp dụng bài học để đưa ra quyết định hành động thực tế. |