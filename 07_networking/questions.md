## 07. Networking

1. Tìm hiểu về chức năng của các lệnh sau?

- ip
- route
- netstat
- nslookup
- dig

2. Sử dụng ufw hoặc netfilter (iptables) để thực hiện các việc sau:

- Chấp nhận truy cập đến cổng 80 và 443 từ bất ký đâu.
- Chấp nhận truy cập đến cổng 3306 từ địa chỉ 192.168.1.11.
- Chặn truy cập đến cổng 80 và 443 từ địa chỉ 192.168.1.151.
- Giới hạn số lần truy cập cổng 22 để chống brute force attacks.

3. Viết file config netplan với cấu hình như sau:

- Đặt IP tĩnh cho máy: 10.0.1.121
- Route trong mạng nội bộ 10.0.1.0/24 với gateway 10.0.1.1
- Route ra mạng internet với gateway 10.0.1.3
- DNS: 8.8.8.8 và 8.8.4.4
