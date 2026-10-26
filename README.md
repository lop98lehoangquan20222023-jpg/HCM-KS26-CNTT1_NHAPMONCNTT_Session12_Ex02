# Bài 2 : Chuẩn bị hồ sơ dự án trước khi triển khai hệ thống


## 📌 Phần 1: Phân Tích (Sơ Đồ Cây Cấu Trúc Heading File SRS)

Cấu trúc phân cấp tài liệu được thiết lập chuẩn Heading Styles nhằm điều hướng trực tiếp trên **Navigation Pane** và xuất mục lục tự động, bao gồm đủ **10 tiêu đề cấp 2 (Heading 2)** tập trung vào module "Lớp học ảo":

```text
SRS: Module Học Trực Tuyến (PTIT-Learning)
│
├── 1. Tổng quan hệ thống (Heading 1)
│   ├── 1.1. Mục tiêu và phạm vi dự án (Heading 2 - #1)
│   ├── 1.2. Đối tượng người dùng & quyền hạn (Heading 2 - #2)
│   └── 1.3. Giả định và sự phụ thuộc (Heading 2 - #3)
│
├── 2. Yêu cầu chức năng - Functional Requirements (Heading 1)
│   ├── 2.1. Quản lý phòng học ảo & phân quyền Video/Audio (Heading 2 - #4)
│   ├── 2.2. Điểm danh tự động qua thời gian tham gia (Heading 2 - #5)
│   ├── 2.3. Tương tác trực tiếp: Bảng trắng & Chia sẻ màn hình (Heading 2 - #6)
│   └── 2.4. Ghi hình bài giảng và lưu trữ đám mây (Heading 2 - #7)
│
└── 3. Yêu cầu phi chức năng & Bảo mật (Heading 1)
    ├── 3.1. Hiệu năng & độ trễ truyền phát trực tuyến (Heading 2 - #8)
    ├── 3.2. Tiêu chuẩn mã hóa đường truyền dữ liệu (Heading 2 - #9)
    └── 3.3. Tương thích trình duyệt và thiết bị (Heading 2 - #10)
```
## 🛠️ Phần 2: Triển Khai Giải Pháp (Word - Excel - PowerPoint)
###  Tài Liệu Word: Quản Lý Khung SRS & Auto TOC
  - Kiểm soát Navigation Pane: Mở tab View $\rightarrow$ tích chọn Navigation Pane. Toàn bộ 3 mục Heading 1 và 10 mục Heading 2 hiển thị theo cấu trúc cây phân cấp để kiểm tra tính toàn vẹn văn bản.
  
  - Quy trình chèn và cập nhật mục lục:

      1. Đặt trỏ chuột tại trang Mục lục $\rightarrow$ chọn thẻ References $\rightarrow$ Table of Contents $\rightarrow$ chọn mẫu tự động.
    
      2. Trước khi lưu file (theo đúng ràng buộc): Chuột phải vào mục lục $\rightarrow$ chọn Update Field $\rightarrow$ tick chọn Update entire table $\rightarrow$ nhấn OK để đồng bộ số trang và tiêu đề mới nhất.2. Bảng Dữ Liệu Excel:

## Phần 3: Kiểm Thử (Quy Trình Xử Lý Lỗi Tra Cứu Tên Bằng Hàm TRIM)
### 1. Nguyên Nhân
Dù nhìn thấy tên sinh viên trùng khớp trên giao diện, bộ lọc Excel vẫn không tìm thấy do chuỗi văn bản chứa khoảng trắng thừa vô hình (Leading spaces ở đầu chuỗi, Trailing spaces ở cuối chuỗi, hoặc nhiều dấu cách liên tiếp giữa các từ) phát sinh trong quá trình import/nhập liệu từ biểu mẫu bên ngoài.
### 2. Các Bước Khắc Phục Bằng Hàm TRIM
1.1 Bước 1 (Tạo cột phụ làm sạch) : 
Chèn một cột phụ F tạm thời ngay bên cạnh cột Họ và tên (Cột B), đặt tên tiêu đề tại F1 là Ten_Chuan_Hoa.

1.2 Bước 2 (Áp dụng công thức TRIM):

Tại ô F2, nhập công thức:

Excel
```
=TRIM(B2)
```

1.3 Bước 3 (Sao chép công thức) : 
Nhấp đúp chuột vào góc dưới bên phải ô F2 (Fill Handle) để áp dụng công thức cho toàn bộ 200 bản ghi.

1.4 Bước 4 (Ghi đè giá trị chuẩn) : 
Chọn toàn bộ dữ liệu cột F $\rightarrow$ nhấn Ctrl + C $\rightarrow$ nhấp chuột phải vào ô B2 $\rightarrow$ chọn Paste as Values (V) để thay thế dữ liệu thô bằng dữ liệu đã chuẩn hóa.

1.5 Bước 5 (Dọn dẹp) : 
Xóa cột phụ F. Sử dụng lại bộ lọc Ctrl + Shift + L để lọc tên; kết quả sẽ hiển thị chính xác 100%.
