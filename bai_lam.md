# BÀI LÀM – HACKATHON 01

- **Mã đề:** 14
- **Họ tên:** 
- **Lớp:** 
- **Link repository:** 
- **Hệ điều hành (Windows/macOS):Windows** 

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
pwd
ls -Force
Move-Item huong_dan_cham_soc.txt docs
Move-Item logo_Nha_Khoa.png media
Coppy-Item media\logo_Nha_Khoa.png backup
Remove-Item *.tmp
cd logs
ls
cd ..

```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
Mở PowerShell tại thư mục gốc (trong Explorer, bấm chuột phải vào chỗ trống => open in terminal, rồi gõ lần lượt:
pwd                                    1. Hiện đường dẫn tuyệt đối thư mục hiện tại
ls -Force                             2. Liệt kê nội dung, gồm cả file ẩn (.env)
Move-Item mau_goi_qua.txt docs         3a. Chuyển file txt vào docs
Move-Item logo_*.png media             3b. Chuyển file logo vào media
Copy-Item media\logo_*.png backup      4. Sao chép (không phải chuyển) logo vào backup
Remove-Item *.tmp                      5. Xóa file .tmp ở thư mục gốc
cd logs                                6. Vào logs bằng đường dẫn tương đối 
ls                                          Liệt kê nội dung 
cd  ..                                 	Quay lại thư mục gốc


```

## 4.3. Lọc log thủ công

### Lệnh đã chạy

```shell
Get-Content logs\Clinic.log | Select-String "ERROR" 

```

### 2 dòng lỗi đầu tiên trong daily_report.txt

```text
2026-04-28 09:51:29 [ERROR] Ket noi he thong ho so that bai
2026-04-28 10:07:29 [ERROR] Khong tim thay trang /bang-gia-dich-vu (404)

```

## 4.4. Thao tác với tài liệu Markdown (README.md)

> README.md được chấm trực tiếp trên file `README.md` ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [X] Heading 1: tên dự án
- [x] Mô tả ngắn có cả **in đậm** và *in nghiêng*
- [x] Bảng `Thư mục | Nội dung`, ít nhất 3 dòng dữ liệu
- [x] Code block chứa lệnh PowerShell/Terminal liệt kê nội dung dự án
- [x] Task list ít nhất 2 công việc, có ít nhất 1 mục đã hoàn thành
- [x] Blockquote nhắc không upload `.env`

## 4.5. Chạy script auto_report (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
.\auto_report.ps1

```

### Kết quả hiển thị

```text
Dang loc log...
Hoan thanh!

```

## 4.6. Đếm số dòng lỗi

### Lệnh

```shell
(Get-Content logs\Clinic.log | Select-String "ERROR" | Measure-Object).Count


•	| (pipeline) chuyển kết quả của lệnh trước sang lệnh sau.
•	Measure-Object là đếm.
•	.Count lấy ra con số.


```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```text
5

```

## 4.7. Báo cáo tổng hợp

### Các lệnh đã chạy

```shell
Tạo logs\tong_hop.txt đúng thứ tự: dòng tiêu đề => các dòng WARNING => số dòng ERROR.
"=== TONG HOP LOG ===" > logs\tong_hop.txt
Get-Content logs\Clinic.log | Select-String "WARNING" >> logs\tong_hop.txt
(Get-Content logs\Clinic.log | Select-String "ERROR" | Measure-Object).Count >> logs\tong_hop.txt
Get-Content logs\tong_hop.txt


```

### Nội dung file logs/tong_hop.txt

```text
2026-04-28 09:19:29 [INFO] Benh nhan dat lich kham
2026-04-28 09:23:29 [INFO] Gui tin nhan nhac lich
2026-04-28 09:27:29 [WARNING] Thoi gian phan hoi cham
2026-04-28 09:31:29 [WARNING] Anh X-quang dung luong lon
2026-04-28 09:35:29 [INFO] Bac si cap nhat ho so
2026-04-28 09:39:29 [WARNING] Anh X-quang dung luong lon
2026-04-28 09:43:29 [INFO] Bac si cap nhat ho so
2026-04-28 09:47:29 [INFO] Benh nhan dat lich kham
2026-04-28 09:51:29 [ERROR] Ket noi he thong ho so that bai
2026-04-28 09:55:29 [INFO] Benh nhan dat lich kham
2026-04-28 09:59:29 [INFO] Bac si cap nhat ho so
2026-04-28 10:03:29 [INFO] Benh nhan dat lich kham
2026-04-28 10:07:29 [ERROR] Khong tim thay trang /bang-gia-dich-vu (404)
2026-04-28 10:11:29 [WARNING] Lich kham chieu thu bay sap kin
2026-04-28 10:15:29 [INFO] Benh nhan dat lich kham
2026-04-28 10:19:29 [ERROR] Ket noi he thong ho so that bai
2026-04-28 10:23:29 [INFO] Xac nhan lich hen
2026-04-28 10:27:29 [ERROR] Ket noi he thong ho so that bai
2026-04-28 10:31:29 [INFO] Thanh toan thanh cong
2026-04-28 10:35:29 [ERROR] Dat lich hen that bai



```

## 4.8. Excel

> Phần Excel được chấm trực tiếp trên file `data/dieu_tri_thang_4.xlsx`, không cần ghi vào đây.
