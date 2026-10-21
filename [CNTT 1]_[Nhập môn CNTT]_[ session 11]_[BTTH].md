# BÁO CÁO THIẾT KẾ KỸ THUẬT & GIẢI PHÁP TỔNG THỂ

***PHẦN 1: THIẾT KẾ KIẾN TRÚC HỆ THỐNG DỮ LIỆU***

**1. Sơ đồ Luồng Dữ liệu (Data Flow Architecture)**

[NGUỒN DỮ LIỆU GỐC] Bảng Excel (Sheet B)
 ├── Quản lý danh sách báo cáo
 └── Danh mục phòng & tra cứu VLOOKUP (Sheet DanhMucPhong)
       │
       ├──► Tài liệu Word (File A: Kế hoạch chi tiết, Auto TOC, H1-3)
       │
       └──► Slide PowerPoint (File C: Khai mạc, Bar/Donut Chart, Rule 10/20/30)


- Thành phần Nguồn (Data Source): Bảng Excel (B). Nơi lưu trữ thông tin gốc của các Báo cáo viên, mã đề tài, phòng họp và định mức thù lao. Tất cả dữ liệu định lượng và phân loại xuất phát từ đây.

- Thành phần Hiển thị (Data Display):
  - Tài liệu Word (A): Nhận thông tin tổng hợp, lịch trình, bảng quy chế và số liệu từ Excel để trình bày văn bản kế hoạch chi tiết cho Ban Giám khảo đọc.

  - Slide PowerPoint (C): Nhận chỉ số tổng hợp (tổng số bài báo, tỷ lệ theo Khoa) từ Excel để trực quan hóa dưới dạng Bar Chart & Donut Chart trình chiếu trước hội nghị.

  **2. Cấu trúc Phân cấp Heading (Word Architecture)**
   
   Tài liệu Kế hoạch (Word) được thiết kế theo chuẩn phân cấp 3 cấp Heading:

   - Heading 1: 1. TỔNG QUAN HỘI NGHỊ KHOA HỌC SINH VIÊN PTIT 2027
     - Heading 2: 1.1. Mục đích và Ý nghĩa Chuyên môn

     - Heading 2: 1.2. Quy mô và Đơn vị Tổ chức

   - Heading 1: 2. CƠ CẤU TỔ CHỨC VÀ HỘI ĐỒNG ĐÁNH GIÁ   
     - Heading 2: 2.1. Ban Tổ chức và Ban Kỹ thuật
     - Heading 2: 2.2. Danh sách Các Phân hội Chuyên môn
  - Heading 1: 3. LỊCH TRÌNH VÀ TIẾN ĐỘ THỰC HIỆN
    - Heading 2: 3.1. Lịch trình Ngày Khai mạc
    - Heading 2: 3.2. Tiến độ Nộp và Duyệt Báo cáo

   - Heading 1: 4. BẢNG KHUNG GIẢI THƯỞNG VÀ ĐỊNH MỨC THÙ LAO
     
     - Heading 2: 4.1. Cơ cấu Giải thưởng Học thuật
     - Heading 2: 4.2. Khung Thù lao Báo cáo viên và Hội đồng

  - Heading 1: 5. QUY CHẾ VÀ QUY ĐỊNH KỸ THUẬT
    - Heading 2: 5.1. Quy định về Báo cáo và Poster
    - Heading 2: 5.2. Quy trình Xử lý Sự cố Kỹ thuật


***PHẦN 2: THIẾT LẬP CHI TIẾT CÁC THÀNH PHẦN***

 - Trang 1: Auto TOC (Table of Contents) được tạo bằng tính năng References -> Table of Contents. Cập nhật tự động dựa trên các thẻ Heading 1, 2, 3.

 - Định dạng: Sử dụng Heading Styles chuẩn (Heading 1: 20pt Bold Navy; Heading 2: 15pt Bold Red; Heading 3: 13pt Semi-bold). Không dùng định dạng thủ công (Format Painter / Font bar) lẻ tẻ.

 - Bảng biểu: Bảng Khung Giải thưởng (Cột: Hạng giải, Số lượng, Giá trị, Quyền lợi kèm theo).

 - Danh sách có thứ tự: 5 bước trong Quy trình nộp slide kỹ thuật (1. Kiểm tra định dạng -> 2. Đặt tên file -> 3. Upload drive -> 4. Checkin thiết bị -> 5. Chạy thử).

 **2. Cấu trúc Bảng Excel (B)** 

 *Sheet 1: DanhSachBaoCao*

 - Các cột: MaTG | HoTen | Khoa | TenBaoCao | MaPhong | Phong | ThuLao

 - Công thức tra cứu tự động VLOOKUP:
   - Cột Phòng (Cột F): =VLOOKUP(E2, DanhMucPhong!$A$2:$C$10, 2, FALSE)
   - Cột Thù lao (Cột G): =VLOOKUP(E2, DanhMucPhong!$A$2:$C$10, 3, FALSE)
 - Hàng Tổng cộng: Được đặt ngoài bảng (phía dưới cùng, cách 1 dòng rỗng hoặc dùng thẻ Total Row) bằng công thức =SUM(G2:G100).

 - Minh họa AutoFilter đa điều kiện:
   - Lọc Khoa = "CNTT" AND Thù lao >= 500,000 VNĐ.

