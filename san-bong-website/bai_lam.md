# bai_lam

# BÀI LÀM – HACKATHON 02

- **Mã đề:** 01
- **Họ tên: Nguyen Hai Duong**
- **Lớp:**
- **Link repository:**
- **Hệ điều hành (Windows/macOS): Windows**

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```bash
+ Hiển thị đường dẫn tuyệt đối của thư mục hiện tại: pwd
+ Liệt kê nội dung, gồm cả file ẩn : ls -Force
+ Di chuyển file ghi_chu_ban_giao.txt vào docs :  mv  ghi_chu_ban_giao.txt docs
+ Tạo thư mục backup trong thư mục gốc : mkdir backup
+ Sao chép data/dat_san_thang_10.xlsx vào backup : cp ./data/dat_san_thang_10.xlsx backup
+ Xoá file .tmp tại thư mục gốc; không xoá file khác : rm temp_002.tmp
+ ùng đường dẫn tương đối vào logs, liệt kê nội dung rồi quay lại thư mục gốc : 
       + cd ./logs
       + Get-ChildItem -Recurse -Force
       + cd..
      
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```
 Directory: D:\Luyen_Tap1\starter-kit\starter-kit\san-bong-website

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----         11/3/2026   8:38 AM                backup
d-----         11/3/2026   8:33 AM                data
d-----         11/3/2026   8:36 AM                docs
d-----         11/3/2026   8:31 AM                evidence
d-----         11/3/2026   8:33 AM                logs
d-----         11/3/2026   8:27 AM                web
-a----         11/3/2026   8:27 AM             76 .env
-a----         11/3/2026   8:27 AM           2409 bai_lam.md

    Directory: D:\Luyen_Tap1\starter-kit\starter-kit\san-bong-website\backup

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   8:27 AM           6074 dat_san_thang_10.xlsx

    Directory: D:\Luyen_Tap1\starter-kit\starter-kit\san-bong-website\data

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   8:27 AM           6074 dat_san_thang_10.xlsx

    Directory: D:\Luyen_Tap1\starter-kit\starter-kit\san-bong-website\docs

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   8:27 AM            154 ghi_chu_ban_giao.txt

    Directory: D:\Luyen_Tap1\starter-kit\starter-kit\san-bong-website\logs

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   8:27 AM            956 access.log

    Directory: D:\Luyen_Tap1\starter-kit\starter-kit\san-bong-website\web

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----         11/3/2026   8:27 AM                images
-a----         11/3/2026   8:27 AM            590 app.js
-a----         11/3/2026   8:27 AM            529 index.html
-a----         11/3/2026   8:27 AM            460 style.css

    Directory: D:\Luyen_Tap1\starter-kit\starter-kit\san-bong-website\web\images

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   8:27 AM           3101 logo-san-bong.png
```

## 4.3. Lọc log truy cập website

### a) Lệnh lọc các dòng status=500

```bash
Get-Content ./logs/access.log | Select-String " status=500" > ./logs/loi_500.tx
```

### 2 dòng đầu tiên trong logs/loi_500.txt

```
2026-10-28 08:24:34 POST /api/thanh-toan status=500
2026-10-28 08:28:45 POST /api/thanh-toan status=500

```

### b) Lệnh đếm số dòng status=404 và kết quả

```bash
(Get-Content ./logs/access.log | Select-String "status=404" | Measure-Object).Count
```

```
4
```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```bash
./tong_hop.ps1
```

### Nội dung file logs/tong_hop.txt

```
=== BAO CAO SU CO WEBSITE ===

2026-10-28 08:07:39 GET /tin-tuc status=404
2026-10-28 08:13:01 GET /dat-san-cu status=404
2026-10-28 08:34:07 GET /images/san-7.jpg status=404
2026-10-28 08:57:24 GET /khuyen-mai status=404

Count    : 6
Average  : 
Sum      : 
Maximum  : 
Minimum  : 
Property : 

```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.
> 
- [x]  README.md: Heading 1, mô tả có **in đậm** và *in nghiêng*, bảng, code block, task list, blockquote
- [x]  .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [x]  .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | --- | --- | --- |
| 1 |  |  |  |
| 2 |  |  |  |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).
> 

### Báo cáo lỗi gửi trưởng nhóm

- **Context:**
- **Expected:**
- **Actual:**
- **Log:**

### Câu tìm kiếm Google

```
(Ghi câu tìm kiếm vào đây – xoá dòng này)
```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/dat_san_thang_10.xlsx`, không cần ghi vào đây.
>