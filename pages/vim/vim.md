# Table Of Content

- [Table Of Content](#table-of-content)
- [VIM](#vim)
  - [1. Thoát VIM](#1-thoát-vim)
  - [2. Vào insert mode](#2-vào-insert-mode)
  - [3. Di chuyển giữa các dòng](#3-di-chuyển-giữa-các-dòng)
  - [4. 1 số setting](#4-1-số-setting)
  - [5. Editing](#5-editing)
  - [6. Xoá](#6-xoá)
  - [7. Sửa đổi 1 chữ trong dòng](#7-sửa-đổi-1-chữ-trong-dòng)
  - [8. Editing khi kết hợp ở trong các dấu "", (), {}, \[\]](#8-editing-khi-kết-hợp-ở-trong-các-dấu----)
  - [9. Vào visual mode, visual line mode](#9-vào-visual-mode-visual-line-mode)
  - [10. Indent](#10-indent)
  - [11. Tìm kiếm](#11-tìm-kiếm)
  - [12. Các mode và command](#12-các-mode-và-command)

# VIM

## 1. Thoát VIM

- Cú pháp: `:q`
- Cú pháp: `:q!` : thêm dấu ! để thoát và không lưu thay đổi
- Cú pháp: `:wq` : thếm w để lưu thay đổi và thoát
- Cú pháp: `:w` : lưu và không thoát

## 2. Vào insert mode

- Cách 1: Bấm `i`: vào `insert mode với con trỏ giữ nguyên vị trí

- Cách 2: Bấm `a`: vào `insert mode với con trỏ dịch sang bên phải 1

- Cách 3: Bấm `o`: vào `insert mode với con trỏ ở 1 dòng mới (phía dưới dòng đặt con trỏ ban đầu)

- Cách 4: Bấm `Shift + i` = `I`: vào insert mode với con trỏ về vị trí đầu dòng

- Cách 5: Bấm `Shift + a` = `A`: vào insert mode với con trỏ về vị trí cuối dòng

- Cách 6: Bấm `Shift + o` = `O`: vào insert mode với con trỏ ở 1 dòng mới (phía trên dòng đặt con trỏ ban đầu)

## 3. Di chuyển giữa các dòng

- Có thể sử dụng các phím sau để thay thế cho các phím điều hướng:
  - `h` ~ mũi tên trái
  - `l` ~ mũi tên phải
  - `k` ~ mũi tên lên
  - `j` ~ mũi tên xuống
- Để di chuyển giữa các dòng, các chữ nên sử dụng `h,j,k,l`
- Khi ở normal mode:

  - VD: Muốn di chuyển 10 kí tự sang trái / phải: `10 h / 10 l`
  - VD: Muốn di chuyển xuống / lên 10 dòng: `10 j / 10 k`

- Khi ở normal mode:
  - Bấm `w` để di chuyển giữa các chữ (nhảy tới chữ cái tiếp theo)
  - Bấm `B` để lùi về 1 chữ cái
  - Bấm `e` để di chuyển đến cuối chữ (hoặc từ cuối chữ này đến cuối chữ tiếp theo)
  - Bấm `0` để di chuyển đến đầu dòng
  - Bấm `$` để về cuối dòng
- Di chuyển giữa các dấu `(), {}, []`: ta sử dụng dấu `%`
- Di chuyển đến 1 chữ cái trong dòng: `tn` hoặc `fn`

  - `tn`: nhảy đến vị trí trước chữ "n" trong dòng
  - `fn`: nhảy đến đúng vị trí của chữ "n" trong dòng
  - `t` và `f` thường sẽ tiến, còn `shift + t` và `shift + f` sẽ lùi
  - `t`, `T` và `f`, `F` là **_jump to next / previous occurence_**

- Di chuyển về đầu file: `gg`
- Di chuyển về cuối file: `G`
- Nhảy đến 1 dòng:

```bash
<linenumber>G
```

VD: nhảy đến dòng 123:

```bash
123G
```

hoặc

```bash
:<số dòng>
```

VD:

```bash
:100
```

## 4. 1 số setting

- Truy cập file setting: `vi ~/.vimrc`
- Sử dụng lệnh `:set number` để hiện thị số dòng

```bash
:set relativenumber
:set tabstop=4
:set shiftwidth=4
colorscheme blue
```

## 5. Editing

- Có thể kết hợp số và các lệnh
  VD:

```
3 + u => 3 lần undo
```

- `undo`: Ở normal mode, bấm `u`
- `redo`: Ở normal Mode, bấm `Ctrl + r`
- Ở normal mode:
  - Bấm `d + d` đế xoá 1 dòng
  - Có thể kết hợp với số `5 d d` => Xoá 5 dòng
  - Bấm `y + y` đế copy 1 dòng
  - Có thể kết hợp với số `4 y y` => Copy 4 dòng
  - Bấm `p` để paste xuống phía dưới, Bấm `shift + p` để paste lên trên
  - Change: bấm `c + c` để xoá dòng hiện tại và vào `insert mode`
  - Bấm `shift + d` để xoá 1 phần (tính từ vị trí con trỏ cho tới hết dòng)
  - Bấm `shift + c`: để xoá 1 phần của dòng và vào insert mode để chỉnh sửa
  - Bấm `shift + y`: để copy cả dòng
  - **_Thay thế 1 chữ_**: (normal mode): đặt con trỏ vào trước chữ cần thay thế, bấm `R` (replace) và bấm 1 chữ mới bất kì

## 6. Xoá

- Ở normal mode:

  - Kết hợp `d` (delete) và `w` / `b`:

    - `dw` để xoá 1 chữ phía trước
    - `d3w` để xoá 3 chữ
    - `db` để xoá 1 chữ lùi,
    - `d10b` để xoá 10 chữ lùi

  - **Nếu con trỏ đang ở giữa chữ**: `dw` chỉ xoá phần còn lại của chữ
  - Nếu muốn xoá hết chữ: `diw` _(delete inner word)_

  - Xoá `d + e`:

    - `e` chỉ đến kí tự cuối cùng của chữ, `w` chỉ đến kí tự đầu tiên của chữ tiếp theo
    - Nếu dùng `dw` hoặc `diw` sẽ xoá hết dấu space
    - Còn dùng `de` hoặc `die` sẽ không xoá hết dấu space

  - `d + 0`: để xoá từ đầu dòng đến chữ cái đứng trước của chữ cái mà con trỏ đang trỏ tới
  - `d + $`: để xoá từ cuối dòng đến vị trí con trỏ

  - `dtn`: Xoá từ vị trí con trỏ cho đến vị trí trược kí tự "n" (không xoá kí tự n) (theo chiều tiến)
  - `dfn`: Xoá từ vị trí con trỏ cho đến vị trí của kí tự "n" (Xoá cả kí tự n) (theo chiều tiến)
  - `dTn`: Xoá từ vị trí con trỏ cho đến vị trí trược kí tự "n" (không xoá kí tự n) (theo chiều lùi)
  - `dFn`: Xoá từ vị trí con trỏ cho đến vị trí của kí tự "n" (Xoá cả kí tự n) (theo chiều lùi)

## 7. Sửa đổi 1 chữ trong dòng

- Nếu đang ở đầu chữ: `cw`
- Nêu đang ở giữa chữ: `ciw`
- Nếu muốn sửa cả 1 dòng: `cc`

## 8. Editing khi kết hợp ở trong các dấu "", (), {}, []

- TH1: Đang ở giữa
  VD:

  ```txt
  print("This is my stupid message");
  ```

  - Muốn thao tác nội dung trong "":

    - `di"`: xoá trong ""
    - `ci"`: thay đổi nội dung trong ""
    - `yi"`: copy nội dung trong ""

  - Tương tự với các dấu: (), {}, []

- TH2: Con trỏ ngay tại vị trí dấu `(), {}, []`
  - Di chuyển giữa các dấu bằng `%`
  - `d%`: xoá tất cả nội dung giữa 2 dấu và cũng xoá luôn 2 dấu

## 9. Vào visual mode, visual line mode

- Bấm `v` đề vào visual mode
- Select vùng được chọn bằng nút điều hướng `h,j,k,l`
- Sau khi chọn xong: bấm `d` để xoá vùng được chọn
- Bấm `y` (yanking) để copy vùng được chọn và sau đó ra chỗ muốn paste, bấm `p` để paste
- Change: bấm `c`: để xoá vùng được chọn và vào `insert mode` để chỉnh sửa vùng đó

- Bấm `shift + v` để vào visual line mode

## 10. Indent

- Ở normal mode:
  - Để lùi vào / lùi lại 1 tab: `shift + > + >` / `shift + < + <`
- Autoindent:
  - Ở normal mode: `bấm = + + (2 lần =)` để auto indent (căn chỉnh, thụt lề)
  - Ở visual line mode: chọn các dòng cần indent lại và bấm =
- **_Autoindent cả file_**: `gg=G`

## 11. Tìm kiếm

- Nhập

```bash
/<Từ muốn tìm kiếm>
```

- Bấm `n` để di chuyển đến matching tiếp theo
- Bấm `shift + N` để quay lại
- VD: `/index` (tìm kiếm từ index)

## 12. Các mode và command

1. Khi mới vào vim ta sẽ ở normal mode (Không thể edit văn bản), các phím đều là các phím chức năng (không để soạn thảo văn bản)
2. Các lệnh bắt đầu bằng dấu 2 chấm (colon) `:<command>` (VD: `:q`) là các lệnh trong editor

   - (Bấm `:` (colon) để bắt đầu các lệnh trong editor)

3. Các lệnh bắt đầu bằng dấu `!` `:!<command>` là các lệnh terminal
4. Bấm `i` để **vào chế độ soạn thảo** (insert mode) và **thoát insert mode** bằng nút `esc`
