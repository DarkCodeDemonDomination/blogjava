---
title: "Bài 6: Mảng (Array) trong Java"
date: 2025-08-26
draft: false
tags: ["Java", "Lập trình", "Học lập trình"]
categories: ["Lập trình Java"]
image: "/image/java6.jpg"
---

Sau khi đã hiểu về **vòng lặp** trong bài trước, hôm nay chúng ta sẽ tìm hiểu một khái niệm cực kỳ quan trọng trong lập trình: **Mảng (Array)**. <!--more-->  
Mảng giúp bạn **lưu trữ và xử lý nhiều giá trị cùng kiểu dữ liệu** chỉ với một biến duy nhất — thay vì phải khai báo hàng chục biến riêng lẻ.

---

## 🧩 Mảng là gì?

**Mảng (Array)** là một cấu trúc dữ liệu dùng để **lưu trữ nhiều phần tử có cùng kiểu dữ liệu**.  
Mỗi phần tử trong mảng được **đánh chỉ số (index)** bắt đầu từ **0**.

Ví dụ: nếu bạn muốn lưu điểm của 5 sinh viên, bạn có thể viết:
```java
int[] scores = {85, 90, 75, 88, 92};
Ở đây:

int[] là kiểu mảng chứa các giá trị kiểu số nguyên (int).

scores là tên mảng.

{85, 90, 75, 88, 92} là 5 phần tử được lưu trong mảng.

Có 2 cách để khai báo mảng:

1. Khai báo và khởi tạo cùng lúc:
int[] numbers = {1, 2, 3, 4, 5};
2. Khai báo trước, khởi tạo sau:
int[] numbers = new int[5]; // mảng có 5 phần tử
numbers[0] = 10;
numbers[1] = 20;
numbers[2] = 30;
numbers[3] = 40;
numbers[4] = 50;
💡 Lưu ý:

Chỉ số phần tử đầu tiên là 0.

Chỉ số phần tử cuối cùng là length - 1.