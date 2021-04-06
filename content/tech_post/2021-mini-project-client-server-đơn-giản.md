---
title: Mini Project Client - Server đơn giản
date: 2021-04-06T12:15:35.541Z
draft: true
tags:
  - tech
  - project
  - Java
author: Le Danh
comments: true
share: true
type: post
---
Mình sẽ tạo ra một client đơn giản gửi text đến server và hiện thị đoạn text đó ở server.

# Server

Đầu tiên là set up ServerSocket và chờ kết nối từ Client

`serverSocket = new ServerSocket(portNumber);`

Accept Client kết nối với Client và taọ ra Socket để kết nối lâu dài với Client

`Socket clientSocket = serverSocket.accept();`

Tiếp đến ta tạo instance of Inner Class ClientJob - class này để tạo InputStreamReader và BufferedReader nhằm chuẩn bị đọc tin nhắn từ Client

Tất cả mình để vào ClientJob constructor

```java
public ClientJob(Socket clientSocket) {
  try {
	socket = clientSocket;
    InputStreamReader isReader = new InputStreamReader(socket.getInputStream());
	reader = new BufferedReader(isReader);
	System.out.println("Waiting for client's message");
  } catch (Exception e) {e.printStackTrace();}
}
```

Cũng ở Inner Class ClientJob mình để phần code hiển thị tin nhắn lên terminal trong run()

```
@Override
public void run() {
  String message;
  try {
    while((message = reader.readLine())!= null){
      System.out.println("message: " + message);
	}
  } catch (Exception ex) {ex.printStackTrace();}
}
```