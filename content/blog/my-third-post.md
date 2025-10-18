---
title: "Bài 3: Toán tử và biểu thức trong Java"
date: 2025-08-23
draft: false
tags: ["Java", "Lập trình", "Học lập trình"]
categories: ["Lập trình Java"]
image: "/image/java3.jpg"
---

Trong hai bài học trước, bạn đã biết cách khai báo biến và hiểu rõ về các kiểu dữ liệu trong Java. <!--more-->  
Tiếp theo, chúng ta sẽ cùng tìm hiểu một phần rất quan trọng trong lập trình: **toán tử (operator)** và **biểu thức (expression)** — những công cụ giúp chương trình thực hiện tính toán, so sánh và xử lý dữ liệu.

---

## ⚙️ Toán tử là gì?

**Toán tử (Operator)** là ký hiệu đặc biệt dùng để **thực hiện các phép toán** trên một hoặc nhiều giá trị (toán hạng).  
Ví dụ: `+`, `-`, `*`, `/`, `%` là các toán tử số học cơ bản.

Ví dụ đơn giản:
```java
int a = 10;
int b = 5;
int tong = a + b;
System.out.println("Tổng = " + tong);