*Sheet 2: DanhMucPhong*
 - Cấu trúc bảng danh mục tra cứu:
 
    PO1 HOI TRUONG A2 500,000
    
    P02 PHONG CHUYEN DE 1 400,000
    
    P03 PHONG CHUYEN DE 2 400,000
    
    P04 PHONG CHUYEN DE 3 400,000

**3. Slide Khai mạc PowerPoint (C)**    
 
 - Rule 10/20/30: Tổng 8 Slide (dưới 10), thời lượng trình chiếu 15-20 phút, Font chữ tiêu đề 32pt - 56pt, nội dung 18pt - 24pt (tuân thủ $\ge$ 30pt cho tiêu đề và $\ge$ 18pt cho nội dung).

 - Thành phần trực quan:
   - Bar Chart (Slide 3): So sánh số lượng đề tài giữa các Khoa.
   - Donut Chart (Slide 4): Biểu diễn tỷ lệ phân bổ các hướng nghiên cứu công nghệ.

***PHẦN 3: BÁO CÁO XỬ LÝ 3 EDGE CASES (TÌNH HUỐNG NGOẠI LỆ)***

**Edge Case 1 (Word): Thay đổi màu Heading 1 trên tài liệu 40 trang**

*Nếu sử dụng Heading Styles*
 - Số thao tác: 3 thao tác.

 - Nhấp chuột phải vào Heading 1 trong tab Home -> Styles.

 - Chọn Modify... 

 - Bấm chọn màu xanh Navy (#0f172a) và bấm OK.

 *Nếu sử dụng Định dạng thủ công*
 - Số thao tác: Ít nhất 80 - 120 thao tác,người dùng phải cuộn qua 40 trang, quét khối từng tiêu đề H1 và đổi màu thủ công 40 lần. Rủi ro cao bị sót tiêu đề hoặc lệch tông màu.

 **Edge Case 2 (Excel): Báo cáo viên mời ngoài chưa có trong DanhMucPhong**
- Hiện tượng: Công thức =VLOOKUP(...) thông thường sẽ trả về lỗi #N/A do không tìm thấy MaPhong tương ứng trong bảng danh mục tra cứu.

- Giải pháp xử lý (Không sửa sheet DanhMucPhong gốc):
Bọc công thức VLOOKUP bằng hàm IFERROR kết hợp giá trị mặc định cho Báo cáo viên khách mời:

  - =IFERROR(VLOOKUP(E2, DanhMucPhong!$A$2:$C$10, 2, FALSE), "Phòng Khách Mời (A1-101)")
  - =IFERROR(VLOOKUP(E2, DanhMucPhong!$A$2:$C$10, 3, FALSE), 600000)

**Edge Case 3 (Slide): Xử lý Slide phụ chứa bảng số liệu chi tiết (Vi phạm Rule 10/20/30)**  
- Đặt vấn đề: Ban giám khảo yêu cầu thêm bảng số liệu đầy đủ (gồm 120 đề tài với 6 cột chi tiết), không thể đưa vào Slide chính vì sẽ làm chữ bị nhỏ (< 14pt) và gây vỡ cấu trúc Rule 10/20/30.

- **Giải pháp Kỹ thuật:** Kỹ thuật "Append Annex Slides" (Slide Phụ lục): Đặt slide bảng số liệu này ở cuối bộ slide (Slide 9 - Slide Phụ lục), nằm sau slide Closing/Q&A.

- **Tạo Hyperlink / Action Button ngầm:** Trên Slide chính (Slide 3 - Bar chart), tạo một nút ẩn hoặc Icon [Chi tiết...] có gắn liên kết (Insert -> Link -> Place in This Document -> Slide 9).

- Tạo nút "Back" trên Slide Phụ lục: Gắn link quay trở lại Slide 3.

**Quy trình vận hành khi thuyết trình:**

- Thuyết trình bình thường với 8 slide gọn gàng, đúng chuẩn Rule 10/20/30.
- Khi Ban giám khảo chất vấn về số liệu chi tiết, bấm vào nút [Chi tiết...] để chuyển nhanh sang Slide Phụ lục 9 giải trình.
- Giải trình xong bấm nút Back để quay lại luồng trình chiếu chính mà không làm gián đoạn trải nghiệm người nghe.