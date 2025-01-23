# 02. Working with Files

1. Tìm hiểu về chức năng của các lệnh sau?
- cat
- less
- head
- tail

2. Các dạng tệp (file types) trong linux? Làm cách nào để biết được một file thuộc dạng nào?

3. Tìm hiểu về chức năng của các lệnh sau?
- chmod
- chown
- chgrp

4. Viết lại các câu lệnh để thực hiện các công việc sau:
- Tạo thư mục `permissions_test`
- Trong `permissions_test` tạo các file `file1.txt`, `file2.txt`, `file3.txt`
- Liệt kê các file va quyền gắn với mỗi file, ghi lại quyền được gắn với mỗi file (vd: -rw-r--r--)
- Giải thích ý nghĩa của các quyền theo từng phần:
  - quyền của chủ sở hữu (owner permissions)
  - quyền của nhóm (group permissions)
  - quyền của người khác (other permissions)
- Thay đổi quyền của `file1.txt` để chỉ có chủ sở hữu có quyền đọc và ghi.
- Thay đổi quyền của `file2.txt` để:
  - Chủ sở hữu có quyền đọc và ghi
  - Nhóm có quyền đọc
  - Người khác không có bất cứ quyền gì
- Thay đổi để thêm quyền thực thi (executable) cho tất cả mọi đối tượng với `file3.txt` (các quyền đọc, ghi giữ nguyên)

5. So sánh giữa soft link và hard link.

6. Làm cách nào để giải nén một tập tin có phần mở rộng `.tar.gz`. Giải thích ý nghĩa các thành phần của câu lệnh đó.
