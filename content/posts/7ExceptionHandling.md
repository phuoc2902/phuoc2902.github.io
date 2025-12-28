---
title: "Exception Handling trong Java – Khi chương trình biết tự xử lý lỗi"
draft: false
tags: ["Java"]
author: ["Trương Huy Phước"]
# Bắt đầu phần cấu hình ảnh bìa
cover:
    image: "/images/js-thumbnail1.jpg"  # Đường dẫn đến file ảnh
    alt: "Hình minh họa biến và kiểu dữ liệu trong JavaScript" # Văn bản mô tả ảnh (tốt cho SEO)
    caption: "Ảnh minh họa"            # Chú thích ảnh (tùy chọn)
    relative: false                    # Đặt false vì ảnh nằm trong thư mục static
---


### 1. Giới thiệu

Khi học Java, sớm hay muộn bạn cũng sẽ gặp lỗi. Lúc mới học, mình từng rất sợ lỗi vì chương trình cứ báo đỏ chói và không chạy. Nhưng thật ra, lỗi không xấu. Quan trọng là Java cho phép chúng ta bắt lỗi và xử lý nó để chương trình không bị sập. Việc đó được gọi là Exception Handling.

### 2. Nội dung chính
### 2.1 Exception là gì?

Exception có thể hiểu là:

Một sự cố xảy ra khi chương trình đang chạy.

Ví dụ ngoài đời:

Đang đi học thì trời mưa

Đang chơi game thì mất điện

Chương trình cũng có những “tai nạn” như vậy.

### 2.2 Ví dụ lỗi đơn giản
int a = 10;
int b = 0;

int c = a / b;


👉 Chia cho 0 là việc không thể, chương trình sẽ bị lỗi và dừng lại.

### 2.3 Try / Catch – Bắt lỗi như thế nào?

Java cho phép ta bọc đoạn code có thể lỗi vào try, và xử lý lỗi ở catch.
```javascript
try {
    int a = 10;
    int b = 0;
    int c = a / b;
} catch (Exception e) {
    System.out.println("Có lỗi xảy ra");
}
```

👉 Khi có lỗi:

Chương trình không bị sập

Java chạy vào catch

### 2.4 Vì sao cần Exception Handling?

Nếu không xử lý lỗi:

Chương trình dừng ngay lập tức

Người dùng không biết chuyện gì xảy ra

Nếu có xử lý lỗi:

Chương trình vẫn chạy tiếp

Thông báo rõ ràng, dễ hiểu

👉 Chương trình thân thiện hơn.

### 2.5 Finally – Luôn luôn chạy
```javascript
finally là phần luôn chạy, dù có lỗi hay không.

try {
    System.out.println("Đang xử lý");
} catch (Exception e) {
    System.out.println("Có lỗi");
} finally {
    System.out.println("Kết thúc chương trình");
}
```

👉 Dùng khi:

Đóng file

Đóng kết nối

Dọn dẹp tài nguyên

### 2.6 Một số loại Exception thường gặp

ArithmeticException → lỗi toán học

NullPointerException → dùng biến chưa có giá trị

ArrayIndexOutOfBoundsException → truy cập sai vị trí mảng

Ví dụ:
```javascript
String ten = null;
System.out.println(ten.length());
```

👉 Gây ra NullPointerException.

### 2.7 Tự tạo Exception

Bạn cũng có thể tạo lỗi cho riêng mình.
```javascript
if (tuoi < 0) {
    throw new Exception("Tuổi không hợp lệ");
}
```

👉 Giúp kiểm tra dữ liệu tốt hơn.

### 3. Một chút chia sẻ cá nhân

Trước đây, mỗi lần chương trình báo lỗi là mình rất nản. Nhưng sau khi hiểu Exception Handling, mình nhận ra lỗi chỉ là cách Java nhắc mình cẩn thận hơn. Bắt lỗi tốt sẽ giúp chương trình chạy ổn định và chuyên nghiệp hơn rất nhiều.

### 4. Tổng kết

Exception là lỗi khi chương trình đang chạy

try / catch / finally giúp xử lý lỗi

Chương trình không bị sập khi có lỗi

Là kiến thức bắt buộc khi học Java

Hiểu Exception Handling là bạn đã tiến thêm một bước quan trọng trong lập trình Java.