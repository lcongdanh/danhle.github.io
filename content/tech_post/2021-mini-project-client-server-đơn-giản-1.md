---
title: Mini Project Client - Server đơn giản
date: 2021-04-12T13:21:54.066Z
draft: false
tags:
  - tech
  - project
  - Java
author: Le Danh
comments: true
share: true
type: post
---
Mình đã học java được khoảng 1 tháng với cuốn Java Head First. Mình đã viết lại phần mềm từ chương 15 của Head First và tham khảo thêm [repo](https://gist.github.com/fliedonion/1002293af6fd043fbd6e729c13018562) này, có cải tiến (ồ! chắc hẳn là “cải tiến”) và chỉnh xửa chút ít theo ý mình. Phần mềm chat gồm có các Clients để gửi tin đến một Server và để Server gửi lại cho các Clients (có thể có nhiều Clients).

![Client - server chat demo](uploads/clientserver.png)

Mình có sử dụng: Thread, ActionListener, GUI cơ bản, Networking Socket. Nghe hoành tráng chứ đơn giản thôi.

**Client**

Đầu tiên là nhận userName từ người dùng gõ vào termial

Lấy userName đó để đặt tên cho chatbox frame và cũng dùng userName đó gửi tới server để biết người gửi là ai

Tiếp tới là setup GUI

Set up network để client có thể gửi tin và nhận tin

Tiếp theo ta set up một cái ActionListener để thực hiện lệnh mỗi lần user ấn send.

Mình tạo thêm một Thread để chờ khi Server gửi tin đến sẽ hiển thị ở showTextArea, ShowTextArea và sendTextArea lần lượt là instance của JTextArea và JtextField.

Tại sao lại cần thêm Thread? Vì 2 thread có thể hoạt động song song với nhau, trong trường hợp này mình có thể vừa gửi tin và nhận tin cùng một lúc.

**Server**

Ở server sẽ hơi phức tạp hơn một chút, quan trọng nhất là chỗ này: mỗi lần có một client kết nối với server mình sẽ tạo ra một thread mới cho client đó, khi một trong các client này gửi tin đến thì server sẽ tự động gửi tin đó đến tất cả các client bao gồm cả client gửi tin.

Đầu tiên là mở infinite loop để chờ client kết nối, khi đó mình tạo một thread cho client đó, đồng thời cũng lưu lại thread đó(thực sự là lưu lại instance của class của thread đó) ở server bằng cách sử dụng ArrayList.

Ở client Thread, khi có tin nhắn từ một client nào đó gửi tới, nơi đây sẽ tiếp nhận và gửi cho tất cả cái client trong ArrayList mà mình đã lưu lại ở mainThread.

repo Mini Project của mình ở [đây](<https://github.com/lcongdanh/MiniProject_Client_Server>)

Nếu bạn không biết bắt đầu đọc code từ đâu hãy bắt đầu từ cách nó chạy tức là bắt đầu từ main rồi cứ theo logic mà đọc tới.

Góp ý cho mình nhé!