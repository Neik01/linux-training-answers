1. Ý nghĩa các câu lệnh:
    - ls: List file và directory
    - cd: Chuyển vị trí
    - pwd: In vị trí hiện tại
    - man: Hiện hướng dẫn sử dụng của 1 lệnh

2. Ý nghĩa / chức năng của các thư mục:
    - /home: Chứa dữ liệu cá nhân của người dùng
    - /bin: Chứa file binary hoặc file thực thi
    - /sbin: Chứa file binary có thể thực thi cho admintrator
    - /etc: Thư mục chứa các file cấu hình của hệ thống
    - /var: Nơi chương trình lưu trữ thông tin trong quá trình chạy như logs, cache, user tracking
    - /usr: Nơi chứa file thực thi, thư viện, source của hầu hết chương trình
    - /lib: Chứa các thư viện chung cho các chương trình
    - /tmp: Chứa các file tạm thời cho chương trình

3. 
- Di chuyển đến thư mục `/tmp`: `cd /tmp`
- Tạo các thư mục `alpha`, `beta`, `gamma`: `mkdir alpha beta gamma`
- Tạo thư mục `omega` trong `beta`: `mkidir beta/omega*`
- Tạo file `alphabet.txt` với nội dung là bảng chữ cái tiếng Anh trong thư mục `alpha`:
    `echo {a..z} > alpha/alphabet.txt`
- Tạo file `numberber.txt` với nội dung là các số 1-9 trong thư mục `gamma`:
    `echo {1..9} > gamma/number.txt`
- Copy file `number.txt` sang thư mục `beta`, sau đó đổi tên file thành `numeric.txt`
    ```bash
    cp gamma/number.txt beta/
    mv beta/number.txt beta/numeric.txt
    ```
- Xóa các files và thư mục đã tạo:
    `rm -r alpha beta gamma`


4. Chức năng các câu lệnh:
- df: Hiển thị dung lượng ổ đĩa đã sử dụng của các file system
- lsblk: Liệt kê các thiết bị lưu trữ (block devices)
- du: Kiểm tra dung lượng của thư mục
- fdisk: Hiển thị, quản lý bảng phân vùng
- mount: mount một file system vào hệ thống tệp