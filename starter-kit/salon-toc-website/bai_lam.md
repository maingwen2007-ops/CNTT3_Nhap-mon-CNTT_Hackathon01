# BÀI LÀM – HACKATHON 01

- **Mã đề:** 20
- **Họ tên: Lê Anh Duy** 
- **Lớp: CNTT3** 
- **[Link repository](https://github.com/maingwen2007-ops/CNTT3_Nhap-mon-CNTT_Hackathon01)** 
- **Hệ điều hành (Windows/macOS): Windows** 

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```powershell
PS C:\starter-kit\salon-toc-website> pwd
PS C:\starter-kit\salon-toc-website> ls -Force
PS C:\starter-kit\salon-toc-website> mv .\lich_lam_viec.txt .\docs\
PS C:\starter-kit\salon-toc-website> mv .\logo_salon_toc.png .\media\
PS C:\starter-kit\salon-toc-website> cp .\media\logo_salon_toc.png .\backup\
PS C:\starter-kit\salon-toc-website> rm -Force .\temp_289.tmp
PS C:\starter-kit\salon-toc-website> cd .\logs\
PS C:\starter-kit\salon-toc-website\logs> ls -Force
PS C:\starter-kit\salon-toc-website\logs> cd..	
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)
```text
PS C:\starter-kit\salon-toc-website> ls -Force


    Directory: C:\starter-kit\salon-toc-website


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/28/2026  10:45 AM                backup
d-----        10/28/2026  10:48 AM                data
d-----        10/28/2026  10:45 AM                docs
d-----        10/28/2026  10:48 AM                logs
d-----        10/28/2026  10:45 AM                media
------        10/27/2026   1:32 AM             67 .env
-a----        10/27/2026   1:32 AM           2230 bai_lam.md
-a----        10/27/2026   1:32 AM             62 lich_lam_viec.txt
-a----        10/27/2026   1:32 AM           6113 logo_salon_toc.png
------        10/27/2026   1:32 AM             22 temp_289.tmp
```

## 4.3. Lọc log thủ công

### Lệnh đã chạy

```powershell
PS C:\starter-kit\salon-toc-website> gc .\logs\salon.log|sls "ERROR" > .\logs\daily_report.txt
```

### 2 dòng lỗi đầu tiên trong daily_report.txt

```text
2026-11-28 09:53:35 [ERROR] Khong tim thay trang /kieu-toc-moi (404)
2026-11-28 09:57:35 [ERROR] Khong tim thay trang /kieu-toc-moi (404)
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
PS C:\starter-kit\salon-toc-website> Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
PS C:\starter-kit\salon-toc-website> .\auto_report.ps1
```

### Kết quả hiển thị

```text
=== BAO CAO LOI ===

2026-11-28 09:53:35 [ERROR] Khong tim thay trang /kieu-toc-moi (404)
2026-11-28 09:57:35 [ERROR] Khong tim thay trang /kieu-toc-moi (404)
2026-11-28 10:13:35 [ERROR] Dat lich that bai
2026-11-28 10:33:35 [ERROR] Dat lich that bai
2026-11-28 10:37:35 [ERROR] Thanh toan bi tu choi
```

## 4.6. Đếm số dòng lỗi

### Lệnh

```shell
PS C:\starter-kit\salon-toc-website> (gc .\logs\salon.log|sls "ERROR").count
```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```text
5
```

## 4.7. Báo cáo tổng hợp

### Các lệnh đã chạy

```powershell
PS C:\starter-kit\salon-toc-website> "=== TONG HOP LOG ===" > .\logs\tong_hop.txt
PS C:\starter-kit\salon-toc-website> gc .\logs\salon.log|sls "WARNING" >> .\logs\tong_hop.txt
PS C:\starter-kit\salon-toc-website> (gc .\logs\salon.log|sls "ERROR").count >> .\logs\tong_hop.txt
```

### Nội dung file logs/tong_hop.txt

```text
=== TONG HOP LOG ===

2026-11-28 09:33:35 [WARNING] Anh kieu toc dung luong lon
2026-11-28 09:37:35 [WARNING] Lich toi thu sau sap kin
2026-11-28 10:01:35 [WARNING] Anh kieu toc dung luong lon
2026-11-28 10:09:35 [WARNING] Thoi gian phan hoi cham


5
```

## 4.8. Excel

> Phần Excel được chấm trực tiếp trên file `data/hoa_don_salon_thang_11.xlsx`, không cần ghi vào đây.
