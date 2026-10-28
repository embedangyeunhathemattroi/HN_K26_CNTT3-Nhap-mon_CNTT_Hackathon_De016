# BÀI LÀM – HACKATHON 01

- **Mã đề:** 16
- **Họ tên:* Phạm Ngọc Linh * 
- **Lớp:*K26CNTT3* 
- **Link repository:** 
- **Hệ điều hành (Windows/macOS):*Windows* 

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
-,pwd
-,ls -Force
-,mv quy_dinh_bao_cao.txt docs
-,mv logo_sua_may_tinh.png media
-,cp .\media\logo_sua_may_tinh.png .\backup\
-,rm temp_241.tmp
-,cd logs
ls
cd ..
-, Get-ChildItem -Recurse -Force


```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
   Directory: C:\Users\TRONG TIN\Downloads\sua-may-tinh-website


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/28/2026  10:55 AM                backup
d-----        10/28/2026  10:49 AM                data
d-----        10/28/2026  10:44 AM                docs
d-----        10/28/2026  10:49 AM                logs
d-----        10/28/2026  10:50 AM                media
-a----        10/27/2026   1:32 AM             72 .env
-a----        10/28/2026  10:48 AM           2273 bai_lam.md
-a----        10/27/2026   1:32 AM             61 quy_dinh_bao_hanh.txt


    Directory: C:\Users\TRONG TIN\Downloads\sua-may-tinh-website\backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026   1:32 AM           6767 logo_sua_may_tinh.png


    Directory: C:\Users\TRONG TIN\Downloads\sua-may-tinh-website\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026   1:32 AM           6101 phieu_sua_thang_6.xlsx


    Directory: C:\Users\TRONG TIN\Downloads\sua-may-tinh-website\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026   1:32 AM           1069 repair.log


    Directory: C:\Users\TRONG TIN\Downloads\sua-may-tinh-website\media


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/27/2026   1:32 AM           6767 logo_sua_may_tinh.png

```

## 4.3. Lọc log thủ công

### Lệnh đã chạy

```shell
-,get-content .\logs\repair.log | select-string "ERROR" >> .\logs\daily_report.txt
-,get-content .\logs\daily_report.txt

```

### 2 dòng lỗi đầu tiên trong daily_report.txt

```text
2026-06-28 08:57:31 [ERROR] Thanh toan bi tu choi
2026-06-28 09:01:31 [ERROR] Thanh toan bi tu choi

```

## 4.4. Thao tác với tài liệu Markdown (README.md)

> README.md được chấm trực tiếp trên file `README.md` ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [ ] Heading 1: tên dự án
- [ ] Mô tả ngắn có cả **in đậm** và *in nghiêng*
- [ ] Bảng `Thư mục | Nội dung`, ít nhất 3 dòng dữ liệu
- [ ] Code block chứa lệnh PowerShell/Terminal liệt kê nội dung dự án
- [ ] Task list ít nhất 2 công việc, có ít nhất 1 mục đã hoàn thành
- [ ] Blockquote nhắc không upload `.env`

## 4.5. Chạy script auto_report (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
-,Set -ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
-,.\auto_report.ps1

```

### Kết quả hiển thị

```text
Dang loc log ...
Hoan Thanh !
```

## 4.6. Đếm số dòng lỗi

### Lệnh

```shell
-, get-content .\logs\repair.log | select-string "ERROR" | measure-object

```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```text
Count    : 6
Average  :
Sum      :
Maximum  :
Minimum  :
Property :


```

## 4.7. Báo cáo tổng hợp

### Các lệnh đã chạy

```shell "=== TONG HOP LOG  ==="
>> Get-Content .\logs\repair.log | Select-String "WARNING"
>> Get-Content .\logs\repair.log | Select-String "ERROR" | measure-object
```

### Nội dung file logs/tong_hop.txt

```text
=== TONG HOP LOG  ===

2026-06-28 08:33:31 [WARNING] Anh chup may dung luong lon
2026-06-28 08:37:31 [WARNING] Thoi gian phan hoi cham
2026-06-28 08:45:31 [WARNING] Linh kien RAM sap het
2026-06-28 09:09:31 [WARNING] Anh chup may dung luong lon

Count    : 6
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

```

## 4.8. Excel

> 