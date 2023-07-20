# Table Of Content

- [Table Of Content](#table-of-content)
- [Lệnh WSL Ubuntu](#lệnh-wsl-ubuntu)
  - [1. mkdir](#1-mkdir)
  - [2. rm và rmdir](#2-rm-và-rmdir)
  - [3. cd](#3-cd)
  - [4. touch](#4-touch)
  - [5. vim](#5-vim)
  - [6. cat](#6-cat)
  - [7. echo](#7-echo)
  - [8. tail](#8-tail)
  - [9. grep](#9-grep)
  - [10. cp](#10-cp)
  - [11. mv](#11-mv)
  - [12. rm](#12-rm)
  - [13. rmdir](#13-rmdir)
  - [14. sudo: super user do](#14-sudo-super-user-do)
  - [15. chmod: change mode](#15-chmod-change-mode)
  - [16. chown: change owner](#16-chown-change-owner)
  - [17. man: manual instruction](#17-man-manual-instruction)
  - [18. wget](#18-wget)
  - [19. apt](#19-apt)
  - [20. ps ux, ps aux](#20-ps-ux-ps-aux)
  - [21. kill](#21-kill)
  - [22. ping](#22-ping)
  - [23. uname: unix name](#23-uname-unix-name)
  - [24. pwd](#24-pwd)
  - [25. passwd](#25-passwd)
  - [26. top hoặc htop](#26-top-hoặc-htop)
  - [27. df hoặc df -h](#27-df-hoặc-df--h)
  - [28. free hoặc free -h](#28-free-hoặc-free--h)
  - [29. Tips](#29-tips)

# Lệnh WSL Ubuntu

```
root password: hieu1234
hieu passsword: hieu1234
```

## 1. mkdir

- Tạo thư mục
- Thêm tham số: -p để có thể tạo nhiều thư mục lồng nhau
- VD:

```bash
mkdir -p parent/child1/child2
```

## 2. rm và rmdir

- rmdir chỉ giúp xóa 1 thư mục bị rỗng
- Xóa thư mục và xóa cả thư mục con: `rm -r <tên thư mục>`
- VD:

```bash
rm -r parent
```

## 3. cd

- Change directory
- Đề lùi lại 1 folder: `cd ..`
- Để về folder home/account: `cd`
- Về thư mục root: `cd /`
- Trở về thư mục trước khi ta thực hiện lệnh cd: `cd -`

## 4. touch

- Lệnh tạo ra 1 file trống không có nội dung
- VD:

```bash
touch text.txt
touch main.js
touch index.html
```

## 5. vim

- Lệnh `vim` để vào **VIM Editor** (được cài sẵn trên những OS Unix)
- Lệnh: `:q + Enter` để thoát khỏi vim
- Lệnh: `vim <tên file mới hoặc cũ>` để vào trình editor vim để chỉnh sửa file
  VD:

  ```bash
  vim demo.html
  ```

  - Nếu chưa có file demo.html nào ở folder, thì tạo mới
  - Nếu có thực hiện thêm nội dung cho file demo.html là demo.html sẽ được tạo mới, nếu không có chỉnh sửa thì demo.html sẽ không được tạo mới

- Vào insert mode: `bấm i hoặc bấm a`
- Thoát insert mode: `bấm esc`
- Thoát khỏi vim và không lưu các chỉnh sửa (Thêm ! vào cuối): `:q!`
- Để lưu file: `:w`
- Để lưu file sau đó thoát: `:wq` hoặc `:x`

## 6. cat

- Xem nội dung của 1 file hoặc nhiều file:

```bash
cat <tên file> <tên file> ...
```

VD:

```bash
cat demo.html
cat demo.html test.html
```

- Chú ý:

  - Nội dung sẽ được in ra ngay ở termial, đây gọi là standard output hay stout

  - **_Gộp nội dung nhiều file vào 1 file_**: ở trên ta biết lệnh `cat` sẽ cho đầu ra là stout nên ta có thể đẩy stout này vào 1 file mới
    VD:
    ```bash
    cat demo.html cat.html > concat.html
    ```
    > 1 file mới concat.html sẽ được tạo ra có nội dung được ghép nối từ 2 file demo.html và test.html

## 7. echo

- Cho ra 1 stout từ 1 chuỗi nội dung nhập từ bàn phím

  - VD1: `echo "Hello anh em"` ==> In ra terminal "Hello anh em"

  - VD2: `echo "<h1> Hello echo command </h1>"` > echo.html
    > 1 file echo.html được tạo ra với nội dung vừa nhập

- **Thêm (append) nội dung vào 1 file bằng echo**.

  VD1:

  ```bash
  echo "Hello anh em 1" > text.txt
  echo "Hello anh em 2" > text.txt
  ```

  - Nếu chỉ sử dụng 1 dấu ">" thì nội dung sau sẽ ghi đè nội dung trước. Để append được ta dùng 2 dấu >>

  VD:

  ```bash
  echo "Hello anh em 1" > text.txt
  echo "Hello anh em 2" >> text.txt
  cat text.txt

  # Sẽ in ra:
  # "Hello anh em 1 \n Hello anh em 2"
  ```

## 8. tail

- **Hiện thị phần cuối cùng của file (sử dụng nếu file quá dài)**
- Hoàn toàn có thể kiểm soát số dòng hiển thị ra, sử dụng tham số `-n`:

```bash
tail -n <số dòng> <tên file>
```

VD:

```bash
tail -n 10 text.txt
```

- **Để follow theo 1 cái file đang xảy ra sự thay đổi (ví dụ có 2 tab termial: 1 tab xem file demo.html, 1 tab sử dụng lệnh echo để thêm nội dung cho demo.html)**:

```bash
tail -f <tên file>
```

VD:

> Khi có sự thay đổi của file `demo.html` ở tab thực hiện chỉnh sửa thì tab theo dõi bằng `tail -f` cũng sẽ đồng thời có hiện thị sự chỉnh sửa đó

```bash
tail -f demo.html

```

- Để biết thêm chi tiết: `tail --help`

## 9. grep

- **Để tìm kiếm từ, tìm kiếm bằng regex trong 1 file hoặc nhiều file,... còn nhiều ứng dụng khác nhưng nâng cao hơn nên tra gg**

- VD: _muốn tìm từ "anh em" trong file `demo.html` và `concat.html`_

```bash
cat demo.html concat.html | grep "anh em"
```

## 10. cp

- **_Dùng để copy file và folder_**
- Cú pháp:

```bash
cp <source file location> <target file location>
```

- VD1:

  > Xét trong cùng 1 folder ta muốn copy nội dung của file demo.html vào file new-demo.html (new-demo.html cũng đồng thời được tạo mới)

  ```bash
  cp demo.html new-demo.html
  ```

- VD2:

  > Muốn copy 1 file vào 1 folder khác

  - Nếu ở sau new-folder không có 1 tên file thì mặc định demo.html được copy vào new-folder và giữ nguyên tên

  ```bash
  cp demo.html new-folder/
  ```

  - Nếu ở sau new-folder có 1 tên file thì demo.html được copy vào new-folder với 1 cái tên mới là demo2.html

  ```bash
  cp demo.html new-folder/demo2.html
  ```

- VD3:

  > copy từ 1 file ở folder A sang folder B

  ```bash
  mkdir -p /mnt/d/Workspace/new-folder/new-folder2

  cp /mnt/d/Workspace/demo.html /mnt/d/Workspace/new-folder/new-folder2/new-demo.html
  ```

- VD4:

  > copy 1 thư mục và toàn bộ nội dung của nó vào 1 thư mục khác, sử dụng tham số `-r`:

  ```bash
  cp -r new-folder2 /mnt/d/Workspace/hieucien
  ```

- VD5:
  > 1 số folder bị giới hạn quyền truy cập thì ta phải sử dụng quyền root `sudo`
  ```bash
  sudo cp demo.html /home/
  ```

## 11. mv

- **_mv là viết tắt của move, sử dụng tương tự như cp_**
- Cú pháp:

```bash
mv <source file location> <target folder location>
```

- VD1:

  > Xét trong 1 folder: nếu thực hiện lệnh mv cho 1 file nhưng target location vẫn là folder đó thì chính là ta đang đổi tên cho file

  ```bash
  mv demo.html new-name-demo.html
  ```

- VD2:

  > Di chuyển 1 file vào 1 folder

  ```bash
  mv demo.html new-folder/
  ```

- VD3:

  > Di chuyển 1 file vào 1 folder và đồng thời đổi tên

  ```bash
  mv demo.html new-folder/new-name-demo.html
  ```

- VD4:
  > Di chuyển 1 folder vào 1 folder nhưng không đổi tên
  ```bash
  mv new-folder1 new-folder2
  ```
- VD5:

  > Di chuyển 1 folder vào 1 folder khác và có đổi tên

  ```bash
  mv new-folder1 new-folder2/new-name-folder-1
  ```

## 12. rm

- **_Để xóa 1 file hoặc nhiều file_**

- Cú pháp:

```bash
rm <source file location> <source file location>
```

VD:

```bash
rm demo.html
rm demo.html concat.html
```

## 13. rmdir

- Nếu không có thamm số gì thì chỉ xóa được thư mục trống:

```bash
rmdir <empty folder name>
```

- Muốn xóa toàn bộ nội dùng ở trong folder và cả folder đó:

```bash
rm -r <tên folder>
```

VD:

```bash
rm -r new-folder-4
```

- Nếu gặp permission denied thì lại thêm sudo vào trước:

```bash
sudo rm -r any-folder-name
```

## 14. sudo: super user do

- **_Cung cấp quyền root_**

## 15. chmod: change mode

- **_change mode_**

## 16. chown: change owner

- **_change owner: chuyển chủ sở hữu_**

## 17. man: manual instruction

- **_Tra cứu tài liệu cách sử dụng ngay trong terminal_**

VD: **tra cứu về lệnh tail**

```bash
man tail
```

## 18. wget

- Tải tài nguyên về từ 1 đường dẫn đề tải

VD: **_có đường dẫn tải về của 1 ảnh_**

```bash
wget <đường dẫn>
```

## 19. apt

- **_Là công cụ dòng lệnh để quản lí các thư viện (gói) đang nằm trong ubuntu (tương tự như npm trong node hay chocolate trong window)_**

- VD1:

```bash
sudo apt update # fetch thông tin cần update
apt list --upgradable # xem thông tin có gói có thể upgradable
sudo apt upgrade # pull - thực hiện nâng cấp cập nhật các gói
```

- VD2: _cài đặt 1 gói nào đó_

```bash
sudo apt install nmap
sudo apt remove nmap
```

## 20. ps ux, ps aux

- **Xem các tiến trình đang chạy (tương tự xem task manager trong window), có hiển thị PID là process id**

- Lệnh:

```bash
ps ux

# hoặc

ps aux

# hoặc

ps aux -a
```

## 21. kill

- `kill` 1 tiến trình,nếu tiến trình bị đơ hay bị crash
- Cú pháp:

```bash
kill -<signal option> <PID>
```

- Chú ý:

  - Có tổng cộng 64 signal option nhưng ta hay sử dụng 2 signal option sau đây

    - `SIGNTERM(15)`: thực hiện dừng chương trình và lưu lại tiến trình. Nếu không truyền signal option thì đây là tín hiệu mặc định sẽ được dùng

    - `SIGNKIll(9)`: thực hiện kill ngay lập tức tiến trình và không lưu lại tiến trình

    - VD:

    ```bash
    tail -f random.js # theo dõi file random.js, coi như đây là 1 tiến trình
    ps aux  # theo dõi các tiến trình đang chạy và sẽ thấy random.js, sẽ thấy cả PID: process ID
    # kill -15 <PID của tiến trình của tail -f random.js, ví dụ ở đây là 1273>
    kill -15 1273
    ```

## 22. ping

- Kiểm tra tốc độ kết của từ máy của mình đến 1 máy chủ, 1 server hoặc 1 địa chỉ ip nào đó

- VD:

```bash
ping google.com
ping fullstack.edu.vn
ping oasis.uet.vnu.edu.vn
```

## 23. uname: unix name

- Để xem thông tin về kerel
- Thêm tham số -a để xem chi tiết

VD:

```bash
uname

# hoặc

uname -a
```

## 24. pwd

- Hiện ra địa chỉ đường dẫn hiện tại

## 25. passwd

- Đổi password cho tài khoản hiện tại

## 26. top hoặc htop

- Hiển thị ra và cập nhật liên tục như task manager

- top (đã cũ), htop (mới cập nhật nên có giao diện đẹp hơn)

## 27. df hoặc df -h

- Xem tình trạng ổ đĩa: ổ c, d

## 28. free hoặc free -h

- Kiểm tra về RAM và Swap

## 29. Tips

- Gõ tab để auto complete
- Gõ `ctrl + A` / `ctrl + E` để di chuyển về đầu / cuối dòng lệnh
- Gõ `ctrl + U` để xóa hết nội dung lệnh đứng trước con trỏ
- Gõ `ctrl + `L để xóa hết các lệnh trước đó ( giống clear ) mà vẫn giữ nguyên dòng lệnh đang gõ
- Gõ `ctrl+ C` để kết thúc dòng lệnh đang gõ , không thực thi dòng lệnh đó
- Gõ `command1; command2; ...` để chạy nhiều command , không cần biết command nào bị lỗi khi chạy

  VD:

  ```bash
  echo 1; echo 2; echo 3; echo 4;...
  ```

- Gõ `command1 && command2 &&...` để chạy nhiều command , command trước phải chạy thành công thì command sau mới chạy

  VD:

  ```bash
  mkdir new-folder && touch new-folder/index.js
  ```

- Bôi đen nội dung và chuột phải để copy
