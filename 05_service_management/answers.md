1. 
- Service là tiến trình hoặc chương trình chạy trong background. Có thể đang thực hiện những công việc đã được định nghĩa hoặc đợi sự kiện nào đó xảy ra
- Chức năng chính của serivce: Cung cấp dịch vụ hệ thống, quản trị mạng, quản lý phần cứng, thực hiện các tác vụ định kỳ, giám sát hệ thống

2. 
- `sudo systemctl enable <service_name>` 

3. 
- `systemctl list-units -type=service --all`

4. File cron.service: 
```bash
[Unit]
Description=Regular background program processing daemon
Documentation=man:cron(8)
After=remote-fs.target nss-user-lookup.target

[Service]
EnvironmentFile=-/etc/default/cron
ExecStart=/usr/sbin/cron -f $EXTRA_OPTS
IgnoreSIGPIPE=false
KillMode=process
Restart=on-failure

[Install]
WantedBy=multi-user.target
```

Giải thích:
- `[Unit]`: Phần thông tin mô tả của service
    + `Description`: Mô tả đơn giản về service
    + `Documentation`: Nguồn tài liệu
    + `After`: Những service phải được khởi động trước service này
- `[Service]`: Định nghĩa cách service hoạt động
    + `EnvironmentFile`: File biến môi trường
    + `ExecStart`: Câu lệnh thực thi khi service khởi động
    + `IgnoreSIGPIPE`: Phớt lờ tín hiệu SIGPIPE hay không
    + `KillMode`: Chỉ định cách mà tiến trình sẽ bị hủy bỏ
    + `Restart`: Xác định xem khi nào service nên tự khởi động lại
- `[Install]`: Thông tin về tiến trình cài đặt
    + `WantedBy`: Chỉ định target sẽ khởi chạy service này khi hệ thống chạm đến target

5. `journalctl -u <service>`

6. 
- `systemctl isolate`: Khởi động service được chỉ định và các dependency của nó và dừng tất cả service khác
- `systemctl mask`: Vô hiệu hóa hoàn toàn một service, ngăn không cho nó khởi động dù bằng thủ công hoặc tự động
- `systemctl unmask`: Hoàn tác lại tác dụng của lệnh mask, cho phép service khởi động bình thường