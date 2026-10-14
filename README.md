#  Lấy tất cả file có đuôi .log 


## Bước 1 : tìm file .log

- ta dùng lệnh sau : `Get-ChildItem "D:\HeThong_Web_Logs" ` . Khi này lệnh sẽ truy cập vào folder HeThong_Web_Logs 

## Bước 2 : Lọc file .log bị lỗi (ERROR)

- Ta dùng lệnh sau : `Get-ChildItem "D:\HeThong_Web_Logs  | Select-String 'ERROR' `
- Khi này lệnh sẽ tìm những file có ERROR , rồi xuất ra màn hình

## Bước 3 : Bước cuối cùng là điền vào file.txt

-  Ta dùng lệnh sau để điền vào file.txt

```powershell
Get-ChildItem "D:\HeThong_Web_Logs  | Select-String 'ERROR' | ForEach-Object {$_.line}` | Add-Content baitap.txt
```

- lệnh trên giúp ta Đọc -> Lọc -> xuất dữ liệu ra không bị lỗi khoảng trắng -> và điền vào baitap.txt   
