# Table Of Content

- [Table Of Content](#table-of-content)
- [1. Đánh index trong MySQL](#1-đánh-index-trong-mysql)
- [2. MyISAM và InnoDB](#2-myisam-và-innodb)
- [3. Partition / Sharding](#3-partition--sharding)

# 1. Đánh index trong MySQL

[Sử dụng câu lệnh Explain để phân tích 1 câu truy vấn](https://viblo.asia/p/su-dung-explain-de-toi-uu-cau-lenh-mysql-BYjv44gmvxpV)

[Một số ví dụ cho đánh Index](https://viblo.asia/p/su-dung-index-trong-database-nhu-the-nao-cho-hieu-qua-4P856q69lY3)

**Chú ý**:

- Primary Key, Foreign Key, Unique, INDEX (ADD INDEX hoặc ADD KEY) sẽ được tạo bảng index
- Có 3 thuật toán tìm kiếm index trong MySQL:
  - _Hash index_: **Sử dụng khi câu lệnh where \( hoặc tương tự \) cần phép so sánh = hoặc !=**
  - _B-tree index_: **Sử dụng khi câu lệnh where \( hoặc tương tự \) cần phép so sánh >, <, LIKE, ORDER BY**. Hoàn toàn có thể sử dụng _B-tree_ cho phép so sánh = hoặc !=, tuy nhiên tốc độ thua _Hash index_
  - _R-tree_: Ít sử dụng

# 2. MyISAM và InnoDB

[MyISAM & InnoDB in MySQL](https://viblo.asia/p/myisam-innodb-in-mysql-924lJOkm5PM)

Cả 2 đều là **[Storage Engine](https://en.wikipedia.org/wiki/Database_engine)**

Nên sử dụng **InnoDB**

# 3. Partition / Sharding

https://topdev.vn/blog/phan-chia-du-lieu-sharding-data-partitioning/

https://viblo.asia/p/tang-toc-performance-query-sql-voi-partitions-WAyK89XEZxX

https://hocdevops.com/database/su-khac-biet-giua-cac-khai-niem-trong-database-replication-partitioning-clustering-va-sharding/#:~:text=Sharding%20v%C3%A0%20Partitioning%20%C4%91%E1%BB%81u%20l%C3%A0,trong%20m%E1%BB%99t%20server%20duy%20nh%E1%BA%A5t.
