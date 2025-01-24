1. Các lệnh kiểm tra tiến trình:
- ps
- top hoặc htop

2. Để kiểm tra cổng 3306
- sudo netstat -tulpn | grep :3306
- sudo ss -tuln | grep :3306
- sudo lsof -i :3306

3. Lệnh `kill` sẽ gửi tín hiệu (signal) đặc biệt đến tiến trình và hủy tiến trình đó. Nếu không chỉ định signal thì signal mặc định được gửi là `TERM`

4. 
- HUP: Được gửi khi terminal điều khiển của một tiến trình bị đóng
- INT: Được gửi bởi terminal cho một tiến trình khi người dùng muốn can thiệp vào tiến trình
- KILL: Bắt buộc hủy tiến trình. Không thể bị chặn, bỏ qua hay được tiến trình xử lý
- TERM: Gửi tín hiệu hủy tiến trình, có thể bị chặn, bỏ qua. Cho phép tiến trình hủy và giải phóng tài nguyên thích hợp
- STOP: Dừng tiến trình. Không thể bị chặn, bỏ qua hay được tiến trình xử lý
- CONT: Tiếp tục tiến trình đã bị dừng

5. Thay đổi độ ưu tiên của một tiến trình đang chạy: `renice Priority -p ProcessID`
Thay đổi độ ưu tiên ban đầu của một tiến trình: `nice -n Number CommandString`
6. 
- bg: Chạy tiến trình đã bị tạm ngưng trong background
- fg: Đưa một tiến trình từ background lên foreground
- nohup: Chạy tiến trình, bỏ qua tín hiệu HUP
