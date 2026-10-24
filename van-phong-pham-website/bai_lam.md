# BÀI LÀM – THI THỬ HACKATHON 01

- **Mã đề:** Thi thử
- **Họ tên:** Nguyen Trung Thanh
- **Lớp:** CNTT-3
- **Link repository:** (điền sau khi upload lên GitHub)
- **Hệ điều hành (Windows/macOS):** Windows

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
pwd
ls -Force
mv nhap_hang.txt docs/
mv logo_van_phong_pham.png media/
cp media/logo_van_phong_pham.png backup/
rm temp_131.tmp
cd logs
ls
cd ..
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
![alt text](image.png)
```

## 4.3. Lọc log thủ công

### Lệnh đã chạy

```shell
Get-Content logs/shop.log | Select-String "ERROR" > logs/daily_report.txt
Get-Content logs/daily_report.txt
```

### 2 dòng lỗi đầu tiên trong daily_report.txt

```text
2025-10-28 08:24:28 [ERROR] Thanh toan bi tu choi
2025-10-28 08:30:28 [ERROR] Thanh toan bi tu choi
```

## 4.5. Hoàn thiện script có khung sẵn

### Lệnh chạy script

```shell
.\auto_report.ps1
```

### Nội dung logs/auto_report.txt

```text
=== BAO CAO LOI ===
2025-10-28 08:24:28 [ERROR] Thanh toan bi tu choi
2025-10-28 08:30:28 [ERROR] Thanh toan bi tu choi
2025-10-28 08:33:28 [ERROR] Ket noi kho du lieu that bai
2025-10-28 08:39:28 [ERROR] Ket noi kho du lieu that bai
2025-10-28 08:42:28 [ERROR] Ket noi kho du lieu that bai
2025-10-28 09:12:28 [ERROR] Thanh toan bi tu choi
```

## 4.6. Đếm số dòng lỗi

### Lệnh đã chạy

```shell
Get-Content logs/shop.log | Select-String "ERROR" | Measure-Object
```

### Kết quả

```text
Count: 6
```

## 4.7. Báo cáo tổng hợp

### Lệnh đã chạy

```shell
"=== TONG HOP LOG ===" > logs/tong_hop.txt
Get-Content logs/shop.log | Select-String "WARNING" >> logs/tong_hop.txt
Get-Content logs/shop.log | Select-String "ERROR" | Measure-Object >> logs/tong_hop.txt
```

### Nội dung logs/tong_hop.txt

```text
(DÁN NỘI DUNG tong_hop.txt Ở ĐÂY)
```

## 4.8. Excel

Công thức dòng 2, kéo xuống dòng 16:

```text
E2: =VLOOKUP(C2,SanPham!$A$2:$C$8,2,FALSE)
F2: =VLOOKUP(C2,SanPham!$A$2:$C$8,3,FALSE)
G2: =D2*F2
```

Lọc AutoFilter tien_ban >= 300000: còn 7 dòng (DB001, DB002, DB004, DB007, DB009, DB010, DB014).