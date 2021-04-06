---
title: Mini Project Server - Client đơn giản
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

Server

Đầu tiên là set up ServerSocket và chờ kết nối từ Client

`serverSocket = new ServerSocket(portNumber);`

Khi accept Client để kết nối mình taọ ra Socket để kết nối lâu dài với Client

`Socket clientSocket = serverSocket.accept();`

Tiếp đến là tạo instance of inner Clas ClientJob - class này để