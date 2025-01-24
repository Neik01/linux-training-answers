1.
- stdin (File descriptor: 0): Luồng dữ liệu đầu vào mặc định của chương trình. Stdin có thể lấy từ bàn phím hoặc chuyển hướng từ file, chương trình khác
- stdout (File descriptor: 1): Luồng dữ liệu đầu ra mặc định của chương trình để hiển thị ở terminal. Có thể chuyển hướng dữ liệu vào file hoặc đến chương trình khác làm input
- stderr (File descriptor: 2): Luồng dữ liệu thông báo lỗi của chương trình. Luồng này cũng được gửi đến terminal nhưng độc lập với stdout. Có thể chuyển hướng vào file hoặc input

2. 
- cut: Cắt các phần trong một dòng của file và ghi vào stdout
- awk: Là một ngôn ngữ kịch bản dùng để xử lý văn bản và tạo báo cáo
- grep: Tìm kiếm văn bản theo một pattern
- sort: Sắp xếp nội dung trong file 
- uniq: Lọc ra các dòng lặp liên tiếp trong tệp đầu vào, phải sắp xếp nội dung file trước
- wc: Đếm số dòng, số từ, số ký tự, số byte

3. `awk '{print $1}' web_access.log | sort | uniq > result.tx`

4. `awk '{if($(NF-1) == 500) print} web_access.log> result2.txt'`

5. `awk '{print substr($(NF-4),2)} web-access.log | sort | uniq -c > result3.txt'`

6. `awk '{print $(NF-3)}' web-access.log | sort| uniq -c | sort | tail -n 3 > result4.txt`

7. `awk -v sum=0 '{sum+=$(NF)} END{print sum}' web-access.log > result5.txt`