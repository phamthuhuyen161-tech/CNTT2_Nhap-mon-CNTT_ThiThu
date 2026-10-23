# BÀI LÀM – THI THỬ HACKATHON 01

- **Mã đề:** Thi thử
- **Họ tên:** Phạm Thu Huyền
- **Lớp:** CNTT2
- **Link repository:** 
- **Hệ điều hành (Windows/macOS):** Windows

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
Get-location
Get-childitem -force
move-item  -path "nhap hang.txt" -destination "docs\"
move-item -path "logo van phong pham.png" -destination "media\"
copy-item -path "media\Logo Van Phong Pham.PNG" -destination "backup\
remove-item ".tmp"
set-location "logs"
get-childitem
set-location ".."

```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
Directory: C:\Users\ADMIN\Downloads\starter-kit(2)\starter-kit\Van Phong Pham Website FINAL


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/23/2026   9:08 AM                logs
------        10/19/2026   9:41 AM             78 .env
-a----        10/19/2026  10:00 AM           2253 bai_lam.md
-a----        10/19/2026   9:41 AM             51 docs
------        10/19/2026   9:41 AM           6105 Don Ban Thang 10.xlsx
------        10/19/2026   9:41 AM           6053 Logo Van Phong Pham.PNG
-a----        10/19/2026   9:41 AM           6053 media
------        10/19/2026   9:41 AM             51 Nhap Hang.txt
------        10/19/2026   9:41 AM           1053 Shop.log

```

## 4.3. Lọc log thủ công

### Lệnh đã chạy

```shell
get-content "logs\shop.log" | select-string "ERROR" | set-content "logs\daily_report.txt"
get-content "logs\daily_report.txt" -totalcount 2
```

### 2 dòng lỗi đầu tiên trong daily_report.txt

```text
2025-10-28 08:24:28 [ERROR] Thanh toan bi tu choi
2025-10-28 08:30:28 [ERROR] Thanh toan bi tu choi

```

## 4.4. Thao tác với tài liệu Markdown (README.md)

> README.md được chấm trực tiếp trên file `README.md` ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [x] Heading 1: tên dự án
- [x] Mô tả ngắn có cả **in đậm** và *in nghiêng*
- [x] Bảng `Thư mục | Nội dung`, ít nhất 3 dòng dữ liệu
- [x] Code block chứa lệnh PowerShell/Terminal liệt kê nội dung dự án
- [x] Task list ít nhất 2 công việc, có ít nhất 1 mục đã hoàn thành
- [x] Blockquote nhắc không upload `.env`

## 4.5. Chạy script auto_report (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
get-content "logs\shop.log" | select-string  "ERROR" | set-content "logs\auto_report.txt"

```

### Nội dung file logs/auto_report.txt

```text
2025-10-28 08:24:28 [ERROR] Thanh toan bi tu choi
2025-10-28 08:30:28 [ERROR] Thanh toan bi tu choi
2025-10-28 08:33:28 [ERROR] Ket noi kho du lieu that bai
2025-10-28 08:39:28 [ERROR] Ket noi kho du lieu that bai
2025-10-28 08:42:28 [ERROR] Ket noi kho du lieu that bai
2025-10-28 09:12:28 [ERROR] Thanh toan bi tu choi


```

## 4.6. Đếm số dòng lỗi

### Lệnh

```shell
get-content "logs\shop.log" | select-string "ERROR"

```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```text
2025-10-28 08:24:28 [ERROR] Thanh toan bi tu choi
2025-10-28 08:30:28 [ERROR] Thanh toan bi tu choi
2025-10-28 08:33:28 [ERROR] Ket noi kho du lieu that bai
2025-10-28 08:39:28 [ERROR] Ket noi kho du lieu that bai
2025-10-28 08:42:28 [ERROR] Ket noi kho du lieu that bai
2025-10-28 09:12:28 [ERROR] Thanh toan bi tu choi

```

## 4.7. Báo cáo tổng hợp

### Các lệnh đã chạy

```shell
set-content -path "logs\tong_hop.txt" -value "=== TONG HOP LOG ==="
get-content -path "logs\shop.log" | select-string -pattern  "WARNING" | add-content -path "logs\tong_hop.txt"
```

### Nội dung file logs/tong_hop.txt

```text
=== TONG HOP LOG ===
2025-10-28 08:51:28 [WARNING] Thoi gian tai trang cham
2025-10-28 08:54:28 [WARNING] Anh san pham dung luong lon
2025-10-28 08:57:28 [WARNING] Thoi gian tai trang cham

```

## 4.8. Excel

> Phần Excel được chấm trực tiếp trên file `data/don_ban_thang_10.xlsx`, không cần ghi vào đây.
