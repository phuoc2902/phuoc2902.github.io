---
title: "Thao tác với DOM đơn giản – Khi JavaScript “đụng tay” vào trang web"
draft: false
tags: ["JavaScript"]
author: ["Trương Huy Phước"]
# Bắt đầu phần cấu hình ảnh bìa
cover:
    image: "/images/dom.jpg"  # Đường dẫn đến file ảnh
    alt: "Hình minh họa biến và kiểu dữ liệu trong JavaScript" # Văn bản mô tả ảnh (tốt cho SEO)
    caption: "Ảnh minh họa"            # Chú thích ảnh (tùy chọn)
    relative: false                    # Đặt false vì ảnh nằm trong thư mục static
---


### 1. Giới thiệu

Khi mới học JavaScript, mình từng thắc mắc: “JavaScript dùng để làm gì ngoài tính toán?”. Câu trả lời là: JavaScript có thể thay đổi trang web đang hiển thị. Việc làm này được gọi là thao tác với DOM. Nghe tên hơi lạ, nhưng thực ra rất đơn giản và thú vị.

### 2. Nội dung chính
### 2.1 DOM là gì?

DOM (Document Object Model) là cách trình duyệt hiểu và quản lý trang web.

Bạn có thể tưởng tượng:

Trang web là một cái cây

Mỗi thẻ HTML là một nhánh cây

JavaScript có thể chạm vào từng nhánh để sửa đổi

👉 Nhờ DOM, JavaScript biết chỗ nào là tiêu đề, chỗ nào là nút bấm, chỗ nào là đoạn chữ.

### 2.2 Lấy phần tử HTML

Muốn sửa cái gì, trước hết phải lấy được nó ra.

Lấy theo id
```javascript
let tieuDe = document.getElementById("title");
```

👉 Lấy phần tử có id="title".

Lấy theo class
```javascript
let danhSach = document.getElementsByClassName("item");
```

👉 Lấy nhiều phần tử cùng class.

Cách hay dùng nhất: querySelector
```javascript
let doanVan = document.querySelector("p");
```

👉 Lấy phần tử đầu tiên giống như trong CSS.

### 2.3 Thay đổi nội dung

Sau khi lấy được phần tử, bạn có thể đổi chữ bên trong.
```javascript
let tieuDe = document.getElementById("title");
tieuDe.innerText = "Xin chào JavaScript";
```

👉 Trang web đổi nội dung ngay lập tức.

### 2.4 Thay đổi màu sắc và kiểu chữ
```javascript
let tieuDe = document.getElementById("title");
tieuDe.style.color = "red";
tieuDe.style.fontSize = "24px";
```

👉 JavaScript giống như đang trang điểm cho trang web.

### 2.5 Bắt sự kiện click

Trang web sẽ thú vị hơn khi người dùng bấm vào.

```javascript
let nut = document.getElementById("btn");

nut.onclick = function () {
    alert("Bạn vừa bấm nút!");
};
```

👉 Khi bấm nút, JavaScript sẽ phản hồi.

### 2.6 Ví dụ hoàn chỉnh nhỏ
```javascript
let nut = document.getElementById("btn");
let tieuDe = document.getElementById("title");

nut.onclick = function () {
    tieuDe.innerText = "Bạn đã bấm nút";
    tieuDe.style.color = "blue";
};
```

👉 Một nút bấm, một dòng chữ thay đổi – rất trực quan.

### 3. Một chút chia sẻ cá nhân

Lần đầu mình thay đổi được chữ trên web bằng JavaScript, cảm giác rất “đã”. DOM giúp mình thấy ngay kết quả mình làm ra, không cần chờ đợi. Đây cũng là phần khiến mình thích học JavaScript hơn.

### 4. Những lỗi người mới hay gặp

Quên gắn id trong HTML

Lấy sai tên id hoặc class

Viết JavaScript trước khi trang web load xong

👉 Những lỗi này rất bình thường khi mới học.

### 5. Tổng kết

DOM giúp JavaScript thay đổi trang web

Có thể sửa chữ, màu sắc, bắt sự kiện

Là nền tảng cho mọi website động

Hiểu được DOM là bạn đã bước một chân vào thế giới web thật sự.