---
title: "Collection Framework trong Java – Cách Java cất giữ nhiều đồ cùng lúc"
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

Khi học Java, đến một lúc bạn sẽ gặp câu hỏi: “Nếu mình có rất nhiều dữ liệu thì lưu ở đâu?”. Lúc này, Collection Framework xuất hiện để giải quyết vấn đề đó. Bạn có thể hiểu đơn giản: Collection Framework là những cái hộp thông minh giúp Java cất giữ, sắp xếp và lấy dữ liệu ra dễ dàng.

### 2. Nội dung chính
### 2.1 Collection Framework là gì?

Collection Framework là một tập hợp các cách lưu trữ nhiều dữ liệu trong Java.

Nếu biến chỉ giữ được một giá trị, thì Collection có thể giữ rất nhiều giá trị cùng lúc.

Ví dụ ngoài đời:

Một hộp bút chứa nhiều cây bút

Một balo chứa nhiều cuốn sách

Java cũng cần những “cái hộp” như vậy.

### 2.2 Vì sao cần Collection Framework?

Không dùng Collection, bạn sẽ gặp khó khăn:

Không biết dữ liệu dài bao nhiêu

Thêm, xóa dữ liệu rất phiền

Code dài và khó đọc

Collection Framework giúp:

Thêm, xóa, tìm kiếm dễ dàng

Code gọn gàng hơn

Ít lỗi hơn

### 2.3 Một số Collection phổ biến trong Java

Trong Java, Collection Framework có nhiều loại, nhưng người mới chỉ cần nhớ vài loại cơ bản.

### 2.3.1 List – Danh sách có thứ tự

List giống như một danh sách:

Có thứ tự

Có thể trùng nhau

Ví dụ: danh sách học sinh trong lớp.
```javascript
import java.util.ArrayList;

ArrayList<String> tenHocSinh = new ArrayList<>();

tenHocSinh.add("An");
tenHocSinh.add("Bình");
tenHocSinh.add("An");

System.out.println(tenHocSinh);
```

👉 Kết quả:

[An, Bình, An]

### 2.3.2 Set – Không cho trùng lặp

Set giống như một bộ sưu tập:

Không có phần tử trùng nhau

Ví dụ: bộ thẻ bài, mỗi lá chỉ có một.
```javascript
import java.util.HashSet;

HashSet<String> monHoc = new HashSet<>();

monHoc.add("Toán");
monHoc.add("Văn");
monHoc.add("Toán");

System.out.println(monHoc);
```

👉 "Toán" chỉ xuất hiện một lần.

### 2.3.3 Map – Lưu theo cặp (khóa – giá trị)

Map giống như cuốn danh bạ:

Tên → số điện thoại
```javascript
import java.util.HashMap;

HashMap<String, Integer> diemSo = new HashMap<>();

diemSo.put("An", 9);
diemSo.put("Bình", 8);

System.out.println(diemSo.get("An"));
```

👉 Kết quả:

9

### 2.4 So sánh nhanh các loại Collection
Loại	Đặc điểm chính	Ví dụ ngoài đời
List	Có thứ tự, cho trùng	Danh sách lớp
Set	Không trùng	Bộ thẻ bài
Map	Khóa – giá trị	Danh bạ
2.5 Duyệt dữ liệu trong Collection

Bạn có thể dùng vòng lặp để xem từng phần tử.
```javascript
for (String ten : tenHocSinh) {
    System.out.println(ten);
}
```
👉 Java tự lấy từng phần tử ra cho bạn.

### 3. Một chút chia sẻ cá nhân

Khi mới học Java, mình từng cố dùng mảng cho mọi thứ và rất hay bị rối. Từ khi dùng Collection Framework, code trở nên dễ đọc hơn, dễ sửa hơn và đỡ mệt hơn rất nhiều.

### 4. Tổng kết

Collection Framework giúp lưu nhiều dữ liệu

List, Set, Map là 3 loại quan trọng nhất

Dùng đúng Collection sẽ giúp code gọn và rõ ràng

Nếu bạn học Java nghiêm túc, Collection Framework là phần bắt buộc phải hiểu.