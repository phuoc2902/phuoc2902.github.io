---
title: "AIVA – Trợ lý AI cá nhân hỗ trợ ghi âm, tóm tắt và trò chuyện thông minh"
draft: false
tags: ["AI", "Python", "Streamlit", "Project"]
author: ["Trương Huy Phước"]

cover:
    image: "/images/projects/aiva/cover.png"
    alt: "AIVA – Trợ lý AI cá nhân"
    caption: "Dự án AI cá nhân – AIVA"
    relative: false
---

### 1. Giới thiệu

Trong quá trình học tập và làm việc nhóm, mình nhận ra một vấn đề khá quen thuộc:  
👉 **Cuộc họp thì nhiều, ghi âm thì có, nhưng rất ít khi nghe lại đầy đủ vì tốn thời gian.**

Từ đó, mình bắt đầu xây dựng **AIVA (Artificial Intelligence Virtual Assistant)** – một **trợ lý AI cá nhân** có thể:
- Ghi nhận nội dung cuộc họp
- Tóm tắt lại những ý chính
- Và cho phép người dùng hỏi trực tiếp AI về nội dung đó

AIVA không phải là một chatbot đơn thuần, mà là một công cụ hỗ trợ học tập và làm việc thực tế.

---

### 2. AIVA làm được những gì?

### 2.1 Đăng nhập và quản lý người dùng

AIVA có hệ thống **đăng ký / đăng nhập** riêng cho từng người dùng.  
Mỗi user sẽ có dữ liệu và lịch sử làm việc độc lập.

### 2.2 Ghi âm và tóm tắt cuộc họp bằng AI

Người dùng chỉ cần upload file audio (mp3, wav, m4a), AIVA sẽ tự động:

Gửi audio lên AI

Phân tích nội dung

Tóm tắt cuộc họp bằng tiếng Việt

Liệt kê các task cần làm
```python
prompt = "Bạn là AIVA. Hãy tóm tắt cuộc họp này và liệt kê task bằng tiếng Việt."
response = client.models.generate_content(
    model="gemini-2.5-flash",
    contents=[gemini_file, prompt]
)
```

👉 Đây là phần mình thích nhất trong dự án, vì thấy rõ AI giải quyết vấn đề thật.

### 2.3 Trò chuyện trực tiếp với AIVA

Ngoài việc tóm tắt, người dùng còn có thể chat trực tiếp với AIVA để hỏi bất cứ điều gì.
```python
response = client.models.generate_content(
    model="gemini-2.5-flash",
    contents=prompt
)
```

Ví dụ:

“Cuộc họp hôm nay nói về gì?”

“Task quan trọng nhất là gì?”

“Tóm tắt ngắn gọn lại giúp mình”

👉 Trải nghiệm giống như có một trợ lý riêng.

### 2.4 Lưu trữ dữ liệu bằng SQLite

Mình sử dụng SQLite để lưu:

Tài khoản người dùng

Lịch sử các cuộc họp

Nội dung tóm tắt
```python
c.execute('''
CREATE TABLE IF NOT EXISTS meeting_history
(username TEXT, file_name TEXT, summary TEXT)
''')
```

👉 Đủ nhẹ, dễ dùng và phù hợp với dự án cá nhân.

### 3. Công nghệ sử dụng trong dự án

Trong dự án AIVA, mình sử dụng:

Python – ngôn ngữ chính

Streamlit – xây dựng giao diện nhanh

Google Gemini API – xử lý AI

SQLite – lưu trữ dữ liệu

dotenv – bảo mật API key

👉 Mục tiêu là làm được sản phẩm chạy thật, không chỉ demo.

### 4. Một số hình ảnh minh họa dự án

(Bạn thay ảnh thật của bạn vào các đường dẫn bên dưới)

### 5. Điều mình học được từ dự án AIVA

Qua dự án này, mình học được:

Cách xây dựng một hệ thống AI hoàn chỉnh

Kết nối AI API vào ứng dụng thực tế

Tư duy chia module rõ ràng (auth / audio / chat)

Hiểu hơn về cách AI hỗ trợ con người trong công việc

Đây là dự án giúp mình tự tin hơn khi tiếp cận các bài toán AI thực tế.

### 6. Hướng phát triển trong tương lai

Trong thời gian tới, mình muốn nâng cấp AIVA thêm:

Ghi âm trực tiếp bằng microphone

Lưu toàn bộ lịch sử hội thoại

Xuất báo cáo PDF sau mỗi cuộc họp

Tối ưu AI ghi nhớ ngữ cảnh dài hơn

### 7. Tổng kết

AIVA là một dự án AI cá nhân mà mình đầu tư nghiêm túc cả về ý tưởng lẫn kỹ thuật.
Thông qua dự án này, mình muốn hướng tới việc ứng dụng AI để giải quyết vấn đề thật, đặc biệt trong học tập và làm việc nhóm.

Nếu bạn quan tâm hoặc muốn trao đổi thêm về dự án, mình rất sẵn sàng kết nối.


Ý tưởng thêm video demo trực tiếp vào bài viết rất hay, nó giúp người xem hình dung rõ ràng nhất cách AIVA hoạt động mà không cần phải chuyển tab.

Vì đây là dự án cá nhân của bạn, tốt nhất là bạn nên tự quay một đoạn màn hình (Screen record) rồi upload lên YouTube cá nhân. Dưới đây là cách bạn thêm Phần 8 vào file Markdown để video hiển thị ngay trên trang (nhúng video):

### 8. Demo sản phẩm
Dưới đây là video ngắn giới thiệu cách thức vận hành của AIVA, từ khâu tải file âm thanh đến khi nhận được bản tóm tắt từ Gemini:

{{< youtube EG9Vl-CtKkQ >}}

<div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden;"> <iframe src="https://www.youtube.com/embed/HceKUGguai0" style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; border:0;" allowfullscreen title="AIVA Demo Video"></iframe> </div>

