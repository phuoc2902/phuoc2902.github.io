---
title: "Tính chất của OOP trong Java – Hiểu như chơi đồ chơi LEGO"
draft: false
tags: ["Java"]
author: ["Trương Huy Phước"]
# Bắt đầu phần cấu hình ảnh bìa
cover:
    image: "/images/co-nen-cho-be-choi-do-choi-xep-hinh.jpg"  # Đường dẫn đến file ảnh
    alt: "Hình minh họa biến và kiểu dữ liệu trong JavaScript" # Văn bản mô tả ảnh (tốt cho SEO)
    caption: "Ảnh minh họa"            # Chú thích ảnh (tùy chọn)
    relative: false                    # Đặt false vì ảnh nằm trong thư mục static
---


### 1. Giới thiệu

Khi học Java đến một lúc nào đó, bạn sẽ nghe tới một khái niệm rất hay: OOP – Lập trình hướng đối tượng. Lúc mới nghe, mình cũng hơi “ngợp” vì tên nghe khá to. Nhưng thật ra, OOP chỉ là cách tổ chức chương trình cho gọn gàng, dễ hiểu và dễ sửa hơn mà thôi.

Trong Java, OOP có 4 tính chất quan trọng. Nếu hiểu được 4 tính chất này, bạn sẽ thấy Java dễ thở hơn rất nhiều.

### 2. Nội dung chính

Trước khi đi vào 4 tính chất, bạn chỉ cần nhớ một điều đơn giản:

Đối tượng trong Java giống như một đồ vật ngoài đời.

Ví dụ:

Con mèo

Chiếc xe

Cái điện thoại

Mỗi đồ vật đều có:

Đặc điểm (màu sắc, tên, tuổi…)

Hành động (chạy, kêu, gọi điện…)

Java mô phỏng điều này vào trong code.

### 2.1 Tính đóng gói (Encapsulation)
Đóng gói là gì?

Đóng gói nghĩa là:

Giấu những thứ không cần cho người khác xem, chỉ cho dùng những gì cần thiết.

Bạn tưởng tượng một chiếc tivi:

Bạn chỉ cần dùng remote để bấm

Bạn không cần mở tivi ra xem dây điện bên trong

Java cũng làm như vậy.

Ví dụ đơn giản trong Java
```javascript
class HocSinh {
    private String ten;

    public void setTen(String t) {
        ten = t;
    }

    public String getTen() {
        return ten;
    }
}
```

Giải thích dễ hiểu:

private → không cho người ngoài đụng vào trực tiếp

setTen → dùng để đặt tên

getTen → dùng để lấy tên ra xem

👉 Người dùng không sửa lung tung, mọi thứ có kiểm soát.

### 2.2 Tính kế thừa (Inheritance)
Kế thừa là gì?

Kế thừa nghĩa là:

Con cái được thừa hưởng đặc điểm từ cha mẹ.

Ngoài đời:

Con mèo con cũng có 4 chân

Con chó con cũng biết sủa

Trong Java, lớp con có thể dùng lại những thứ của lớp cha.

Ví dụ
```javascript
class DongVat {
    void an() {
        System.out.println("Động vật đang ăn");
    }
}

class Meo extends DongVat {
    void keu() {
        System.out.println("Meo meo");
    }
}
```

Giải thích:

DongVat → lớp cha

Meo → lớp con

Mèo tự động có hành động an()

👉 Không cần viết lại từ đầu, tiết kiệm rất nhiều công sức.

### 2.3 Tính đa hình (Polymorphism)
Đa hình là gì?

Đa hình nghĩa là:

Cùng một hành động, nhưng mỗi đối tượng làm theo cách khác nhau.

Ví dụ ngoài đời:

Con chó kêu: gâu gâu

Con mèo kêu: meo meo

Cùng là “kêu”, nhưng âm thanh khác nhau.

Ví dụ
```javascript
class DongVat {
    void keu() {
        System.out.println("Động vật kêu");
    }
}

class Cho extends DongVat {
    void keu() {
        System.out.println("Gâu gâu");
    }
}

class Meo extends DongVat {
    void keu() {
        System.out.println("Meo meo");
    }
}
```

👉 Khi gọi keu():

Chó sẽ kêu kiểu chó

Mèo sẽ kêu kiểu mèo

Java tự biết phải làm gì cho đúng.

### 2.4 Tính trừu tượng (Abstraction)
Trừu tượng là gì?

Trừu tượng nghĩa là:

Chỉ quan tâm làm được gì, không quan tâm làm như thế nào.

Ví dụ:

Bạn lái xe → chỉ cần biết ga, thắng

Không cần biết động cơ hoạt động ra sao

Ví dụ
```javascript
abstract class DongVat {
    abstract void keu();
}

class Cho extends DongVat {
    void keu() {
        System.out.println("Gâu gâu");
    }
}
```

Giải thích:

abstract → chỉ nói “có hành động này”

Chi tiết để lớp con tự làm

👉 Giúp code rõ ràng và dễ mở rộng.

### 3. Tổng kết 4 tính chất OOP
Tính chất	Hiểu đơn giản
Đóng gói	Giấu bên trong, dùng bên ngoài
Kế thừa	Con dùng lại của cha
Đa hình	Cùng lệnh, khác cách làm
Trừu tượng	Chỉ cần biết dùng, không cần biết bên trong
### 4. Một chút chia sẻ cá nhân

Khi mới học OOP, mình từng nghĩ đây là phần khó nhất Java. Nhưng sau khi liên tưởng đến đồ vật ngoài đời, mọi thứ trở nên rất dễ hiểu. OOP giúp code gọn hơn, ít lỗi hơn và dễ sửa hơn rất nhiều.