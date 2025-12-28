---
title: "Biến và Kiểu dữ liệu trong JS"
draft: false
tags: ["JavaScript"]
author: ["Trương Huy Phước"]
# Bắt đầu phần cấu hình ảnh bìa
cover:
    image: "/images/js-thumbnail1.jpg"  # Đường dẫn đến file ảnh
    alt: "Hình minh họa biến và kiểu dữ liệu trong JavaScript" # Văn bản mô tả ảnh (tốt cho SEO)
    caption: "Ảnh minh họa"            # Chú thích ảnh (tùy chọn)
    relative: false                    # Đặt false vì ảnh nằm trong thư mục static
---
Chủ đề: #JavaScript Tác giả: [Trương Huy Phước] Biến và Kiểu dữ liệu trong JavaScript... (Nội dung bài viết)

Biến và Kiểu dữ liệu trong JavaScript – Hiểu đơn giản từ đầu
### 1. Giới thiệu

Sau khi biết JavaScript (JS) là gì, bước tiếp theo mà ai học lập trình cũng phải gặp là Biến và Kiểu dữ liệu. Lúc mới học, mình từng thắc mắc: “Sao phải biến với chả kiểu dữ liệu cho mệt vậy?”. Nhưng khi hiểu ra rồi, mình mới thấy đây là phần quan trọng nhất, giống như học cách cất đồ trước khi làm việc lớn.

### 2. Nội dung chính
2.1 Biến là gì?

Biến là nơi dùng để lưu trữ thông tin trong chương trình.

Bạn có thể tưởng tượng biến giống như:

Một cái hộp

Một cái ngăn kéo

Hoặc một chiếc balo

Bạn bỏ đồ vào đó, khi cần thì lấy ra dùng.

Ví dụ:

Bạn có tên

Bạn có tuổi

Bạn có điểm số

Máy tính cũng vậy, nó cần chỗ để nhớ những thông tin này.

### 2.2 Cách tạo biến trong JavaScript

Trong JavaScript, để tạo một biến, ta dùng từ khóa let.

```javascript
let ten = "An";
```

Giải thích cực đơn giản:

let → tạo một cái hộp mới

ten → tên cái hộp

"An" → thứ được bỏ vào hộp

Nghĩa là:

Tạo một cái hộp tên là ten và bỏ chữ “An” vào đó

Bạn có thể tạo nhiều biến khác nhau:

let tuoi = 10;
let diem = 9;

### 2.3 Dùng biến để làm gì?

Biến giúp chương trình ghi nhớ và sử dụng lại thông tin.

Ví dụ:
```javascript
let ten = "An";
console.log(ten);
```

Khi chạy chương trình, màn hình sẽ hiện:

An


Nếu sau này bạn muốn đổi tên:
```javascript
ten = "Bình";
console.log(ten);
```

Máy tính sẽ in ra:

Bình


👉 Bạn chỉ cần đổi giá trị trong biến, không cần sửa lại cả chương trình.

### 2.4 Kiểu dữ liệu là gì?

Kiểu dữ liệu cho biết:

Thứ bạn bỏ vào biến là loại gì?

Giống như ngoài đời:

Nước thì bỏ vào chai

Sách thì để lên kệ

Tiền thì bỏ vào ví

Máy tính cũng cần biết dữ liệu là chữ, số, hay đúng/sai.

### 2.5 Một số kiểu dữ liệu cơ bản trong JavaScript
1. Kiểu số (Number)

Dùng để lưu số:
```javascript
let tuoi = 10;
let diem = 8.5;
```

👉 Không cần dấu ngoặc kép.

2. Kiểu chữ (String)

Dùng để lưu chữ hoặc câu nói.

let loiChao = "Xin chào";
let ten = "An";


👉 Chữ luôn nằm trong dấu ngoặc kép.

3. Kiểu đúng / sai (Boolean)

Chỉ có 2 giá trị:

true (đúng)

false (sai)

Ví dụ:

let daLamBaiTap = true;
let troiMua = false;


Kiểu này rất hay dùng khi kiểm tra điều kiện.

###  2.6 Kết hợp biến và kiểu dữ liệu

Bạn có thể dùng biến để tạo câu hoàn chỉnh:
```javascript
let ten = "An";
let tuoi = 10;

console.log("Mình tên là " + ten);
console.log("Mình " + tuoi + " tuổi");
```

Kết quả:

Mình tên là An
Mình 10 tuổi

###  2.7 Một chút chia sẻ cá nhân

Khi mới học, mình từng nghĩ biến và kiểu dữ liệu là mấy thứ khô khan. Nhưng sau này mình nhận ra:

Nếu không có biến, chương trình sẽ không nhớ được gì cả.

Biến giống như trí nhớ của máy tính. Muốn làm game, làm web hay app gì thì bắt buộc phải dùng biến.

### 3. Kết luận

Biến là nơi lưu trữ thông tin

Kiểu dữ liệu cho biết thông tin đó là loại gì

JavaScript rất dễ ở chỗ: viết đơn giản, đọc cũng dễ hiểu

Chỉ cần hiểu tốt phần này, bạn đã đi được một bước rất quan trọng trên con đường học lập trình.
