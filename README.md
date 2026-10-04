# Bài 4: Cấu hình tường lửa bảo vệ máy chủ (UFW & Cloud Firewall Integration)

## Lớp 1: Cấu hình UFW (Uncomplicated Firewall) trên OS
Chạy các lệnh sau trên Droplet để cấu hình UFW:

```bash
# Thiết lập chính sách mặc định chặn các truy cập vào và cho phép truy cập ra
sudo ufw default deny incoming
sudo ufw default allow outgoing

# Cho phép cổng SSH (22) và HTTP (80)
sudo ufw allow 22/tcp
sudo ufw allow 80/tcp

# Kích hoạt tường lửa
sudo ufw enable

# Kiểm tra trạng thái tường lửa
sudo ufw status verbose
```

**Đầu ra lệnh `sudo ufw status verbose`:**
```text
[Học viên chèn kết quả log text của lệnh ufw status verbose tại đây]
```

## Lớp 2: Cấu hình DO Cloud Firewall
- Truy cập giao diện quản lý Cloud Firewall trên DigitalOcean Console.
- Tạo Cloud Firewall mới và cấu hình Inbound Rules:
  - Cho phép **SSH (cổng 22)** từ mọi nguồn (All IPv4/IPv6).
  - Cho phép **HTTP (cổng 80)** từ mọi nguồn (All IPv4/IPv6).
- Gán (Assign) Droplet của bạn vào Cloud Firewall này.

**Ảnh chụp màn hình thiết lập Cloud Firewall trên DigitalOcean:**

![Cloud Firewall]()
