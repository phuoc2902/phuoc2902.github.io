---
title: "Xử lý bất đồng bộ (Async / Await) – Chờ đợi thông minh trong JavaScript"
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


### 1. Giới thiệu

Khi mới học JavaScript, mình từng thắc mắc: “Tại sao có đoạn code chạy liền, có đoạn lại phải chờ?”. Thật ra, máy tính cũng giống con người, có việc làm nhanh, có việc cần thời gian. Async / Await giúp JavaScript biết khi nào nên chờ và khi nào nên làm tiếp mà không bị rối.

### 2. Nội dung chính
2.1 Bất đồng bộ là gì?

Bất đồng bộ nghĩa là:

Không cần đứng yên chờ xong việc này rồi mới làm việc khác.

Ví dụ ngoài đời:

Bạn nấu cơm

Trong lúc chờ cơm chín, bạn làm bài tập

Bạn không đứng nhìn nồi cơm suốt 30 phút.

JavaScript cũng vậy.

### 2.2 Ví dụ dễ hiểu về bất đồng bộ

Giả sử bạn nhờ bạn mình làm bài tập, bạn phải đợi một lúc mới có kết quả.
```javascript
setTimeout(() => {
    console.log("Bài tập đã làm xong");
}, 3000);

console.log("Mình đi chơi trước");
```

Kết quả in ra:

Mình đi chơi trước
Bài tập đã làm xong


👉 JavaScript không đứng chờ, nó làm việc khác trước.

### 2.3 Promise là gì? (Hiểu nhanh)

Trước khi có async / await, JavaScript dùng Promise.

Promise giống như một lời hứa:

Hứa sẽ xong

Hoặc thất bại

Nhưng chưa biết khi nào

Ví dụ:
```javascript
let lamBaiTap = new Promise((resolve) => {
    setTimeout(() => {
        resolve("Bài tập xong rồi");
    }, 2000);
});
```
### 2.4 Async / Await là gì?

Async / Await giúp viết code dễ đọc hơn, giống như viết từng dòng bình thường.

async → nói rằng hàm này có việc cần chờ

await → đứng chờ cho việc đó xong rồi mới làm tiếp

👉 Nhưng chỉ hàm đó chờ, chương trình không bị đứng.

### 2.5 Ví dụ đơn giản với Async / Await
```javascript
async function hocBai() {
    console.log("Bắt đầu học");

    await new Promise((resolve) => {
        setTimeout(() => {
            resolve();
        }, 2000);
    });

    console.log("Học xong rồi");
}
```
hocBai();


Kết quả:

Bắt đầu học
(Hệ thống chờ 2 giây)
Học xong rồi


👉 Code đọc từ trên xuống dưới rất dễ hiểu.

### 2.6 So sánh không dùng và dùng Async / Await

Không dùng async / await:
```javascript
setTimeout(() => {
    console.log("Xong việc");
}, 2000);


Dùng async / await:

async function lamViec() {
    await new Promise((resolve) => {
        setTimeout(resolve, 2000);
    });
    console.log("Xong việc");
}

lamViec();
```

👉 Cách thứ hai dễ đọc hơn, ít rối hơn khi code dài.

### 2.7 Bắt lỗi với try / catch

Khi chờ đợi, có thể xảy ra lỗi. JavaScript cho phép bắt lỗi rất gọn.
```javascript
async function taiDuLieu() {
    try {
        await new Promise((_, reject) => {
            reject("Lỗi tải dữ liệu");
        });
    } catch (loi) {
        console.log(loi);
    }
}
```
taiDuLieu();


👉 Nếu có lỗi, chương trình không bị sập.

### 3. Khi nào nên dùng Async / Await?

Bạn nên dùng khi:

Lấy dữ liệu từ internet

Đọc file

Chờ phản hồi từ server

Việc cần thời gian

👉 Gần như web nào cũng dùng async / await.

### 4. Chia sẻ nhỏ khi mới học

Lúc mới học async / await, mình từng nghĩ nó rất khó. Nhưng khi hiểu rằng nó chỉ là cách “chờ đợi thông minh”, mọi thứ trở nên rất rõ ràng. Viết quen rồi, bạn sẽ không muốn quay lại cách cũ nữa.

### 5. Tổng kết

Bất đồng bộ giúp chương trình không bị đứng

async và await giúp code dễ đọc

Rất quan trọng khi làm web và app

Hiểu được async / await là bạn đã tiến thêm một bước lớn trong JavaScript.