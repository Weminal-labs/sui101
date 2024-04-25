# Setup WSL2

## 1. Cấu hình mặc định của WSL2:
- RAM: 4GB
- Disk: dung lượng của Ubuntu không tự động giảm đi sau khi xóa dữ liệu. Ví dụ, nếu bạn tải xuống một tệp 10 GB, ổ đĩa trong Ubuntu WSL2 sẽ được Windows cấp thêm 10 GB. Tuy nhiên, sau khi bạn xóa bớt dữ liệu, Windows không tự động thu hồi lại 10 GB đó đã được cấp cho WSL2.

## 2. Hướng dẫn setup

### File cấu hình .wslconfig
```
[wsl2]
memory=8GB

[experimental]
sparseVhd=true
```

### Video hướng dẫn
Các bạn làm theo [video](https://www.youtube.com/watch?v=1IWZiCh1WSA) này nhé. 

### Kiểm tra
Có thể kiểm tra lại RAM bằng **neofetch** hoặc **free** command.

Kiểm tra dung lượng ổ cứng bằng **df** command hoặc vào Apps > Installed apps > Ubuntu trên Windows

## 3. References
[windows 10 - How do I get back unused disk space from Ubuntu on WSL2? - Super User](https://superuser.com/questions/1606213/how-do-i-get-back-unused-disk-space-from-ubuntu-on-wsl2)
[Windows Subsystem for Linux September 2023 update - Windows Command Line (microsoft.com)](https://devblogs.microsoft.com/commandline/windows-subsystem-for-linux-september-2023-update/#automatic-disk-space-clean-up-set-sparse-vhd)
[How to Configure Memory Limits in WSL 2 | Limiting Memory Usage in WSL 2 - YouTube](https://www.youtube.com/watch?v=1IWZiCh1WSA)
