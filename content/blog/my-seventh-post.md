---
title: "Bài 7: Lập trình mạng TCP & UDP trong Java"
date: 2025-08-27
draft: false
tags: ["Java", "Lập trình mạng", "TCP", "UDP"]
categories: ["Lập trình Java"]
image: "/image/java7.jpg"
---

Khi làm việc với các ứng dụng thực tế, đặc biệt là những ứng dụng cần **truyền dữ liệu giữa các máy tính**, bạn sẽ cần đến **lập trình mạng (Network Programming)**. <!--more-->  
Trong Java, hai giao thức phổ biến nhất để giao tiếp qua mạng là **TCP** và **UDP**.  
Hiểu rõ sự khác biệt và cách triển khai giúp bạn viết code dễ hơn, ổn định hơn và tránh lỗi khó chịu khi chạy ứng dụng mạng.

---

## 🌐 1. Tổng quan về TCP và UDP

| Giao thức | Đặc điểm chính | Ứng dụng thực tế |
|------------|----------------|------------------|
| **TCP (Transmission Control Protocol)** | - Có kết nối (Connection-oriented)<br>- Đảm bảo dữ liệu đến đúng thứ tự, không mất gói<br>- Tốc độ chậm hơn UDP một chút | Truyền file, chat app, web server |
| **UDP (User Datagram Protocol)** | - Không kết nối (Connectionless)<br>- Dữ liệu gửi nhanh, có thể mất gói<br>- Không đảm bảo thứ tự | Streaming, game online, voice chat |

💡 *TCP giống như gửi thư bảo đảm — chắc chắn đến nơi, nhưng chậm hơn một chút.*  
💡 *UDP thì như gửi tin nhắn nhanh — đến sớm, nhưng không chắc mọi gói đều đến.*

---

## ⚙️ 2. Cách lập trình TCP trong Java

### 🖥️ Ví dụ: Giao tiếp Client – Server với TCP

#### 🧩 Server (TCPServer.java)
```java
import java.io.*;
import java.net.*;

public class TCPServer {
    public static void main(String[] args) {
        try {
            ServerSocket serverSocket = new ServerSocket(8888);
            System.out.println("Server đang lắng nghe trên cổng 8888...");

            Socket socket = serverSocket.accept();
            System.out.println("Client đã kết nối!");

            BufferedReader input = new BufferedReader(new InputStreamReader(socket.getInputStream()));
            PrintWriter output = new PrintWriter(socket.getOutputStream(), true);

            String message = input.readLine();
            System.out.println("Nhận từ client: " + message);

            output.println("Xin chào client, server đã nhận được tin nhắn!");

            socket.close();
            serverSocket.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}

💻 Client (TCPClient.java)
import java.io.*;
import java.net.*;

public class TCPClient {
    public static void main(String[] args) {
        try {
            Socket socket = new Socket("localhost", 8888);

            BufferedReader input = new BufferedReader(new InputStreamReader(System.in));
            PrintWriter output = new PrintWriter(socket.getOutputStream(), true);
            BufferedReader response = new BufferedReader(new InputStreamReader(socket.getInputStream()));

            System.out.print("Nhập tin nhắn gửi đến server: ");
            String message = input.readLine();
            output.println(message);

            System.out.println("Phản hồi từ server: " + response.readLine());

            socket.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
✅ Chạy thử:

Chạy TCPServer trước.

Sau đó chạy TCPClient.

Gõ tin nhắn từ client → server nhận → gửi phản hồi lại.

📡 3. Cách lập trình UDP trong Java

Khác với TCP, UDP không cần tạo kết nối giữa client và server.

🧩 Server (UDPServer.java)
import java.net.*;

public class UDPServer {
    public static void main(String[] args) {
        try {
            DatagramSocket socket = new DatagramSocket(8888);
            byte[] buffer = new byte[1024];

            System.out.println("UDP Server đang chạy...");

            DatagramPacket packet = new DatagramPacket(buffer, buffer.length);
            socket.receive(packet);

            String message = new String(packet.getData(), 0, packet.getLength());
            System.out.println("Nhận từ client: " + message);

            socket.close();
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
💻 Client (UDPClient.java)
import java.net.*;

public class UDPClient {
    public static void main(String[] args) {
        try {
            DatagramSocket socket = new DatagramSocket();
            InetAddress address = InetAddress.getByName("localhost");

            String message = "Xin chào UDP Server!";
            byte[] buffer = message.getBytes();

            DatagramPacket packet = new DatagramPacket(buffer, buffer.length, address, 8888);
            socket.send(packet);

            System.out.println("Gửi dữ liệu thành công!");
            socket.close();
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
✅ Chạy thử:

Mở terminal đầu tiên → chạy UDPServer.

Mở terminal thứ hai → chạy UDPClient.

Server sẽ nhận được chuỗi "Xin chào UDP Server!".