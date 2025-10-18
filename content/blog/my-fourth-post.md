---
title: "Bài 4: Cấu trúc điều kiện trong Java"
date: 2025-08-24
draft: false
tags: ["Java", "Lập trình", "Học lập trình"]
categories: ["Lập trình Java"]
image: "/image/java4.jpg"
---

Sau khi đã tìm hiểu về **toán tử và biểu thức** trong Java, bước tiếp theo trong hành trình lập trình của bạn là học cách **ra quyết định** trong chương trình. <!--more-->  
Đây chính là lúc chúng ta khám phá **cấu trúc điều kiện (conditional statements)** – công cụ giúp chương trình xử lý linh hoạt theo từng tình huống khác nhau.

---

## 🧩 Cấu trúc điều kiện là gì?

Cấu trúc điều kiện giúp chương trình **kiểm tra một biểu thức logic** và **thực hiện hành động tương ứng** nếu điều kiện đó đúng (hoặc sai).

Ví dụ đời thường:  
> Nếu trời mưa → mang theo ô.  
> Nếu không mưa → không cần mang ô.

Trong lập trình Java, ta diễn tả điều đó bằng lệnh `if` hoặc `if-else`.

---

## ⚙️ Cấu trúc `if` cơ bản

Cú pháp:
```java
if (điều_kiện) {
    // Thực hiện khi điều kiện đúng
}
