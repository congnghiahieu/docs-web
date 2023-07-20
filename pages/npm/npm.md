# Table Of Content

- [Table Of Content](#table-of-content)
- [1. NPM (Node package manager)](#1-npm-node-package-manager)
  - [1.1 Project scope (phạm vi chỉ nằm trong folder / project)](#11-project-scope-phạm-vi-chỉ-nằm-trong-folder--project)
  - [1.2 Global scope (thêm tham số -g)](#12-global-scope-thêm-tham-số--g)
- [2. NPX (npm package executor)](#2-npx-npm-package-executor)
  - [2.1 **_So sánh sử dụng create-react-app theo kiểu local npm và npx_**:](#21-so-sánh-sử-dụng-create-react-app-theo-kiểu-local-npm-và-npx)
- [3. YARN (Yet Another Resource Negotiator)](#3-yarn-yet-another-resource-negotiator)

# 1. NPM (Node package manager)

## 1.1 Project scope (phạm vi chỉ nằm trong folder / project)

- Các thư viện mà code trong project phải sử dụng đến hay phụ thuộc vào gọi là dependencies (các phụ thuộc)

- VD: react react-dom, các thư viện này phải cài đặt là project scope vì project cần sử dụng đến nó

```
- npm install react react-dom => dependencies
- npm i react react-dom => dependencies

- npm install react react-dom --save-dev => devDependencies
- npm i react react-dom -D => devDependencies

- npm uninstall react react-dom
```

## 1.2 Global scope (thêm tham số -g)

- Các thư viện mà code trong project không phụ thuộc vào sẽ được cài đặt ở global scope, nhưng tất cả các project trong máy của bạn có thể sử dụng đến thư viện này

- VD: create-react-app để tạo ra 1 react project
- Các thư viện ở global scope sẽ được lưu vào folder chuyên chứa các các thư viện kiểu này ở trên máy của bạn
- Kiểm tra các thư viện global scope có ở local:

```
Window + R
nhập: %Appdata%/npm
```

```
- npm install --global create-react-app
- npm i -g create-react-app

- npm uninstall -g create-react-app
```

# 2. NPX (npm package executor)

- Giúp thực thi thư viện mà không cần cài đặt thư viện ở local

  - Trong trường hợp này ta không nói đến các thư viện project scope mà code trong project phụ thuộc vào

- Ta xét trường hợp create-react-app:

  - create-react-app có thể được install về máy ở global scope:

  ```bash
  npm install -g create-react-app
  ```

  - Nhưng đôi khi ta không cần create-react-app ở máy local mãi mãi, ta chỉ cần thư viện create-react-app khi ta cần tạo ra 1 react project (tức là ta chỉ cần create-react-app khi cần tạo react-project)

- Lệnh:

  ```bash
  npx create-react-app my-project-name
  ```

  Sẽ thực hiện các bước sau:

  - Bước 1: Kiểm tra xem ở project scope (_trong trường hợp này ta không cài đặt create-react-app ở project scope vì nó không phải là dependencies_) và global scope (_ta cũng không cài đặt và lưu create-react-app ở local_) nếu không có thư viện create-react-app thì sẽ tải nó về thực hiện tạo ra 1 project react mới

  - Bước 2: Sau khi project react mới được tạo ra thành công, tiến hành xóa thư viện create-react-app
    - Vậy mục đích của npx là để sử dụng các thư viện theo kiểu temporary (tạm thời) dùng 1 lần xong xóa luôn, không có nhu cầu lưu trữ lâu dài trong local

## 2.1 **_So sánh sử dụng create-react-app theo kiểu local npm và npx_**:

- Local: Thư viện create-react-app sẽ được lưu trữ trong local, bất lợi của việc này là create-react-app ở local của bạn có thể là phiên bản cũ nếu bạn không để ý cập nhật sau 1 thời gian

```bash
  npm install --global create-react-app
  create-react-app my-react-project
```

- Npx: (Xét không có thư viện create-react-app ở trong project scope và global scope), tiến hành tải thư viện create-react-app phiên bản mới nhất từ npm registry và tạo ra react project mới, sau khi tạo xong react project thì xóa thư viện create-react-app (kiểu thư viện dùng 1 lần)

```bash
  npx create-react-app my-react-project
```

# 3. YARN (Yet Another Resource Negotiator)

**_YARN tương tự như NPM_**

- `YARN` được phát hành bởi Facebook
