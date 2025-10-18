---
title: "Bài 5: Vòng lặp trong Java"
date: 2025-08-25
draft: false
tags: ["Java", "Lập trình", "Học lập trình"]
categories: ["Lập trình Java"]
image: "/image/java5.jpg"
---

Ở các bài trước, bạn đã học cách chương trình **ra quyết định** bằng cấu trúc điều kiện. <!--more-->  
Tuy nhiên, trong thực tế, nhiều khi chúng ta cần **lặp lại một hành động nhiều lần** — ví dụ như in danh sách, tính tổng dãy số, hoặc duyệt qua dữ liệu.  
Đó chính là lúc **vòng lặp (loop)** phát huy sức mạnh trong lập trình Java.

---

## 🔁 Vòng lặp là gì?

**Vòng lặp (loop)** cho phép chương trình **thực hiện lại một khối lệnh nhiều lần** cho đến khi điều kiện không còn đúng.  
Nói cách khác, thay vì viết cùng một lệnh hàng chục lần, ta chỉ cần viết một vòng lặp để máy tự làm việc đó.

---

## 🌀 Các loại vòng lặp trong Java

### 1. `for` – vòng lặp có giới hạn rõ ràng
Dùng khi bạn **biết trước số lần lặp**.

Cú pháp:
```java
for (khởi_tạo; điều_kiện; bước_nhảy) {
    // Khối lệnh được thực thi
}
