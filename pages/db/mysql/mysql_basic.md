# Table Of Content

- [Table Of Content](#table-of-content)
- [Bài 1: Tạo, xem và xoá Database](#bài-1-tạo-xem-và-xoá-database)
  <details>
  <summary>More</summary>

  - [1.1 Tạo Database](#11-tạo-database)
  - [1.2 Xoá Databse](#12-xoá-databse)
  - [1.3 Xem các database hiện có trong server](#13-xem-các-database-hiện-có-trong-server)
  - [1.4 Chọn CSDL để làm việc](#14-chọn-csdl-để-làm-việc)
  - [1.5 Xem các bảng trong 1 database](#15-xem-các-bảng-trong-1-database)

  </details>

- [Bài 2: Các kiểu dữ liệu. Tạo và sửa đổi cấu trúc bảng](#bài-2-các-kiểu-dữ-liệu-tạo-và-sửa-đổi-cấu-trúc-bảng)
  <details>
    <summary>More</summary>

  - [2.1 Tạo bảng cơ sở dữ liệu](#21-tạo-bảng-cơ-sở-dữ-liệu)
  - [2.1.1 Khóa chính - PK](#211-khóa-chính---pk)
    - [2.1.1.1 Các ràng buộc: `Primary Key`, `Foreign Key`, `Default`, `Not Null`, `Unique, Check`](#2111-các-ràng-buộc-primary-key-foreign-key-default-not-null-unique-check)
    - [2.1.1.2 Khai báo ràng buộc theo cột, theo bảng, đặt tên cho ràng buộc khóa chính và khóa ngoài](#2112-khai-báo-ràng-buộc-theo-cột-theo-bảng-đặt-tên-cho-ràng-buộc-khóa-chính-và-khóa-ngoài)
  - [2.1.2 Khóa ngoài - FK](#212-khóa-ngoài---fk)
  - [2.1.3 Ví dụ về Check, Null, Default](#213-ví-dụ-về-check-null-default)
  - [2.1.4 Xem mô tả của bảng](#214-xem-mô-tả-của-bảng)
  - [2.2 Bổ sung khóa bằng lệnh Alter table và xóa bảng](#22-bổ-sung-khóa-bằng-lệnh-alter-table-và-xóa-bảng)
    - [2.2.1 Alter table](#221-alter-table)
    - [2.2.2 Xóa bảng](#222-xóa-bảng)
  - [2.3 Chèn dữ liệu vào bảng](#23-chèn-dữ-liệu-vào-bảng)
    - [2.3.1 Insert](#231-insert)

  </details>

- [Bài 3: Xử lý ngày tháng năm thời gian](#bài-3-xử-lý-ngày-tháng-năm-thời-gian)
  <details>
  <summary>More</summary>

  - [3.1 `YEAR()`](#31-year)
  - [3.2 `MONTH()`](#32-month)
  - [3.3 `DAY()`](#33-day)
  - [3.4 `NOW()`: **_ngày hiện tại dạng yyyy-mm-dd hh:mm:ss_**](#34-now-ngày-hiện-tại-dạng-yyyy-mm-dd-hhmmss)
  - [3.5 `CURDATE()`: **_ngày hiện tại dạng yyyy-mm-dd_**](#35-curdate-ngày-hiện-tại-dạng-yyyy-mm-dd)
  - [3.6 `DATEDIFF()`](#36-datediff)
  - [3.7 `ADDDATE()`](#37-adddate)
  - [3.8 `EXTRACT()`](#38-extract)

  </details>

- [Bài 4: Sử dụng câu lệnh truy vấn - P1: SELECT, FROM, WHERE, SELECT DISTINCT, ORDER BY, LIMIT, YEAR(), MONTH(), DAY(), AND, OR, BETWEEN, NOW(), CURDATE()](#bài-4-sử-dụng-câu-lệnh-truy-vấn---p1-select-from-where-select-distinct-order-by-limit-year-month-day-and-or-between-now-curdate)

  <details>
  <summary>More</summary>

  - [4.1 Tổng hợp cơ bản các câu truy vấn](#41-tổng-hợp-cơ-bản-các-câu-truy-vấn)
  - [4.2 Select From Where](#42-select-from-where)

  </details>

- [Bài 5: Câu lệnh truy vấn cơ bản - P2: IN, BETWEEN, UNION, LIKE, ORDER BY, Thuộc tính suy diễn](#bài-5-câu-lệnh-truy-vấn-cơ-bản---p2-in-between-union-like-order-by-thuộc-tính-suy-diễn)
    <details>
  <summary>More</summary>

  - [5.1 Toán tử `IN` và `NOT IN`](#51-toán-tử-in-và-not-in)
  - [5.2 Toán tử `BETWEEN` và `NOT BETWEEN`](#52-toán-tử-between-và-not-between)
  - [5.3 Toán tử `LIKE` và `NOT LIKE`, `LEFT(string, length)` và `RIGHT(string, length)`](#53-toán-tử-like-và-not-like-leftstring-length-và-rightstring-length)
  - [5.4 Thuộc tính suy diễn được (Derived Attribute)](#54-thuộc-tính-suy-diễn-được-derived-attribute)
  - [5.5 `ORDER BY`](#55-order-by)
  - [5.6 Kết hợp các kết quả với toán tử `UNION` - Tương đương toán tử hợp trong đại số quan hệ](#56-kết-hợp-các-kết-quả-với-toán-tử-union---tương-đương-toán-tử-hợp-trong-đại-số-quan-hệ)

  </details>

- [Bài 6: Substring(), Concat(), Replace(), If(), Last_insert_id, DateDiff(), AddDate(), Extract()](#bài-6-substring-concat-replace-if-last_insert_id-datediff-adddate-extract)
    <details>
  <summary>More</summary>

  - [6.1 Hàm `Substring()`](#61-hàm-substring)
  - [6.2 Hàm `Concat()`](#62-hàm-concat)
  - [6.3 Hàm `Replace()`](#63-hàm-replace)
  - [6.4 Hàm `If()`](#64-hàm-if)
  - [6.5 Hàm `LAST_INSERT_ID`](#65-hàm-last_insert_id)
  - [6.6 `DATEDIFF`](#66-datediff)
  - [6.7 `ADDDATE`](#67-adddate)
  - [6.8 `EXTRACT()`](#68-extract)

  </details>

- [Bài 7: Truy vấn nhóm](#bài-7-truy-vấn-nhóm)
  <details>
  <summary>More</summary>

  - [7.1 Hàm nhóm: `Sum()`, `Avg()`, `Min()`, `Max()`, `Count()`](#71-hàm-nhóm-sum-avg-min-max-count)
    - [7.1.1 Hàm `SUM`](#711-hàm-sum)
    - [7.1.2 Hàm `AVG`](#712-hàm-avg)
    - [7.1.3 Hàm `MAX` và `MIN`](#713-hàm-max-và-min)
    - [7.1.4 Hàm `COUNT`](#714-hàm-count)
  - [7.2 Mệnh đề nhóm `GROUP BY`](#72-mệnh-đề-nhóm-group-by)
  - [7.3 Mệnh đề điều kiện `HAVING`](#73-mệnh-đề-điều-kiện-having)

  </details>

- [Bài 8: INNER JOIN, LEFT JOIN, RIGHT JOIN, SELF JOIN](#bài-8-inner-join-left-join-right-join-self-join)
- [Bài 9: Truy vấn con](#bài-9-truy-vấn-con)

# Bài 1: Tạo, xem và xoá Database

## 1.1 Tạo Database

```sql
CREATE DATABASE {your_database_name}
```

hoặc

```sql
CREATE DATABASE IF NOT EXISTS {your_database_name}
```

## 1.2 Xoá Databse

```sql
DROP DATABASE {your_database_name}
```

hoặc

```sql
DROP DATABASE IF EXISTS {your_database_name}
```

## 1.3 Xem các database hiện có trong server

```sql
SHOW DATABASE
```

## 1.4 Chọn CSDL để làm việc

```sql
USE {your_database_name}
```

## 1.5 Xem các bảng trong 1 database

```sql
USE {database_name}

SHOW TABLES
```

# Bài 2: Các kiểu dữ liệu. Tạo và sửa đổi cấu trúc bảng

## 2.1 Tạo bảng cơ sở dữ liệu

### 2.1.1 Khóa chính - PK

```sql
CREATE TABLE IF NOT EXISTS {table_name} (
{column_name} {data_type} {default_value} {column_constraints},
...
{table constraints}
...
) type=table_type
```

#### 2.1.1.1 Các ràng buộc: `Primary Key`, `Foreign Key`, `Default`, `Not Null`, `Unique, Check`

- `Primary Key`: các giá trị trong cột này là phân biệt và không được null
- `Not null`: giá trị của cột không được null
- `Unique`: giá trị của cột là phân biệt và chấp nhận có 1 giá trị là null
- `Check`: Kiểm tra xem dữ liệu đầu vào có thỏa mãn điều kiên nào không
- Chú ý:

  - `column_constraints` là ràng buộc áp dụng cho 1 cột cụ thể
  - `table_constraints` được khai báo tách rời, có thể áp dụng cho 1 cột hoặc nhiều cột

#### 2.1.1.2 Khai báo ràng buộc theo cột, theo bảng, đặt tên cho ràng buộc khóa chính và khóa ngoài

- `Mức cột`:

```sql
{column_name} {data_type} {default_value} CONSTRAINT {constraint_name} {constraint_type}
```

Example:

```sql
employeeNumber int(11) NOT NULL PRIMARY KEY
```

- Mức bảng:

```sql
CONSTRAINT {constraint_name} {constraint_type} (column_name_1,column_name_2,...)
```

### 2.1.2 Khóa ngoài - FK

- Cú pháp khai báo đầy đủ:

```sql
  CREATE TABLE child_table
  (
  column1 datatype [ NULL | NOT NULL ],
  column2 datatype [ NULL | NOT NULL ],
  ...

  CONSTRAINT fk_name
  FOREIGN KEY (child_col1, child_col2, ... child_col_n)
  REFERENCES parent_table (parent_col1, parent_col2, ... parent_col_n)
  [ ON DELETE { NO ACTION | CASCADE | SET NULL | SET DEFAULT } ]
  [ ON UPDATE { NO ACTION | CASCADE | SET NULL | SET DEFAULT } ]
  );
```

VD1:

```sql
CREATE TABLE country (
country_id SMALLINT UNSIGNED NOT NULL AUTO_INCREMENT,
PRIMARY KEY(country_id),
country VARCHAR(50) NOT NULL,
last_update TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP
ON UPDATE CURRENT_TIMESTAMP
);
```

```sql
CREATE TABLE city (
city_id SMALLINT UNSIGNED NOT NULL AUTO_INCREMENT,
PRIMARY KEY(city_id),
city VARCHAR(50) NOT NULL,
country_id SMALLINT UNSIGNED NOT NULL,
last_update TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP
ON UPDATE CURRENT_TIMESTAMP,
CONSTRAINT fk_city_country FOREIGN KEY (country_id) REFERENCES country (country_id)
-- cột được tham chiếu này phải là PK hoặc cột có ràng buộc Unique ---
ON DELETE RESTRICT ON UPDATE CASCADE
);
```

- Chú ý: **Ý nghĩa dòng tùy chọn đi kèm:**

  - `ON DELETE RESTRICT`: có nghĩa không cho phép xóa dòng dữ liệu ở bảng được tham chiếu khi còn dữ liệu tham chiếu tới. Trong ví dụ trên không được phép xóa dòng dữ liệu của bảng country nếu tồn tại dòng dữ liệu từ bảng city tham chiếu tới.
  - `ON UPDATE CASCADE`: có nghĩa khi cập nhật dữ liệu ở bảng được tham chiếu, dữ liệu bên bảng tham chiếu sẽ được tự động cập nhật. Trong ví dụ trên, khi thay đổi dữ liệu của cột country_id của bảng country thì cột country_id của bảng city sẽ được tự động cập nhật.
  - **_Khi không sử dụng các tùy chọn này, ngầm định RESTRICT sẽ được sử dụng cho các sự kiện DELETE và UPDATE._**

### 2.1.3 Ví dụ về Check, Null, Default

- VD1: `Check`

```sql
CREATE DATABASE khachhang;
USE khachhang;
CREATE TABLE nguoidung (
ID int NOT NULL,
HoVaTen varchar(255) NOT NULL,
Tuoi int,
Check(Tuoi >= 18)
);
```

- VD2: Ví dụ về `Default`

```sql
USE Example;
CREATE TABLE student(
ID int NOT NULL,
full_name varchar(30) NOT NULL,
birth date NOT NULL DEFAULT ('1997-01-07'),
address varchar(30)
);
Insert với giá trị default --
INSERT INTO student (ID, full_name, address) values
(21020540, 'Cong Nghia Hieu', 'Ha Noi');
```

### 2.1.4 Xem mô tả của bảng

```sql
DESCRIBE {table_name}
```

```sql
Hiện thị các câu lệnh được sử dụng để tạo bảng --
SHOW CREATE TABLE {table_name}
```

## 2.2 Bổ sung khóa bằng lệnh Alter table và xóa bảng

### 2.2.1 Alter table

- Cú pháp:

```sql
ALTER TABLE table_name tùy chọn[, tùy chọn...] --
Các tùy chọn --
ADD [COLUMN] <column_definition>
MODIFY [COLUMN] <create_definition>
DROP [COLUMN] <column_name>
ADD <table_constraint>
DROP <constraint_name>
```

- VD1: **_Thêm cột salary có kiểu INT, không vượt quá 10 chữ số, ràng buộc "NOT NULL" vào bảng dữ liệu employees_**

```sql
ALTER TABLE employees ADD salary INT(10) NOT NULL
```

- VD2: **_Sửa kiểu của cột salary thành kiểu decimal(15,2)_**

```sql
ALTER TABLE employees MODIFY salary decimal(15,2);
```

- VD3: **_Xóa cột officeCode khỏi bảng employees_**

```sql
ALTER TABLE employees DROP officeCode
```

- VD4: **_Bổ sung khóa chính_**

```sql
CREATE TABLE Persons (
ID int NOT NULL,
LastName varchar(255) NOT NULL,
FirstName varchar(255),
Age int
);
ALTER TABLE Persons ADD PRIMARY KEY (ID, LastName);
ALTER TABLE Persons ADD CONSTRAINT PK_Person PRIMARY KEY (ID,LastName); Bổ sung tên --
```

- VD5: **_Bổ sung khóa phụ. Bảng mẹ là bảng Persons còn bảng con là bảng Orders_**

```sql
CREATE TABLE Orders (
OrderID int NOT NULL,
OrderNumber int NOT NULL,
PersonID int,
PRIMARY KEY (OrderID)
);
ALTER TABLE Orders ADD FOREIGN KEY (PersonID) REFERENCES Persons(ID);
ALTER TABLE Orders ADD CONSTRAINT FK_PersonOrder FOREIGN KEY (PersonID) REFERENCES Persons(ID);
FK của bảng này khi tham chiếu tới PK của bảng kia ko nhất thiết phải đặt trên hai cột trùng tên, chỉ
cần giống kiểu dữ liệu
Nếu như ko muốn đặt tên chỉ cần bỏ cụm từ CONSTRAINT FK_PersonOrder đi
```

### 2.2.2 Xóa bảng

```sql
DROP TABLE IF EXISTS {table_name}
```

## 2.3 Chèn dữ liệu vào bảng

### 2.3.1 Insert

- Cú pháp:

```sql
USE {database_name}
INSERT INTO {table_name}
(...),
...
();
```

VD1:

```sql
Create Database Phong1234;
Use Phong1234;
Create Table Nguoidan (
Hovaten char(40),
Ngaysinh date,
Gioitinh char(10),
SĐT int);
Insert Into NguoiDan values
('Nguyen Phuong Thao', '1994-02-17', 'Nu', 0987345679),
('Nguyen Ngoc Quynh', '1997-01-07', 'Nu', 0305768901);
```

# Bài 3: Xử lý ngày tháng năm thời gian

## 3.1 `YEAR()`

```sql
  SELECT YEAR('2021-03-07 12:18:15'); kết quả ra 2021 --
  SELECT YEAR('2021-03-07'); kết quả ra 2021 --
```

## 3.2 `MONTH()`

```sql
SELECT MONTH('2021-03-07 12:18:15'); kết quả ra 3 --
SELECT MONTH('2021-03-07'); kết quả ra 3 --
```

## 3.3 `DAY()`

```sql
SELECT DAY('2021-03-07 12:18:15'); kết quả ra 7
SELECT DAY('2021-03-07'); kết quả ra 7
```

## 3.4 `NOW()`: **_ngày hiện tại dạng yyyy-mm-dd hh:mm:ss_**

```sql
SELECT NOW(); --kết quả: 2021-03-07 00:34:29 --
```

## 3.5 `CURDATE()`: **_ngày hiện tại dạng yyyy-mm-dd_**

```sql
SELECT CURDATE(); --kết quả: 2021-03-07
```

## 3.6 `DATEDIFF()`

- Mô tả: _Hàm DATEDIFF trả về chênh lệch giữa hai giá trị thời gian dựa trên mốc thời gian được chỉ định là `expr1` và `expr2`. Hai giá trị thời gian phải là ngày hoặc các biểu thức ngày và giờ dưới dạng date hoặc datetime._
- Cú pháp:

```sql
DATEIFF(expr1, expr2) expr1 và expr2 là 2 mốc thời gian --
```

Ví dụ 1:

```sql
SELECT DATEDIFF('2011-08-17','2011-08-17'); --Trả về 0 ngày --
SELECT DATEDIFF('2011-08-17','2011-08-08'); --Trả về 9 ngày --
SELECT DATEDIFF('2011-08-08','2011-08-17'); --Trả về -9 ngày --
```

Ví dụ 2: **_Để tính toán số ngày còn lại giữa ngày vận chuyển và ngày yêu cầu để trong đơn đặt hàng, chúng ta sử dụng DATEDIFF_**:

```sql
USE classicmodels;
SELECT orderNumber, DATEDIFF(requiredDate,shippedDate) AS daysLeft
Do ngày yêu cầu diễn ra sau ngày vẫn chuyển, cho nên khi ta viết requireDate trước shippedDate --
thì kết quả sẽ ra số dương --
FROM orders
ORDER BY daysLeft DESC; Lệnh sắp xếp giảm dần --
```

## 3.7 `ADDDATE()`

- Mô tả hàm `ADDATE`: **_trả về giá trị thời gian mới khi nó được cộng thêm
  một khoảng thời gian được chỉ định._**

- Cú pháp 1:

```sql
ADDDATE(expr, day)
expr: khoảng thời gian ta muốn thay đổi. --
day: một số nguyên ngày ta muốn thêm vào biểu thức expr. --
```

- Cú pháp 2:

```sql
ADDDATE(date, INTERVAL expr unit)
date: ngày mà khoảng thời gian được thêm vào. --
value: giá trị của khoảng thời gian / ngày mà ta muốn thêm. Ta cũng có thể chỉ định giá trị dương và âm cho tham số này.--
unit: loại đơn vị của khoảng thời gian như ngày (day), giờ (hour), tháng (month), phút (minute), tuần (week) --
```

Ví dụ 1: **_Thêm một khoảng thời gian nhất định, sử dụng cú pháp `ADDDATE(expr, day)`_**

```sql
SELECT ADDDATE('2020-04-16', 28);
Kết quả sẽ ra là 2020-05-14, ngày cũ được cộng thêm 28 ngày --
```

Ví dụ 2: **_Đưa ra ngày tháng sau ngày giờ hiện tại là 30 ngày, sử dụng cú pháp ADDDATE(date, INTERVAL expr unit)_**

```sql
SELECT ADDDATE(NOW(), INTERVAL 30 day);
Kết quả khi chạy là '2021-04-04 00:28:30'- thời gian hiện tại của máy tính --
```

```sql
SELECT ADDDATE('2020-04-16', interval 28 day)
Cho ra kết quả giống ví dụ 1 --
```

Ví dụ 3: **_Đưa ra các đơn đặt hàng trong khoảng 30 ngày tính từ ngày 1/5/2005, sử dụng cú pháp `ADDDATE(date, INTERVAL expr unit)`_**

> Do các đơn đặt hàng được tính từ ngày 1/5/2005 trở đi cho nên orderDate phải lớn hơn hoặc bằng 1/5/2005 và nhỏ hơn mốc 1/5/2005 cộng thêm với 30 ngày. Ta sử dụng cú pháp `ADDDATE(date, INTERVAL expr unit)` để tính thêm mốc cộng thêm đó.

```sql
USE classicmodels;
SELECT *
FROM orders
WHERE orderDate>= '2005-5-1' AND orderDate < ADDDATE('2005-5-1', INTERVAL 30 DAY);
```

Ví dụ 4: **_Đưa ra các đơn đặt hàng tính từ trước ngày 1/5/2005 30 ngày (câu hỏi trong giáo trình hơi dễ nhầm)_**

> Do đơn đặt hàng được tính từ trước ngày 1/5/2005 cho nên orderDate phải nhỏ hơn hoặc bằng 1/5/2005 và lớn hơn mốc 1/5/2005 trừ đi 30 ngày

```sql
SELECT *
FROM orders
WHERE orderDate<= '2005-5-1' AND orderDate > ADDDATE('2005-5-1', INTERVAL -30 DAY);
```

Hoặc viết lại như sau:

```sql
SELECT *
FROM orders
WHERE orderDate<= '2005-5-1' AND orderDate > ADDDATE('2005-5-1', INTERVAL -1 MONTH);
```

> Nếu như ví dụ 1 và ví dụ 2 có thể viết giống nhau (bỏ đi interval và chỉ thêm số ngày) thì ở ví dụ này không thể viết như thế được. Ta bắt buộc phải thêm interval.

## 3.8 `EXTRACT()`

- Mô tả hàm `EXTRACT`: **_tách ra các giá trị như ngày, tháng, năm từ một giá trị có kiểu thời gian._**
- Cú pháp:

```sql
EXTRACT( unit FROM date )
unit: loại đơn vị của khoảng thời gian như ngày(day), giờ (hour) tháng (month), phút (minute), tuần (week). --
date: giá trị ngày hoặc ngày giờ để trích xuất --
```

Ví dụ 1: **_Đưa ra tháng của một giá trị thời gian, sử dụng cú pháp `EXTRACT( unit FROM date )`_**:

```sql
SELECT EXTRACT(MONTH FROM '2004-12-31 23:59:59');
Kết quả trả về là tháng 12 --
```

Hoặc cũng có thể viết để ra kết quả tương tự:

```sql
SELECT MONTH('2004-12-31 23:59:59');
```

Hoặc cũng có thể đưa ra năm của một giá trị thời gian

```sql
SELECT EXTRACT(YEAR FROM '2004-12-31 23:59:59');
Kết quả trả về là năm 2004 --
```

Ví dụ 2: **_Đưa ra tuần của một giá trị thời gian, sử dụng cú pháp EXTRACT( unit FROM date )_**:

```sql
SELECT EXTRACT(WEEK FROM '2021-03-05 23:59:59');
Kết quả ra 9, nghĩa là từ ngày 5 tháng 3 năm 2021 trở về trước đã trôi qua 9 tuần --
```

> _Nếu ta tăng ngày 5 lên khoảng 7 ngày thì số tuần sẽ là 10_

Ví dụ 3: **_Đưa ra các đơn hàng đặt năm 2005, sử dụng cú pháp `EXTRACT( unit FROM date )` kết hợp với điều kiện `Where`_**

```sql
SELECT *
FROM orders
WHERE EXTRACT(YEAR FROM orderDate) = 2005;
```

Ví dụ 4: **_Đưa ra các đơn hàng đặt trong tháng 5 năm 2005_**

```sql
SELECT *
FROM orders
WHERE EXTRACT(YEAR FROM orderDate) = 2005 and EXTRACT(MONTH FROM orderDate) = 5;
```

Nếu muốn dùng hàm ADDDATE như phần **a**, tả phải viểt là:

```sql
SELECT *
FROM orders
WHERE orderDate>= '2005-5-1' AND orderDate <= ADDDATE('2005-5-1', INTERVAL 30 DAY);
```

> Cách viết trên giống với ví dụ 3 phần a nhưng ADDDATE được để là <= thay vì <, cho nên nếu ở ví dụ 3 phần 3, orderNumber chỉ tới số 10423 (do dừng ở ngày 30) nhưng ở đây orderNumber sẽ tới số 10425 (do dừng ở ngày 31, tháng 5 có 31 ngày).

# Bài 4: Sử dụng câu lệnh truy vấn - P1: SELECT, FROM, WHERE, SELECT DISTINCT, ORDER BY, LIMIT, YEAR(), MONTH(), DAY(), AND, OR, BETWEEN, NOW(), CURDATE()

## 4.1 Tổng hợp cơ bản các câu truy vấn

1. **_Chọn các cột nào_**

```sql
SELECT {column_name_1} {column_name_2} ...
SELECT *
```

2. **_Từ bảng nào_**

```sql
FROM {table_name}
```

3. **_Với điều kiện nào_**

```sql
WHERE {condition}
```

4. `DISTINCT`: **_Loại bỏ các dữ liệu kết quả trùng lặp_**

```sql
SELECT DISTINCT {column_name}
FROM {table}
WHERE ...
```

5. **_Giới hạn các bản ghi trả về_**

```sql
LIMIT {number}
```

6. **_Sắp xếp kết quả trả về theo thứ tự tăng dần / giảm dần của cột nào_**

```sql
ORDER BY {column_name} ASC / DESC
```

7. **_Toán tử `AND` và `OR` ở phần điều kiện của câu lệnh `WHERE`_**

```sql
VD: WHERE {column_1} = {value_1} AND / OR {column_2} = {value_2}
```

## 4.2 Select From Where

1. Thứ tự truy vấn

```sql
SELECT tên cột 1, tên cột 2, ...
FROM các bảng
[WHERE điều kiện chọn]
[GROUP BY nhóm]
[HAVING điều kiện chọn nhóm]
[ORDER BY các cột sắp xếp] ASC DESC
[LIMIT giới hạn số lượng];
```

2. Toán tử điều kiện `AND`, `OR`, `BETWEEN`

Ví dụ 7: **_Đưa ra các khách hàng tại Mỹ của người chăm sóc khách hàng có mã là 1165_**

```sql
SELECT *
FROM customers
WHERE country ='USA' and salesRepEmployeeNumber = 1165;
```

Ví dụ 8: **_Đưa ra các đơn hàng có trạng thái là 'On Hold' (tạm ngừng) hoặc 'In Process' (đang tiến hành)_**

```sql
SELECT *
FROM orders
WHERE status = 'On Hold' or status ='In Process' or status = "Shipped";
```

> `BETWEEN` thay cho a >= b AND a <= c

```sql
SELECT *
FROM orders
WHERE orderDate BETWEEN '2005/04/01' AND '2005/04/30' AND status = 'Shipped';
```

3. `IS NULL`: **_tìm giá trị không xác định_**

Ví dụ 9: **_Đưa ra các khách hàng chưa được gán nhân viên chăm sóc_**

```sql
SELECT customerName, salesRepEmployeeNumber
FROM customers
WHERE salesRepEmployeeNumber is NULL; #(không được viết là = Null)
```

4. `DISTINCT`

Ví dụ 10: **_Để tìm thấy bao nhiêu vị trí công việc của tất cả các nhân viên_**

```sql
SELECT DISTINCT jobTitle #(thử bỏ distinct để thấy sự khác biệt)
FROM Employees;
```

Ví dụ 11: **_Tìm ra mã số các sản phẩm đã được mua bằng truy vấn_**

```sql
SELECT DISTINCT productCode
FROM OrderDetails;
```

5. `LIMIT` và `ORDER BY`

- Cú pháp:

```sql
LIMIT {index của hàng bắt đầu},{số lượng hàng muốn lấy}
```

Chú ý:

- index được bắt đầu từ 0, số lượng hàng muốn lấy bao gồm cả hàng bắt đầu

```sql
LIMIT 9,10
```

- Tức là bắt đầu từ hàng có index là 9 (tương đương hàng thứ 10 nếu ta đếm từ 1), lấy tổng cộng 10 hàng (bao gồm cả hàng có index là 9) vậy ta sẽ lấy đến hàng có index là 18 (18 - 9 + 1 = 10);

- Cú pháp:

```sql
ORDER BY {column_name} ASC / DESC
```

Ví dụ 12: **_Lấy ra thông tin về tên của 5 sản phẩm đầu tiên trong bảng Product_**

```sql
SELECT productName
FROM Products
LIMIT 5;
Có thể viết là Limit 0,5 --
Lệnh Limit này lấy ra 5 dòng đầu tiên, vị trí đầu tiên được bắt đầu với 0. --
```

> **_Lấy ra thông tin về 5 sản phẩm đầu tính từ hàng thứ 1, chạy thử để thấy sự khác biệt với ví dụ 12_**

```sql
SELECT productName
FROM Products
LIMIT 1,5;
```

Ví dụ 13: **_Lấy ra thông tin về 10 khách hàng đầu tiên hiện đang ở Pháp_**

```sql
SELECT *
FROM customers
WHERE country = "France"
Limit 10;
```

> **_Nếu như muốn lấy dòng cuối cùng, vẫn dùng lệnh Limit và kết hợp lệnh sắp xếp Order By Desc_**

```sql
SELECT *
FROM customers
WHERE country = "France"
ORDER BY customerNumber DESC
Limit 10;
```

Ví dụ 13-1: **_Ví dụ ta muốn lấy 10 dòng cuối cùng_**

```sql
SELECT *
FROM customers
ORDER BY customerNumber DESC
LIMIT 10;
```

> Hoặc là sử dụng hàm COUNT kết hợp `*` để đếm tổng số hàng

```sql
SELECT COUNT(*)
FROM customers;

SELECT COUNT(*)
FROM customers
Limit 112, 10;

-- Trong đó 112 là số thứ tự, 10 là hàng phải lấy --
-- Ở đây ta phải lấy 10 hàng cuối cùng. 122 là tất cả các hàng ta tìm được sau câu lệnh SELECT COUNT(*). Nhưng do Limit bắt đầu từ 0, cho nên số thứ tự của hàng 122 sẽ là 121. --
-- Số thứ tự của hàng mốc mà ta phải lấy là 121 - 10 + 1 = 112 --
-- Cho nên câu lệnh đúng sẽ là 112,10 --
```

# Bài 5: Câu lệnh truy vấn cơ bản - P2: IN, BETWEEN, UNION, LIKE, ORDER BY, Thuộc tính suy diễn

## 5.1 Toán tử `IN` và `NOT IN`

- Toán tử `IN` cho phép ta chỉ định nhiều giá trị trong mệnh đề `WHERE`.
- Toán tử `IN` là viết tắt của nhiều điều kiện `OR`, được sử dụng để giảm thiểu việc phải sử dụng quá nhiều điều kiện `OR` trong các lệnh `SELECT`, `INSERT`, `UPDATE` hoặc `DELETE`

- Cú pháp:

```SQL
SELECT danh sách các cột
FROM tên bảng
WHERE cột IN ('giá trị 1', 'giá trị 2');
```

Ví dụ 1: **_Tìm tất cả các văn phòng được đặt tại Mỹ (USA) hoặc Pháp (France)_**

```sql
Dùng OR
SELECT officeCode, city, phone, country
FROM offices
WHERE country = 'USA' OR country = 'France';

Dùng IN
SELECT officeCode, city, phone, country
FROM offices
WHERE country IN ('USA','France');

Hai cách dùng đều cho ra kết quả giống nhau
```

Ví dụ 2: **_Tìm tất cả các văn phòng được đặt tại Anh (UK), Nhật Bản (Japan), Australia_**

```sql
SELECT officeCode, city, country, phone
FROM offices
WHERE country IN ("UK", "Japan", "Australia");
```

Ví dụ 3: **_Tìm tất cả các văn phòng không nằm ở Mỹ và Pháp_**

```sql
SELECT officeCode, city, country, phone
FROM offices
WHERE country NOT IN ('USA','France');
```

## 5.2 Toán tử `BETWEEN` và `NOT BETWEEN`

Ví dụ 4: **_Tìm tất cả các sản phẩm có giá nằm trong phạm vi 90$ và 100$,_**

```sql
SELECT productCode, ProductName, buyPrice
FROM products
WHERE buyPrice BETWEEN 90 AND 100
ORDER BY buyPrice DESC;
Không được đảo thứ tự là 100 AND 90, như vậy sẽ trả ra kết quả NULL
```

Ví dụ 5: **_Tìm tất cả các sản phẩm với giá mua nằm ngoài phạm vi 20 và 100_**

```sql
SELECT productCode, ProductName, buyPrice
FROM products
WHERE buyPrice NOT BETWEEN 20 AND 100
ORDER BY buyPrice DESC;

Truy vấn tương tự khi dùng OR:
SELECT productCode, ProductName, buyPrice
FROM products
WHERE buyPrice > 100 OR buyPrice < 20
ORDER BY buyPrice DESC;
```

Ví dụ 6: **_Lấy danh sách khách hàng có tên ký tự trong khoảng từ 'A' đến 'C'_**

```sql
SELECT employeeNumber, lastName, firstName, jobTitle
FROM employees
WHERE firstName BETWEEN 'A' AND 'C'
ORDER BY firstName;
```

Ví dụ 7: **_Tìm các đơn hàng đã được vận chuyển trong khoảng thời gian từ 4/1/2004 tới 4/2/2004_**

```sql
SELECT orderNumber, shippedDate, status
FROM orders
WHERE shippedDate BETWEEN '2004-01-04' AND '2004-02-04' AND status = 'Shipped';
```

## 5.3 Toán tử `LIKE` và `NOT LIKE`, `LEFT(string, length)` và `RIGHT(string, length)`

- Toán tử `LIKE` cho phép thực hiện việc tìm kiếm thông tin dựa trên so sánh ký tự ('giống như')
- `LIKE` thường được sử dụng trong mệnh đề `WHERE` ở các lệnh `SELECT`, `INSERT`, `UPDATE` và `DELETE`
- MySQL cung cấp cho `LIKE` hai ký tự đại diện:
  - Phần trăm (`%`): đại diện cho chuỗi ký tự với bất kỳ độ dài nào, bao gồm cả độ dài 0.
  - Dấu gạch dưới (`_`): đại diện cho một ký tự đơn
- Những ký tự đại diện này có thể sử dụng kết hợp.
- Cú pháp

```sql
SELECT cột1, cột2,...
FROM tên bảng
WHERE tên cột LIKE mẫu;
```

- Một vài ví dụ về mẫu

```sql
1. WHERE tên cột LIKE 'a%' : -- Tìm giá trị bắt đầu với a --
2. WHERE tên cột LIKE '%a' : -- Tìm giá trị kết thúc với a --
3. WHERE tên cột LIKE '%a%' : -- Tìm giá trị có a ở bất kỳ vị trí nào --
4. WHERE tên cột LIKE '\_a%' : -- Tìm giá trị có a ở vị trí thứ 2 --
5. WHERE tên cột LIKE 'a%%' : -- Tìm giá trị bắt đầu có a và có ít nhất 3 ký tự (hoặc cũng có thể viết là a*%*%) --
6. WHERE tên cột LIKE 'a%b' : -- Tìm giá trị bắt đầu có a và kết thúc với b\*/ --
-- Chú ý không phân biệt case sensitive 'a%' hay 'A%' là như nhau --
```

Ví dụ 8: **_Tìm kiếm những nhân viên có tên bắt đầu với ký tự 'a', ta dùng cú pháp WHERE tên cột LIKE 'a%'_**

```sql
SELECT employeeNumber, lastName, firstName
FROM employees
WHERE firstName LIKE 'a%';
```

Ví dụ 9: **_Tìm kiếm tất cả các nhân viên có họ kết thúc với chuỗi 'on', ta dùng cú pháp WHERE tên cột LIKE '%a'_**

```sql
SELECT employeeNumber, lastName, firstName
FROM employees
WHERE lastName LIKE '%on';
```

Ví dụ 10: **_Tìm kiếm những nhân viên mà họ của những nhân viên này có cụm từ 'on', ta dùng cú pháp WHERE tên cột LIKE '%a%_**

```sql
SELECT employeeNumber, lastName, firstName
FROM employees
WHERE lastName LIKE '%on%';
```

Ví dụ 11: **_Tìm kiếm những nhân viên có họ không bắt đầu bởi 'B', ta dùng cú pháp WHERE tên cột LIKE '%a%' kết hợp với NOT_**

```sql
SELECT employeeNumber, lastName, firstName
FROM employees
WHERE lastName NOT LIKE 'B%';
Tương tự nếu muốn tìm những nhân viên có họ không chứa ký tự 'B':
SELECT employeeNumber, lastName, firstName
FROM employees
WHERE lastName NOT LIKE '%B%';
```

Ví dụ 12: **_Tìm những mã sản phẩm có 10 ở vị trí thứ 2 ta dùng cú pháp WHERE tên cột LIKE '\_a%'_**

```sql
SELECT productCode, productName
FROM products
WHERE productCode LIKE '\_10%';
```

Ví dụ 13: **_Tìm những giá trị quantityInStock có 4 chữ số, bắt đầu bằng 7 và kết thúc bằng 3. Ta sử dụng cú pháp WHERE tên cột LIKE '7\_\_3' (2 dấu gạch dưới)_**

```sql
SELECT productCode, productLine, quantityInstock
FROM products
WHERE quantityInstock LIKE '7__3';
```

Ví dụ 14: **_Tìm những tên khách hàng bắt đầu bằng B và có ít nhất 3 ký tự, ta dùng cú pháp WHERE tên cột LIKE 'a\%\%' _**

```sql
SELECT customerNumber, customerName
FROM customers
WHERE customerName LIKE 'B%%';
```

Ví dụ 15: **_Tìm những tên khách hàng bắt đầu bằng A và có o ở cuối, ta dùng cú pháp WHERE tên cột LIKE 'a\%o' _**

```sql
SELECT customerNumber, customerName
FROM customers
WHERE customerName LIKE 'a%o';
```

Ví dụ 16: **_Tìm tất cả các nhân viên có tên đầu tiên bắt đầu với một chuỗi quy định, có thể sử dụng hàm LEFT()_**

```sql
SET @str = 'b';
SELECT employeeNumber, lastName, firstName
FROM employees
WHERE LEFT(lastname,length(@str)) = @str;
```

## 5.4 Thuộc tính suy diễn được (Derived Attribute)

> "SQL cung cấp khả năng tạo ra các thuộc tính suy diễn trong bảng kết quả trả về, sử dụng các toán tử và hàm dựa trên thuộc tính có sẵn. Tên cột của thuộc tính suy diễn phụ thuộc vào hệ thống, tuy nhiên có thể gán bí danh làm tên cột"

Ví dụ 17: **_Tạo ra 1 cột suy diễn đặt tên là lineTotal, thuộc tính này là kết quả phép nhân giữa hai thuộc tính priceEach và quantityOrdered_**

```sql
SELECT orderNumber, (priceEach*quantityOrdered) AS lineTotal
FROM orderdetails;
```

> Nếu ta muốn tính tổng của tất cả các mã đơn hàng (orderNumber), ví dụ như tổng của tất cả đơn hàng có mã 10100 thì phải kết hợp thêm lệnh GROUB BY và hàm SUM như sau:

```sql
SELECT orderNumber, SUM(priceEach*quantityOrdered) as lineTotal
FROM orderdetails
GROUP BY orderNumber;
```

## 5.5 `ORDER BY`

- ORDER BY được sử dụng để sắp xếp kết quả tra về theo một cột, nhiều cột. Mệnh đề này chỉ có thể dùng trong lệnh `SELECT`, với các tham số tăng dần là `ASC` và giảm dần là `DESC`

- Chú ý:
  - Nếu `ORDER BY {column_1}, {column_2},...` thì thứ tự sắp xếp sẽ được ưu tiên từ column 1 rồi đến column 2.
    VD:
    ```sql
    ORDER BY name, age asc
    -- Nếu có 2 giá trị name bằng nhau, (ví dụ cùng bằng "hiếu") thì sẽ so sánh đến age --
    ```

Ví dụ 18: **_Đưa ra thông tin về các sản phẩm theo thứ tự giảm dần của số lượng hàng tồn kho_**

```sql
SELECT productName, quantityInstock
FROM products
ORDER BY quantityInstock DESC;
```

## 5.6 Kết hợp các kết quả với toán tử `UNION` - Tương đương toán tử hợp trong đại số quan hệ

- Sử dụng UNION để kết hợp hai hoặc nhiều bộ kết quả từ nhiều bảng với nhau.

- Cú pháp:

```sql
SELECT biểu thức 1, biểu thức 2,... biểu thức n
FROM bảng [WHERE điều kiện]
UNION
SELECT biểu thức 1, biểu thức 2,... biểu thức n
FROM bảng [WHERE điều kiện]
```

- Lưu ý khi sử dụng `UNINON`:
  - Số lượng các cột trong mỗi câu lệnh `SELECT` phải giống nhau
  - Mỗi cột tương ứng vị trí phải có cùng kiểu dữ liệu và độ dài, hoặc ít nhất có thể chuyển đổi sang cho nhau
  - Theo mặc định thì `UNION` sẽ loại bỏ các kết quả trùng lặp của các câu SELECT và tạo cho chúng ta hai lựa chọn sau:
    - Nếu chọn UNION DISTINCT thì sẽ loại bỏ kết quả trùng lặp.
    - Nếu chọn UNION ALL thì giữ lại kết quả trùng lặp.
    - Nếu không chọn gì thì mặc định sẽ là UNION DISTINCT

Ví dụ 19: **_Kết hợp thông tin về khách hàng và nhân viên thành một tập hợp kết quả_**

> Chạy 3 ví dụ 1,2,3 để xem sự liên kết

Ví dụ 19-1:

```sql
select customerNumber, contactLastname
From customers;
```

Ví dụ 19-2

```sql
Select employeeNumber, firstName
From employees;
```

Ví dụ 19-3

```sql
select customerNumber, contactLastname
From customers
UNION
Select employeeNumber, firstName
From employees;
```

Ví dụ 20: **_Kết hợp thông tin của nhân viên và khách hàng, sau đó muốn sắp xếp kết quả theo tên và ID thứ tự tăng dần _**

```sql
SELECT customerNumber, contactLastname
FROM customers
UNION
SELECT employeeNumber, firstName
FROM employees
ORDER BY contactLastName, customerNumber;
-- Giống Orderby 2,1 do cột 2 được ưu tiên trước cho nên sẽ ra thứ tự số contactLastName sẽ là a,b,c --
```

Ví dụ 21:

```sql
select customerNumber, contactLastname
From customers
UNION
Select employeeNumber, firstName
From employees
Order by customerNumber, contactLastName;
-- Giống orderby 1,2, do cột 1 được ưu tiên trước cho nên sẽ ra thứ tự số customerNumber từ nhỏ đến lớn --
```

# Bài 6: Substring(), Concat(), Replace(), If(), Last_insert_id, DateDiff(), AddDate(), Extract()

## 6.1 Hàm `Substring()`

- Cú pháp:

```sql
SUBSTRING ( String, start_postion, [length] )
SUBSTRING ( String FROM start_postion For length )
```

- Trong đó:
  - String (ở một số chỗ khác sẽ viết tắt là str)
  - Chuỗi nguồn start_position (ở một số chỗ khác sẽ viết là position hoặc pos): Vị trí bắt đầu trích xuất. Vị trí đầu tiên trong chuỗi luôn là 1.
  - length: Đây là số lượng ký tự để trích xuất, phải là số nguyên dương. Nếu tham số bị bỏ qua, hàm SUBSTRING sẽ trả về toàn bộ chuỗi. Không bắt buộc, cho nên trong trường hợp không quy ước length thì ta có thể viết là (như trong giáo trình):
    ```sql
    SUBSTRING ( str, pos ) hoặc SUBSTRING ( str FROM pos )
    ```
- Lưu ý:
  - Vị trí đầu tiên trong chuỗi là 1.
  - Nếu start_position là một số dương thì hàm SUBSTRING bắt đầu từ đầu chuỗi.
  - Nếu start_position là một số âm thì hàm SUBSTRING bắt đầu từ cuối chuỗi đếm ngược.

Cú pháp:

```sql
SUBSTRING ( str pos )

SUBSTRING ( str FROM pos )
```

Ví dụ 1:

```sql
SELECT SUBSTRING('MySQL Substring', 7);
SELECT SUBSTRING('MySQL Substring' FROM 7);
```

- Kết quả trả về của cả 2 câu lệnh là chuỗi `"Substring"` của `"MySQl Substring"`
- Startposition là 7. Do vị trí bắt đầu trích xuất là _7_ và _7_ là một số nguyên dương, cho nên hàm SUBSTRING bắt đầu từ đầu chuỗi. Ta đếm từ đầu chuỗi có các ký tự `'M', 'y', 'S', 'Q', 'L'`, dấu cách trắng và ký tự `'S'` là ký tự số _7_, cho nên chuỗi được trích xuất bắt đầu từ `'S'`.
- Length: không có, cho nên chuỗi được trích xuất sẽ được lấy hết từ ký tự số _7_ trở đi, tức là toàn bộ chuỗi `"Substring"`.

Cú pháp:

```sql
SUBSTRING ( String, start*postion, length )
SUBSTRING ( String FROM start_postion For length )
```

Ví dụ 2:

```sql
SELECT SUBSTRING('MySQL Substring', 7, 3);
SELECT SUBSTRING('MySQL Substring'FROM 7 FOR 3);
```

- Cả hai câu lệnh đều trả về chuỗi `"Sub"`
- String (chuỗi nguồn) là 'MySQL Substring'
- Startposition là _7_. Do vị trí bắt đầu trích xuất là _7_ và _7_ là một số nguyên dương, cho nên hàm `SUBSTRING` bắt đầu từ đầu chuỗi. Ta đếm từ đầu chuỗi có các ký tự `'M', 'y', 'S', 'Q', 'L'`, dấu cách trắng và ký tự `'S'` là ký tự số _7_, cho nên chuỗi được trích xuất bắt đầu từ `'S'`.
- Length: là _3_, cho nên chuỗi được trích xuất sẽ được lấy _3_ ký tự từ số _7_ trở đi, tức các ký tự `'S', 'u', 'b'`.

Cú pháp:

```sql
SUBSTRING ( str, pos )
SUBSTRING ( str FROM pos )
```

Ví dụ 3:

```sql
SELECT SUBSTRING('MySQL Substring', -9);
SELECT SUBSTRING('MySQL Substring' FROM -9);

-- Do startposition bằng - 9 là số âm, và không có length cho nên chuỗi được trích xuất sẽ là 9 ký tự được tính từ cuối chuỗi lên (kết quả trả về là "Substring"). --
```

Cú pháp:

```sql
SUBSTRING ( String, start*postion, [length] )
SUBSTRING ( String FROM start_postion For length )
```

Ví dụ 4:

```sql
SELECT SUBSTRING('MySQL Substring', -9, 2);
SELECT SUBSTRING('MySQL Substring' FROM -9 FOR 2);

-- Do startposition bằng - 9 là số âm, và lenght = 2 cho nên chuỗi được trích xuất sẽ là 2 ký tự tính từ ký tự số 9 được tính từ cuối chuỗi lên. (kết quả trả về là Su) --
```

Ví dụ 5:
Cú pháp:

```sql
SUBSTRING ( str, pos )
SELECT SUBSTRING('MySQL Substring', 20);

-- Ở đây do strart_position (20) vượt ngưỡng số ký tự của string (15) cho nên kết quả sẽ trả về vô giá trị --
```

Ví dụ 6: **_Lấy ra 5 ký tự đầu tiên của cột city trong bảng offices_**

```sql
SELECT SUBSTRING(city, 1,5)
FROM classicmodels.offices;
```

Ví dụ 7: **_Lấy ra 7 ký tự đầu tiên của vị trí thứ nhất trong của cột producLine trong bảng productlines, đặt tên cột là productTittle_**

```sql
SELECT productLine, substring(productLine, 1,7) AS productTittle
From classicmodels.productLines;
```

## 6.2 Hàm `Concat()`

- Mô tả: Hàm `CONCAT` được sử dụng để nối hai hoặc nhiều chuỗi. Nếu các đối số là số, chúng sẽ được chuyển đổi thành chuỗi trước khi nối.
- Cú pháp:

```sql
CONCAT (string1, string2,...string*n)
```

Ví dụ 1: **_Để hiện thị tên đầy đủ đầu tiên của địa chỉ liên lạc của khách hàng ta sử dụng hàm `CONCAT` để nối các tên đầu tiên và tên cuối cùng và dấu phân cách giữa chúng._**

```sql
SELECT CONCAT(contactLastname,',',contactFirstname) AS fullname
FROM customers;
```

- Kết quả hàng 1 là chuỗi 'Schmitt, Carine'
- Ở đây câu lệnh CONCAT đã định rõ thứ tự lần lượt là: `contactLastname, dấu phẩy, contactFirstname`.
- Nếu như ta muốn dấu phẩy ở cuối thì phải viết là: `contactLastname, contactFirstname, dấu phẩy`.
- Hoặc muốn có dấu phẩy ở cả giữa và cuối thì phải viết là: `contactLastname, dấu phẩy, contactFirstname, dấu phẩy`

Ví dụ 2: **_Dùng hàm concat_ws dùng để ghép hai hoặc nhiều chuỗi
lại với nhau và thêm một dấu phân cách giữa mỗi chuỗi được nối._**

Cú pháp:

```sql
CONCAT_WS( separator,string1,string2,...string_n)

-- Trong đó, separator là dấu phân cách được thêm vào giữa mỗi chuỗi được nố --
```

```sql
SELECT CONCAT_WS('; ',contactLastname,contactFirstname)
fullname
FROM customers;
```

- Kết quả hàng 1 là chuỗi 'Schmitt; Carine '
- Ở đây câu lệnh CONCAT_WS đã thực thi việc ghép hai chuỗi contactLastName và contactFirstname,phân tách hai chuỗi bằng dấu ';', không phân thành thứ tự lần lượt như câu lệnh CONCAT phía trên.
- Ta so sánh với câu lệnh dưới để thấy sự khác biệt:

```sql
SELECT CONCAT('; ',contactLastname,contactFirstname)
fullname
FROM customers;
```

> **Nếu muốn dùng câu lệnh CONCAT để ra kết quả giống CONCAT_WS, ta phải viết là:**

```sql
SELECT CONCAT(contactLastname,'; ',contactFirstname)
fullname
FROM customers;
```

Ví dụ 3: **_Nối các hàm bằng chuỗi lệnh CONCAT_**

```sql
SELECT CONCAT('MySQL', 'Workbench');
SELECT CONCAT('My', 'SQL', 'Workbench');
SELECT CONCAT('My ', 'SQL ','Workbench ');
```

Ví dụ 4: **_Chạy thử các ví dụ_**

```sql
SELECT CONCAT_WS(',', 'First name', 'Second name', 'Last Name');
-- "First name,Second name,Last Name" --
SELECT CONCAT_WS(',', 'First name', NULL, 'Last Name');
-- "First name,Last Name" --
```

Ví dụ 5: **_Chạy thử các ví dụ_**

```sql
SELECT CONCAT_WS(NULL ,'Jonathan', 'Smith');
-- Kết quả trả về rỗng --
SELECT CONCAT_WS(',','Jonathan', 'Smith',NULL);
-- Kết quả trả về chuỗi 'Jonathan,Smith' --
```

Ví dụ 6:

```sql
SELECT
CONCAT*WS(CHAR(13),
CONCAT_WS(' ', contactLastname, contactFirstname),
addressLine1,
addressLine2,
CONCAT_WS(' ', postalCode, city),
country,
CONCAT_WS(CHAR(13), '')) AS Customer_Address
FROM customers;
-- Bỏ đi CONCAT_WS(CHAR(13), '') không ảnh hưởng đến kết quả --
```

## 6.3 Hàm `Replace()`

- Mô tả: Hàm Replace cho phép thay thế một chuỗi trong một cột của một bảng bằng một chuỗi mới.
- Cú pháp:

```sql
UPDATE [tên bảng]
SET tên cột = REPLACE (tên cột, xâu cần tìm, xâu thay thế)
WHERE [các điều kiện]
```

- Lưu ý:
  - Khi tìm kiếm các văn bản để thay thế, **MySQL có phân biệt chữ hoa và chữ thường.**
  - Nếu một trong hai tham số "xâu cần tìm" và "xâu thay thế" là NULL thì hàm sẽ trả về giá trị NULL.
  - Nếu "xâu cần tìm" không tìm thấy thì hàm sẽ trả về chuỗi của cột được chọn như ban đầu và không có sự thay đổi.

Ví dụ 1: **_Nếu muốn sửa lỗi chính tả trong bảng Product trong cơ sở dữ liệu mẫu, sử dụng hàm Replace như sau_**

```sql
SET SQL_SAFE_UPDATES = 0;
USE classicmodels;
UPDATE products
SET productDescription = REPLACE(productDescription,'abuot','about');
```

- Do CSDL mẫu không có bị sai chính tả cho nên cho dù câu lệnh đã chạy đúng thì
  dữ liệu cũng không thay đổi (Changed:0, Warnings:0)
- Lý do dùng SQL_SAFE_UPDATES = 0:
  - Khi sử dụng `MySql Workbench` để thực hiện câu lệnh `update` hoặc `delete` và cả `replace` dữ liệu bằng câu điều kiện `Where` với một column không phải Key, thì ta sẽ gặp 1 lỗi như sau: _`Error Code: 1175. You are using safe update mode and you tried to update a table without a WHERE that uses a KEY column To disable safe mode, toggle the option in Preferences -> SQL Editor and reconnect.`_
  - Đây là một cơ chế trong MySQL Workbench để cảnh báo cho việc thực hiện xóa hay update dữ liệu với 1 column không phải là Key để tránh rủi ro mất mát dữ liệu quá lớn. Để xóa được dữ liệu, ta có thể tắt chế độ Safe Update Mode tạm thời bằng việc sử dụng câu lệnh
  ```sql
  SET SQL_SAFE_UPDATES = 0;
  ```

## 6.4 Hàm `If()`

- Mô tả: IF là một hàm điều khiển, trả về kết quả là một chuỗi hoặc số dựa trên một điều kiện cho trước.
- Cú pháp:

```sql
IF (expr, if_true_expr, if_false_expr)

-- expr: Giá trị mà ta muốn kiểm tra. --
-- if_true_expr: Không bắt buộc, là giá trị được trả về nếu điều kiện đúng --
-- if_false_expr: Không bắt buộc, là giá trị được trả về nếu điều kiện sai. --
```

- Lưu ý:
  - Tham số đầu tiên là expr sẽ được kiểm tra là đúng hay sai. Giá trị đúng có nghĩa là expr không bằng 0 và expr không bằng NULL. Lưu ý rằng NULL là một giá trị đặc biệt, không bằng bất cứ điều gì khác, ngay cả bản thân nó.
  - Nếu expr được đánh giá là đúng, hàm IF sẽ trả lại if_true_expr, nếu không nó sẽ trả lại if_false_expr.
  - Hàm IF có thể trả về một chuỗi hoặc một giá trị số, tùy thuộc vào hoàn cảnh mà nó được sử dụng.

Ví dụ 1:

```sql
SELECT IF (1 = 1, 'true', 'false');
SELECT IF ('a' = 'b', 'true', 'false');
SELECT IF (1 = 3, true, false); -- Viết thế này là sai cú pháp, trả về 0 --
```

Ví dụ 2: **_Hiển thị trạng thái của khách hàng là N/A nếu nó là Null, ở đây ta dùng cú pháp IF (expr, if_true_expr, if_false_expr)_**

```sql
-- Dùng câu lệnh này để thấy được dữ liệu toàn vẹn ban đầu --

SELECT customerNumber, customerName, state,country
FROM customers;


SELECT customerNumber,customerName, IF(state IS NULL,'N/A',state) AS state, country
FROM customers;
```

- Ở đây ta dùng lệnh Select chọn ra 4 trường là customerNumber, custormerName, state và country, trong đó dùng hàm IF để bổ sung thêm điều kiện cho state.
- Ở đây expr (giá trị mà ta muốn kiểm tra) là liệu giá trị trong trường state có Null hay không.
- Giá trị if_true_expr là N/A, nghĩa là nếu giá trị trong trường state là Null (đúng) thì sẽ trả về là N/A. Giá trị if_false_expr là state, nghĩa là nếu giá trị trong trường stage không Null (sai) thì sẽ trả về đúng với giá trị của trường state ban đầu

Ví dụ 3: **_Hàm IF cũng rất hữu ích với chức năng tổng hợp. Giả sử nếu muốn biết có bao nhiêu đơn đặt hàng đã vận chuyển và huỷ bỏ cùng một lúc, chúng ta có thể sử dụng IF để đếm như sau_**:

```sql
SELECT SUM(IF(status = 'Shipped',1,0)) AS Shipped,
SUM(IF(status = 'Cancelled',1,0)) AS Cancelled
FROM orders;
```

- Trong truy vấn trên, nếu tình trạng của đơn đặt hàng là SHIPPED hoặc CANCELLED, IF sẽ trả lại giá trị 1, nếu không nó trả về 0. Và sau đó hàm SUM sẽ tính toán tổng số để vận chuyển và bị hủy bỏ dựa trên giá trị trả về của hàm IF

```sql
-- Bỏ SUM để xem các giá trị đơn lẻ --
SELECT (IF(status = 'Shipped',1,0)) AS Shipped,
(IF(status = 'Cancelled',1,0)) AS Cancelled
FROM orders;
```

## 6.5 Hàm `LAST_INSERT_ID`

- Mô tả: Hàm `LAST_INSERT_ID` trả về ID của bản ghi cuối cùng được chèn(`insert`) hoặc cập nhập (`update`) vào bảng, với điều kiệu đó là ID của cột có thuộc tính `AUTO_INCREMENT`.
- Cú pháp:

```sql
LAST_INSERT_ID ( )
```

Ví dụ 1: **_Tạo một bảng mới để thử nghiệm gọi là bảng thông tin sinh viên. Trong bảng sinh viên, ta sử dụng cột mã sinh viên là cột `Auto_Increment` _**

```sql
CREATE DATABASE SinhVienX;
USE SinhVienX;
CREATE TABLE ThongTinSinhVien
( Masinhvien INT AUTO_INCREMENT NOT NULL PRIMARY KEY,
Hoten VARCHAR(100) NOT NULL,
Quequan VARCHAR(200) );
USE SinhVienX;
INSERT INTO ThongTinSinhVien (Hoten, Quequan) VALUES
('Đặng Thừa An', 'Hà Nội'),
('Nguyễn Ngọc Quỳnh', 'Hà Nội'),
('Lại Hồ Ngọc Trâm', 'Hà Nội'),
('Phạm Mai Ngọc', 'Thái Bình');
```

- Sau khi chạy câu lệnh thì ta sẽ có mã sinh viên tự động từ 1 đến 4
- Nhập dữ liệu mới và sử dụng hàm LAST_INSERT_ID sẽ cho ra mã sinh viên tự động là 5

```sql
USE SinhVienX;
INSERT INTO ThongTinSinhVien (Hoten, Quequan) VALUES
('Đặng Vũ', 'Bắc Ninh');
SELECT LAST_INSERT_ID();
```

- Nhập dữ liệu bổ sung: Dữ liệu trong bảng sẽ cho ra mã sinh viên tự động từ 6 đến 11, tuy nhiên chỉ hiện thị 6 (giá trị bản ghi nhập đầu tiên)

```sql
INSERT INTO ThongTinSinhVien (Hoten, Quequan) VALUES
('Phạm Thu Hà', 'Bắc Ninh'),
('Nguyễn Thu Lan', 'Thanh Hóa'),
('Nguyễn Thị Hoa', 'Hà Nội'),
('Phạm Trung Đức', 'Bắc Giang'),
('Nguyễn Phương Thảo', 'Bắc Ninh'),
('Trần Công Long', 'Hà Nội');
SELECT LAST_INSERT_ID();
```

- Nguyên nhân do cơ chế: MySQL `LAST_INSERT_ID` hoạt động dựa trên nguyên tắc độc lập với client. Nó có nghĩa là giá trị được trả về bởi hàm `LAST_INSERT_ID` cho một client cụ thể là giá trị mà client đó tạo ra. Điều này đảm bảo rằng mỗi client có thể nhận được ID riêng của mình mà không cần phải quan tâm đến các hoạt động của các client khác và không cần sử dụng cơ chế `"LOCK"` hay `"TRANSACTION"` (sẽ học sau).

- Chú ý
  - `AUTO_INCREMENT` chỉ thiết lập được cho kiểu INT và mỗi bảng chỉ có một field duy nhất, nghĩa là nếu ta thiết lập 2 fields là `AUTO_INCREMENT` thì sẽ bị lỗi ngay.
  - Khi thêm dữ liệu, nếu ta có truyền data thì nó sẽ lấy data đó thay vì tăng tự động, ngược lại nó sẽ lấy giá trị lớn nhất hiện tại và tăng lên 1 (giá trị lớn nhất này lưu trong config của table chứ không phải là id lớn nhất trong các records).
  - Khi xóa một record thì sẽ bị khuyết mất một giá trị, lúc này nếu ta thêm thì nó sẽ không lấp vào vị trí này mà nó tuân theo quy luật trên.
  - Ví dụ: Giả sử giá trị 100 là lớn nhất, ta xóa đi 100 thì lúc này lớn nhất là 99. Lúc này nếu thêm mới thì nó sẽ lấy 101 chứ không phải là 100 vì giá trị lớn nhất nó lưu trong config của table.
  - Thông thường ta sử dụng `AUTO_INCREMENT` cho `Primary Key` khi viết ứng dụng website
  - Mặc định `AUTO_INCREMENT` sẽ có giá trị đầu tiên là 1

## 6.6 `DATEDIFF`

- Mô tả: Hàm DATEDIFF trả về chênh lệch giữa hai giá trị thời gian dựa trên mốc thời gian được chỉ định là `expr1` và `expr2`. Hai giá trị thời gian phải là ngày hoặc các biểu thức ngày và giờ dưới dạng `date` hoặc `datetime`.
- Cú pháp:

```sql
DATEIFF(expr1, expr2)
-- expr1 và expr2 là 2 mốc thời gian --
```

Ví dụ 1:

```sql
SELECT DATEDIFF('2011-08-17','2011-08-17'); -- Trả về 0 ngày --
SELECT DATEDIFF('2011-08-17','2011-08-08'); -- Trả về 9 ngày --
SELECT DATEDIFF('2011-08-08','2011-08-17'); -- Trả về -9 ngày --
```

Ví dụ 2: **_Để tính toán số ngày còn lại giữa ngày vận chuyển và ngày yêu cầu để trong đơn đặt hàng, chúng ta sử dụng DATEDIFF_**:

```sql
USE classicmodels;
SELECT orderNumber, DATEDIFF(requiredDate,shippedDate) AS daysLeft
FROM orders
ORDER BY daysLeft DESC; Lệnh sắp xếp giảm dần

-- Do ngày yêu cầu diễn ra sau ngày vẫn chuyển, cho nên khi ta viết requireDate trước shippedDate thì kết quả sẽ ra số dương --
```

## 6.7 `ADDDATE`

- Mô tả hàm ADDATE: trả về giá trị thời gian mới khi nó được cộng thêm
  một khoảng thời gian được chỉ định.

- Cú pháp:

```sql
ADDDATE(expr, day)

-- expr: khoảng thời gian ta muốn thay đổi. --
-- day: một số nguyên ngày ta muốn thêm vào biểu thức expr. --
```

- Cú pháp:

```sql
ADDDATE(date, INTERVAL expr unit)

-- date: ngày mà khoảng thời gian được thêm vào. --
-- value: giá trị của khoảng thời gian / ngày mà ta muốn thêm. Ta cũng có thể chỉ định giá trị dương và âm cho tham số này. --
-- unit: loại đơn vị của khoảng thời gian như ngày(day), giờ (hour), tháng (month), phút (minute), tuần (week) --
```

Ví dụ 1: **_Thêm một khoảng thời gian nhất định, sử dụng cú pháp `ADDDATE(expr, day)`_**

```sql
SELECT ADDDATE('2020-04-16', 28);

-- Kết quả sẽ ra là 2020-05-14, cộng thêm 28 ngày --
```

Ví dụ 2: **_Đưa ra ngày tháng sau ngày giờ hiện tại là 30 ngày, sử dụng cú pháp_**

```sql
ADDDATE(date, INTERVAL expr unit)
SELECT ADDDATE(NOW(), INTERVAL 30 day);

-- Kết quả khi chạy là '2021-04-04 00:28:30'- thời gian hiện tại của máy tính --
```

```sql
SELECT ADDDATE('2020-04-16', interval 28 day)
-- Cho ra kết quả giống ví dụ 1 --
```

Ví dụ 3: **_Đưa ra các đơn đặt hàng trong khoảng 30 ngày tính từ ngày 1/5/2005, sử dụng cú pháp `ADDDATE(date, INTERVAL expr unit)`_**

```sql
USE classicmodels;
SELECT *
FROM orders
WHERE orderDate>= '2005-5-1' AND orderDate < ADDDATE('2005-5-1', INTERVAL 30 DAY);
```

> Do các đơn đặt hàng được tính từ ngày 1/5/2005 trở đi cho nên orderDate phải lớn hơn hoặc bằng 1/5/2005 và nhỏ hơn mốc 1/5/2005 cộng thêm với 30 ngày. Ta sử dụng cú pháp ADDDATE(date, INTERVAL expr unit) để tính thêm mốc cộng thêm đó.

Ví dụ 4: **_Đưa ra các đơn đặt hàng tính từ trước ngày 1/5/2005 30 ngày (câu hỏi trong giáo trình hơi dễ nhầm)_**

> Do đơn đặt hàng được tính từ trước ngày 1/5/2005 cho nên orderDate phải nhỏ hơn hoặc bằng 1/5/2005 và lớn hơn mốc 1/5/2005 trừ đi 30 ngày

```sql
SELECT *
FROM orders
WHERE orderDate<= '2005-5-1' AND orderDate > ADDDATE('2005-5-1', INTERVAL -30 DAY);
```

> Hoặc viết lại như sau:

```sql
SELECT *
FROM orders
WHERE orderDate<= '2005-5-1' AND orderDate > ADDDATE('2005-5-1', INTERVAL -1 MONTH);
```

> Nếu như ví dụ 1 và ví dụ 2 có thể viết giống nhau (bỏ đi interval và chỉ thêm số ngày) thì ở ví dụ này không thể viết như thế được. Ta bắt buộc phải thêm interval.

## 6.8 `EXTRACT()`

- Mô tả hàm EXTRACT: tách ra các giá trị như ngày, tháng, năm từ một giá trị có kiểu thời gian.
- Cú pháp:

```sql
EXTRACT( unit FROM date )

-- unit: loại đơn vị của khoảng thời gian như ngày(day), giờ (hour), tháng (month), phút (minute), tuần (week).--
-- date: giá trị ngày hoặc ngày giờ để trích xuất --
```

Ví dụ 1: **_Đưa ra tháng của một giá trị thời gian, sử dụng cú pháp EXTRACT( unit FROM date ) _**

```sql
SELECT EXTRACT(MONTH FROM '2004-12-31 23:59:59'); #Kết quả trả về là tháng 12
```

> Hoặc cũng có thể viết để ra kết quả tương tự

```sql
SELECT MONTH('2004-12-31 23:59:59');
```

> Hoặc cũng có thể đưa ra năm của một giá trị thời gian

```sql
SELECT EXTRACT(YEAR FROM '2004-12-31 23:59:59'); #Kết quả trả về là năm 2004
```

Ví dụ 2: **_Đưa ra tuần của một giá trị thời gian, sử dụng cú pháp EXTRACT( unit FROM date ) _**

```sql
SELECT EXTRACT(WEEK FROM '2021-03-05 23:59:59');

-- Kết quả ra 9, nghĩa là từ ngày 5 tháng 3 năm 2021 trở về trước đã trôi qua 9 tuần --

-- Nếu ta tăng ngày 5 lên khoảng 7 ngày thì số tuần sẽ là 10 --
```

Ví dụ 3: **_Đưa ra các đơn hàng đặt năm 2005, sử dụng cú pháp EXTRACT( unit FROM date ) kết hợp với điều kiện Where _**

```sql
SELECT *
FROM orders
WHERE EXTRACT(YEAR FROM orderDate) = 2005;
```

Ví dụ 4: **_Đưa ra các đơn hàng đặt trong tháng 5 năm 2005_**

```sql
SELECT *
FROM orders
WHERE EXTRACT(YEAR FROM orderDate) = 2005 and EXTRACT(MONTH FROM orderDate) = 5;
```

Nếu muốn dùng hàm `ADDDATE` như phần `a`, tả phải viểt là:

```sql
SELECT _
FROM orders
WHERE orderDate>= '2005-5-1' AND orderDate <= ADDDATE('2005-5-1', INTERVAL 30 DAY);
```

- Cách viết trên giống với ví dụ 3 phần a nhưng ADDDATE được để là <= thay vì <,
  cho nên nếu ở ví dụ 3 phần 3, orderNumber chỉ tới số 10423 (do dừng ở ngày 30)

# Bài 7: Truy vấn nhóm

## 7.1 Hàm nhóm: `Sum()`, `Avg()`, `Min()`, `Max()`, `Count()`

### 7.1.1 Hàm `SUM`

- Mô tả: Hàm `SUM` trả về giá trị tổng của một biểu thức
- Cú pháp:

```sql
  SELECT Sum(Tên_cột)
  FROM Tên_bảng
  WHERE Điều_kiện
```

Ví dụ 1: **_Tính tổng số lượng hàng hóa hiện còn trong kho._**

```sql
SELECT sum(quantityInStock)
FROM products;
```

Ví dụ 2: **_Tính tổng số tiền đã thu được từ đầu tới giờ và đặt tên cho cột tổng số tiền là Total._**

```sql
SELECT sum(priceEach * quantityOrdered) AS total
FROM orderdetails;
```

### 7.1.2 Hàm `AVG`

- Mô tả: Hàm `AVG` trả về giá trị trung bình tính theo cột được chỉ định và không chấp nhận giá trị NULL.
- Cú pháp:

```sql
  SELECT Avg(Tên_cột)
  FROM Tên_bảng
  WHERE Điều_kiện
```

Ví dụ 3: **_Tính giá trị trung bình của tất cả các sản phẩm đã mua_**

```sql
SELECT AVG(buyPrice) average_buy_price
FROM Products;
```

### 7.1.3 Hàm `MAX` và `MIN`

- Mô tả: Hàm `MAX` trả về giá trị lớn nhất và hàm MIN trả về giá trị nhỏ nhất của một tập các giá trị.
- Cú pháp MAX:

```sql
SELECT Max(Tên_cột)
FROM Tên_bảng
WHERE Điều_kiện
```

- Cú pháp MIN:

```sql
SELECT Min(Tên_cột)
FROM Tên_bảng
WHERE Điều_kiện
```

Ví dụ 4: **_Sử dụng MIN, MAX để lấy ra mức giá cao nhất và mức giá nhỏ nhất của sản phẩm._**

```sql
SELECT MAX(buyPrice) as highest_price,
MIN(buyPrice) as lowest_price
FROM Products;
```

Ví dụ 5: **_Sử dụng MIN, MAX để lấy ra số lượng cao nhất và số lượng nhỏ nhất của sản phẩm._**

```sql
SELECT MAX(quantityInstock) most_product,
MIN(quantityInstock) less_product
FROM Products;
```

### 7.1.4 Hàm `COUNT`

- Mô tả: Hàm COUNT là hàm đếm số lượng.
- Cú pháp:

```sql
  SELECT Count(Tên_cột)
  FROM Tên_bảng
  WHERE Điều_kiện
```

Ví dụ 6: **_Đếm số dòng dữ liệu trong bảng. Ta sử dụng cú pháp `SELECT Count(\*) FROM Tên_bảng`_**

```sql
SELECT COUNT(*) AS Total
FROM products;

SELECT COUNT(*) AS Total
FROM payments;
```

- Lưu ý: một phiên bản khác của hàm COUNT sử dụng tham số là tên cột. Nếu cách này được sử dụng, sẽ chỉ đếm các dòng mà giá trị tại cột đó là khác NULL. Ta có thể thấy rõ điều này qua ví dụ 7.

Ví dụ 7: **_Đếm số hàng trong bảng productlines. Ở câu lệnh đầu tiên ta dùng (\*), mySQL sẽ đếm số hàng của toàn bảng. Nhưng ở câu lệnh tiếp theo ta lại đếm cột image, mà cột này toàn giá trị NULL nên kết quả sẽ trả về là 0._**

```sql
SELECT COUNT(*)
FROM productlines;

SELECT COUNT(image)
FROM productlines;
```

## 7.2 Mệnh đề nhóm `GROUP BY`

- Mô tả:
- GROUP BY dùng để gộp các bản ghi có cùng giá trị tại một hay nhiều cột, thành một tập hợp.
- GROUP BY nếu có thì nó phải đứng sau mệnh đề WHERE hoặc FROM. Theo sau từ khoá GROUP BY là một danh sách các biểu thức, phân cách nhau bởi dấu phẩy.
- GROUP BY thường được sử dụng với các hàm tổng hợp COUNT, MAX, MIN, SUM,
  AVG.

- Cú pháp:

```sql
  SELECT cột1, cột2,... cộtn, các hàm nhóm(biểu thức)
  FROM tên_bảng
  WHERE điều_kiện
  GROUP BY cột1, cột2,... cột n
  ORDER BY danh sách cột
```

Ví dụ 8: **_Phân chia các đơn đặt hàng trong từng nhóm phụ thuộc vào trạng thái đơn hàng._**

```sql
SELECT status
FROM orders
GROUP BY status;
```

- **Nếu như ta mở bảng orders, ở trong cột status, có rất nhiều dữ liệu và những giá trị `Shipped, Resolved, Cancelled, On Hold, Dispute, In Process` được lặp đi lặp lại rất nhiều lần. Ở đây câu lệnh `GROUP BY` đã gộp các giá trị trùng lặp lại và đưa ra 1 tập hợp duy nhất, cho ta biết có mấy kiểu trạng thái trong cột status**

Ví dụ 9: **_Nếu như ta muốn xem các giá trị xuất hiện bao nhiêu lần thì có thể kết hợp với lệnh count(\*)_**:

```sql
SELECT status, COUNT(*) AS numberAppeared
FROM orders
GROUP BY status;
```

Ví dụ 10: **_Tương tự ví dụ 9, nếu như muốn biết có bao nhiêu loại sản phẩm trong mỗi loại dòng sản phẩm ta cũng có thể làm như sau_**:

```sql
SELECT productLine, COUNT(*) AS NA
FROM products
GROUP BY productLine;
```

Ví dụ 11: **\*Để tính tổng số tiền cho mỗi sản phẩm đã bán ở bảng orderdails, ta sử dụng kết hợp cả hàm `SUM` để tính tổng và `GROUP BY` để nhóm các sản phẩm**:

```sql
SELECT productCode, sum(priceEach * quantityOrdered) AS total
FROM orderdetails
GROUP by productCode;

-- Nếu như muốn sắp xếp kết quả ta thêm ORDER BY total DESC hoặc ORDER BY total ASC --
```

## 7.3 Mệnh đề điều kiện `HAVING`

- Mô tả:
  Mệnh đề `HAVING` trong `MySQL` được sử dụng để lọc các bản ghi và chỉ lấy những bản ghi phù hợp với điều kiện, tương tự như mệnh đề `WHERE`. Tuy nhiên:
  - `WHERE` là câu lệnh điều kiện trả kết quả đối chiếu với từng dòng.
  - `HAVING` là câu lệnh điều kiện trả kết quả đối chiếu cho nhóm được tạo bởi mệnh đề `GROUP BY`. Vì vậy mà sau `GROUP BY` thì sẽ chỉ dùng được `HAVING` còn `WHERE` không dùng được sau `GROUP BY`.
- Cú pháp:

```sql
  SELECT cột1, cột2,... cột n
  FROM tên_bảng1, tên bảng2,... tên bảng
  WHERE điều_kiện
  GROUP BY cột1, cột2,... cột n
  HAVING điều_kiện
  ORDER BY cột1, cột2,... cột n
  -- Khi truy vấn ta phải tuân theo đúng thứ tự trên. --
```

Ví dụ 12: **_Sử dụng mệnh đề GROUP BY để có được tất cả các đơn đặt hàng, số lượng các mặt hàng bán ra và tổng giá trị trong mỗi đơn đặt hàng_**

```sql
SELECT ordernumber,
sum(quantityOrdered) AS itemsCount,
sum(priceEach * quantityOrdered) AS total
FROM orderdetails
GROUP BY ordernumber;
```

Ví dụ 13: **_Nếu ta muốn yêu cầu chỉ hiện thị những đơn hàng có tổng giá trị lớn hơn $2000 và đơn đặt hàng lớn hơn 630, ta cần sử dụng HAVING (vì bên trên đã sử dụng GROUP BY) kết hợp cùng AND_**

```sql
SELECT ordernumber,
sum(quantityOrdered) AS itemsCount,
sum(priceEach * quantityOrdered) AS total
FROM orderdetails
GROUP BY ordernumber
HAVING total > 2000 AND itemsCount > 630;

-- Có thể sử dụng một điều kiện kết hợp trong mệnh đề HAVING với các toán tử OR, AND. --
```

# Bài 8: INNER JOIN, LEFT JOIN, RIGHT JOIN, SELF JOIN

# Bài 9: Truy vấn con
