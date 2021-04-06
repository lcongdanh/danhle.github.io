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

Server

Đầu tiên là set up ServerSocket và chờ kết nối từ Client

Khi accept client để kết nối

```
	public void go() {
		ServerSocket serverSocket = null;
		try {
			serverSocket = new ServerSocket(portNumber);
			System.out.println("Server has started at port " + serverSocket.getLocalSocketAddress());
			while(true){
				Socket clientSocket = serverSocket.accept();
				ClientJob clientJob = new ClientJob(clientSocket);
				Thread thread = new Thread(clientJob);
				thread.start();
			}
		} catch (Exception e) {
			e.printStackTrace();
		}
	} // close go method
```