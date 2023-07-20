# Table Of Content

- [Table Of Content](#table-of-content)
- [1. Chạy MongoDB](#1-chạy-mongodb)
  - [1.1. Chạy MongoDB local](#11-chạy-mongodb-local)
    - [Cách 1: Start service có sẵn](#cách-1-start-service-có-sẵn)
    - [Cách 2: Chạy service bằng cmd](#cách-2-chạy-service-bằng-cmd)
    - [Cách 3: Chạy service bằng cmd với mongod.cfg](#cách-3-chạy-service-bằng-cmd-với-mongodcfg)
  - [2. Chạy MongoDB cloud](#2-chạy-mongodb-cloud)
  - [3. Đánh Index trong MongoDB](#3-đánh-index-trong-mongodb)
  - [4. Partition](#4-partition)
  - [5. Sharding](#5-sharding)
- [2. MongoDB Design Pattern](#2-mongodb-design-pattern)
  - [2.1 Polymorphic Pattern (Mẫu đa hình)](#21-polymorphic-pattern-mẫu-đa-hình)
  - [2.2 Attribute Pattern](#22-attribute-pattern)
  - [2.3 Bucket Pattern](#23-bucket-pattern)
  - [2.4 Subset Pattern](#24-subset-pattern)

# 1. Chạy MongoDB

## 1.1. Chạy MongoDB local

#### Cách 1: Start service có sẵn

- Vào Services, tìm MongoDB chạy service. Service có sẵn này chạy được nhờ **mongod.exe** ("_C:\Program Files\MongoDB\Server\6.0\bin\mongod.exe_") và **file config** (_C:\Program Files\MongoDB\Server\6.0\bin\mongod.cfg_)

- File config **storage path**, **systemlog path**, **network port** (3 options này có thể config bằng cmd)

#### Cách 2: Chạy service bằng cmd

- Vào C:\Program Files\MongoDB\Server\6.0\bin\ chạy mongod.exe (Có thể thay bằng biến môi trường)

- Run command: mongod.exe --port **_portInFavour_** --dbpath **_pathToDbFolder_** --logPath **_pathToLogFile_** --install --serviceName "MongoDB"

- Note: Tham số --install sẽ tạo và lưu MongoDB này như 1 windows service (có thể kiểm tra bằng **Services console**)

- VD: mongod --port 27017 --dbpath "D:\mongo_storage\data" --logpath="D:\mongo_storage\log\mongod.log"

#### Cách 3: Chạy service bằng cmd với mongod.cfg

_Xem ví dụ config file: C:\Program Files\MongoDB\Server\6.0\bin\mongod.cfg_

Run command: "C:\Program Files\MongoDB\Server\6.0\bin\mongod.exe" --config "C:\Program Files\MongoDB\Server\6.0\bin\mongod.cfg" --service

## 2. Chạy MongoDB cloud

## 3. Đánh Index trong MongoDB

## 4. Partition

## 5. Sharding

# 2. MongoDB Design Pattern

## 2.1 Polymorphic Pattern (Mẫu đa hình)

VD1: Sản phẩm trong Ecommerce

```json
{
  "_id": "21830102939812",
  "product_name": "Dien thoai",
  "product_thumb": "./image/url/img.jpg",
  "product_price": "30000",
  "product_sold_qty": 200,
  "attrs": {
    "Xuat su": "VN",
    "Mau sac": "Vang"
  }
  "createdAt": "2023",
  "updatedAt": "2023"
}
```

## 2.2 Attribute Pattern

```json
{
  "_id": "21830102939812",
  "product_name": "Dien thoai",
  "product_thumb": "./image/url/img.jpg",
  "product_price": "30000",
  "product_sold_qty": 200,
  "attrs": [
    {
      "attr_name": "Xuat su",
      "attr_value": "VN"
    },
    {
      "attr_name": "Mau sac",
      "attr_value": "Xanh"
    }
  ],
  "createdAt": "2023",
  "updatedAt": "2023"
}
```

Khi cần tìm kiếm các attr (VD: tìm kiếm điện thoại màu xanh) ta chỉ cần đánh index như sau:

```js
db.collectionName.createIndex({ attr_name: 1, attr_value: 1 });
```

Và tìm kiếm như sau:

```js
db.collectionName.find({ attr_name: 'Mau sac', attr_value: 'Xanh' });
```

**Ưu điểm**: _Làm cho các document trong collection có cùng 1 cấu trúc \(dễ thao tác, dễ đánh index\)_

**Nhược điểm**: _Truy vấn sâu vào các cấp_

## 2.3 Bucket Pattern

**Note**:

- Thường được sử dụng để lưu logs (IOT, Server request)
- Sử dụng mảng để lưu trữ 1 lượng có giới hạn

## 2.4 Subset Pattern
