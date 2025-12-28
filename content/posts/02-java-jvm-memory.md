# Bài 2: Quản lý bộ nhớ trong Java: Stack vs Heap và cách JVM hoạt động

Tại sao Java lại mạnh mẽ? Câu trả lời nằm ở Java Virtual Machine (JVM).

### 1. Cấu trúc bộ nhớ JVM
* **Stack:** Lưu trữ các biến cục bộ và lời gọi hàm. Mỗi thread có một Stack riêng.
* **Heap:** Lưu trữ tất cả các đối tượng (Objects) và biến instance. Đây là vùng nhớ chung.



### 2. Garbage Collection (GC)
Java tự động giải phóng bộ nhớ thông qua GC. Nó tìm các đối tượng không còn được tham chiếu trong Heap và xóa chúng.

### 3. Lời khuyên tối ưu
* Hạn chế tạo đối tượng dư thừa trong vòng lặp.
* Hiểu rõ về `Memory Leak` khi các đối tượng không còn dùng nhưng vẫn bị tham chiếu.