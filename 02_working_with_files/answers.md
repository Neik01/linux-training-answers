1. Chức năng các lệnh:
- cat: Nối nội dung của file ra ouput
- less: Đọc và hiển thị nội dung của file theo trang ra output, cho phép cuộn lên và cuộn xuống nội dung trung file
- head: Lấy một số dòng từ đầu file ra output, mặc định là 10
- tail: Lấy một số dòng từ cuói file ra output, mặc định 10

2. Các dạng tệp (file types) trong linux:
- Tệp thông thường (Regular file): Các tệp chứa văn bản, dữ liệu, hình ảnh, chương trình
- Tệp thư mục (Directory file): Tệp chứa các "lối vào" (entry) đến các tệp khác
- Tệp thiết bị khối (Block file): Tệp đặc biệt đại diện cho các thiết bị thực hiện Input và Output dữ liệu theo đơn vị khối (units of blocks) 
- Tệp thiết bị ký tự (Character device file): Đọc/ghi dữ liệu theo từng ký tự trong file. Sử dụng  để kết nối trực tiếp với các thiết bị phần cứng
- Đường ống đặt tên (Named pipe file): Là một loại tệp đặc biệt cho phép chuyển dữ liệu từ Output của tiến trình này sang Input của tiến trình khác. Hoạt động theo cơ chế First in, First out 
- Tệp liên kết biểu tượng (Symbol link file): Một loại tệp mà sẽ trỏ về tệp khác trong hệ thống
- Tệp Socket (Socket file): Tệp đặc biệt dùng để truyền thông tin giữa các ứng dụng và các tiến trình

3. Chức năng của các lệnh:
- chmod: Thay đổi quyền của một file
- chown: Thay đổi chủ sở hữu và/hoặc nhóm sở hữu của file
- chgrp: Thay đổi nhóm sở hữu của file

4. 
- Tạo thư mục `permissions_test`: 
    `mkdir permissions_test`

- Trong `permissions_test` tạo các file `file1.txt`, `file2.txt`, `file3.txt`:
    ```bash
    cd permission_test
    touch file{1..3}.txt
    ```

- Liệt kê các file va quyền gắn với mỗi file, ghi lại quyền được gắn với mỗi file (vd: -rw-r--r--):
    - file1.txt: -rw-rw-r--
    - file2.txt: -rw-rw-r--
    - file3.txt: -rw-rw-r--

- Giải thích ý nghĩa của các quyền theo từng phần:
  - quyền của chủ sở hữu (owner permissions): Đọc, ghi, không thực thi 
  - quyền của nhóm (group permissions): Đọc, ghi, không thực thi
  - quyền của người khác (other permissions): Chỉ đọc

- Thay đổi quyền của `file1.txt` để chỉ có chủ sở hữu có quyền đọc và ghi.
    `chmod 600 file1.txt` hoặc `chmod u=rw,go= file1.txt`

- Thay đổi quyền của `file2.txt` để:
  - Chủ sở hữu có quyền đọc và ghi: `chmod u=rw file2.txt`
  - Nhóm có quyền đọc: `chmod g=r file2.txt`
  - Người khác không có bất cứ quyền gì: `chmod o= file2.txt`

- Thay đổi để thêm quyền thực thi (executable) cho tất cả mọi đối tượng với `file3.txt` (các quyền đọc, ghi giữ nguyên): `chmod a+x file3.txt`

5. So sánh soft link và hard link
- Soft link: Trỏ vào đường dẫn file, khi file gốc bị mất, xóa thì liên kết này sẽ bị hỏng. Soft link có thể link vào thư mục, có thể trỏ qua nhiều file system
- Hard link: Trỏ vào inode của file, khi file gốc bị mất, xóa thì dữ liệu vẫn còn tồn tại trên liên kết. Hard link không thể tạo với thư mục và qua nhiều file system

6. Dùng câu lệnh: `tar -xzf file.tar.gz` để giải nén tệp có phần mở rộng `.tar.gz`
Giải thích: 
    - `tar`: Sử dụng chương trình tar
    - `-x`: Tùy chọn để giải nén tệp
    - `-z`: Tùy chọn dùng gzip cho tệp có `.gz`
    - `-f`: Chỉ định tệp mà chương trình sẽ thực hiện công việc
    - `file.tar.gz`: Tên tệp cần giải nén