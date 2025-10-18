---
title: "Bài 1: Giới thiệu cơ bản về lập trình Java"
date: 2025-08-21
draft: false
tags: ["Java", "Lập trình", "Học lập trình"]
categories: ["Lập trình Java"] 
image: "/image/java1.jpg"
---

Java là một trong những ngôn ngữ lập trình phổ biến và mạnh mẽ nhất trên thế giới. <!--more-->  
Được phát triển bởi **Sun Microsystems** (nay thuộc **Oracle**), Java nổi tiếng với khẩu hiệu **“Write Once, Run Anywhere”** – viết một lần, chạy được ở mọi nơi.

---

## 🧠 Java là gì?
Java là ngôn ngữ lập trình **hướng đối tượng (OOP)**, có thể chạy trên nhiều nền tảng khác nhau như Windows, macOS, Linux, và thậm chí cả trên điện thoại Android.  
Điểm đặc biệt của Java là nó **biên dịch mã nguồn thành bytecode**, chạy trên **Java Virtual Machine (JVM)**, giúp chương trình hoạt động độc lập với hệ điều hành.

---

## ⚙️ Tại sao nên học Java?
- Dễ học và có cú pháp rõ ràng.  
- Ứng dụng rộng rãi trong phát triển **web, app Android, phần mềm doanh nghiệp, game, IoT, AI**, v.v.  
- Cộng đồng lớn, tài liệu học phong phú, dễ tìm trợ giúp.  
- Là nền tảng để hiểu sâu hơn về **OOP** và tư duy lập trình.  

---

## 🧩 Cấu trúc cơ bản của một chương trình Java
Ví dụ đơn giản về chương trình Java đầu tiên:

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Xin chào thế giới!");
    }
}
