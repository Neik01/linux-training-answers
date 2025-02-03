1. 
    - `ip`: Cho phép cài đặt và cấu hình cài đặt mạng
    - `route`: Xem và thay đổi route table của hệ thống
    - `netstat`: Hiển thị các kết nối mạng và các thông tin liên quan
    - `nslookup`: Truy vấn DNS lấy các thông tin về tên miền, địa chỉ IP và các thông tin liên quan
    - `dig`: Phiên bản mạnh mẽ và chi tiết hơn nslookup

2. 
- Chấp nhận truy cập đến cổng 80 và 443 từ bất ký đâu.
    ```bash
    sudo ufw allow 80 
    sudo ufw allow 443 
    ```
- Chấp nhận truy cập đến cổng 3306 từ địa chỉ 192.168.1.11.
    `sudo ufw allow from 192.168.1.11 to any port 3306`

- Chặn truy cập đến cổng 80 và 443 từ địa chỉ 192.168.1.151.
 ```bash
 sudo ufw deny from 192.168.1.151 to any port 80
 sudo ufw deny from 192.168.1.151 to any port 443
 ```
 
- Giới hạn số lần truy cập cổng 22 để chống brute force attacks.
    `sudo ufw limit 22`

3. 
```yaml
networK:
  ethernets:
    ens33:
      adresses: 10.0.1.121 
      routes:
        - to: 10.0.1.0/24
          via: 10.0.1.1
        - to: 0.0.0.0/0
          via: 10.0.1.3
      nameservers:
        addresses:
            - 8.8.8.8
            - 8.8.4.4
```