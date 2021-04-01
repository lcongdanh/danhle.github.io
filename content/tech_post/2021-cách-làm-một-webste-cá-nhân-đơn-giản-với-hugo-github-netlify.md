---
title: Cách làm một webste cá nhân đơn giản với Hugo - Github - Netlify
date: 2021-03-18T14:27:21.507Z
draft: false
tags:
  - "tech_guide_website"
author: Le Danh
comments: true
share: true
type: post
---
## **1. Lưu ý**

Sau nhiều ngày hì hục cuối cùng mình cũng làm xong website mà không tốn 1 đồng nào (chỉ tốn thời gian :D).

Khi đọc bài viết này mình sẽ coi như bạn muốn tạo cho mình một website theo ý của mình và bạn cũng cần hiểu về HTML/CSS, thành phần cơ bản của một trang web, cơ bản thôi không cần quá cao siêu đâu.

Bài viết này không phải là một bài hướng dẫn chi tiết từng bước mà như là một “guide” để cho bạn có cái nhìn bao quát từ đầu đến cuối, để không phải mò mẫm như mình (khổ lắm! Thấy vậy chớ cũng xảy ra nhiều lỗi lắm).

## **2. Sơ qua về quá trình làm**

Tên miền mình lấy miễn phí trên Freenoom - họ free cho mình tối đa 12 tháng mà không cần thông tin cá nhân. Nếu được hãy mua cho một tên miền(domain) với đuôi phổ biến hơn như .com .vn .net .org, giá khoảng một tô phở 210k/năm (rẻ mà :D). Nơi mua thì có rất nhiều, theo mình biết thì có Google Domain, Hostinger, Godaddy,...

Mình dùng static site generator Hugo, nếu bạn chưa biết Hugo là gì, mình sẽ giải thích bên dưới. Còn để dễ hình dung, hãy tưởng tượng thay vì mình tự viết HTML/CSS/JavaScript từ đầu đến cuối, thay vào đó mình cài Hugo và tải theme về là có thể có một website riêng rồi (nghe dễ quá phải không?).

Tiếp đến mình host website trên Github (vì nó miễn phí :D)

Xong rồi ta dùng Netlify để deploy website.

Cuối cùng là set up Netlify CMS luôn (nếu bạn chưa biết CMS là gì hãy xem tiếp nhé!), đây là một trong những lý do mà mình dùng netlify để deploy website.

Đây là [series step by step tutorial](https://www.youtube.com/watch?v=5aajv-2YZYM&list=PL-Kz5P-mYdMgAJDmRJquyMHfdaIOD-3oj) của *Chris Staye*, mình làm theo hướng dẫn của cậu này, khá cụ thể và dễ hiểu.

## **3. Các bước cụ thể.**

### **3.1. Hugo**

Hugo là gì? - Như mình nói ở trên Hugo là static site generator, để không phải viết một trang web từ đầu, ta chỉ cần cài Hugo và tải theme về rồi sửa nó theo ý thích là sẽ có một trang web như ý rồi.

Bên cạnh Hugo cũng có những static site generator khác như: Gatby, Middleman, etc.

![diference kind of static site generators](uploads/sitegenerators.png)

Mình chọn Hugo vì có nhiều theme và tuorials. Hugo khá phổ biến nên lỡ có bị lỗi\[không “lỡ” gì cả nhất định sẽ có lỗi :))] trong quá trình làm mình cũng dễ tìm được cách giải quyết hơn.

Bạn tạo một folder rồi cài Hugo vào đó - chỗ này như là thư mục gốc (root directory) của website, xong Hugo sẽ tạo ra một số folder có cấu trúc trông như thế này đây:

![Hugo folder](uploads/rootdirectory.png)

Khi bạn chưa tải theme về thì sẽ chưa có thư mục theme như trên hình. Sau khi cài thêm về, bạn vào thư mục theme bạn sẽ thấy cấu trúc file của theme giống với root directory.

Cấu trúc thư mục của root và theme giống nhau để làm gì ? (Điều này quan trọng lắm đây).

Vì nếu bạn cần sửa theme không nên sửa trực tiếp ở thư mục theme mà sửa bên ngoài thư mục root, để root sẽ viết chồng (override) lên theme. Và thêm nữa lỡ bạn có quên hay nhầm gì đó thì có thể quay lại thư mục theme xem lại hoặc copy lại file gốc từ thưc mục theme mang ra root.

![Hugo Themes](uploads/hugothemes.png)

Theme trên Hugo có rất nhiều tùy theo nhu cầu mà chọn. Bạn nên hình dung website của mình sẽ trông như thế nào trước, sau đó chọn gần nhất với nó để đỡ mắc công sửa (lười là căn bệnh quốc dân mà, đừng ngại :D)

### **3.2. Host website trên Github.**

Với chức năng Github pages ta có thể host một website miễn phí trên đó.

![Github pages](uploads/githubpages.png)

Thực ra bạn cũng có thể deploy website của bạn trên Github luôn nhưng vì Netlify có CMS (content management system) và có nhiều theme để lựa chọn.

### **3.3. Public website bằng Netlify.**

Ở bước này bạn cần lưu ý khi public website và nhập domain cá nhân xong thì netlify cần khoảng 15 – 30p để public website, nên hãy kiên nhẫn đợi đấy (thực ra không kiên nhẫn thì cũng không làm gì được người ta đâu :D).

### **3.4. Add netlify cms vào website của bạn.**

[](<>)Khi bạn add cms vào website của mình bạn cần làm theo những [bước như thế này](<https://www.netlifycms.org/docs/add-to-your-site/>), mà có một đều cần chú ý là xem kỹ từ đầu tới cuối (mình làm sót bước “Add the Netlify Identity Widget” cũng mất một ít thời gian mình mới tìm ra).

Netlify cms của mình trông như thế này:

![Netlify CMS](uploads/netlifycms.png)

nếu bạn chưa biết thì CMS, thì nó là chỗ để bạn edit nội dung trước khi đăng lên website, mọi thứ sẽ tiện lợi hơn rất nhiều nếu dùng cms.
## **4. Lưu ý khi sử dụng git.**
Nếu bạn có sử dụng Editorial Workflow trong Netlify CMS, thì lưu ý là khi bạn edit một bài post bằng cms thì netlify sẽ tạo ra một branch trong repo của bạn, khi bạn edit xong bài post và click publish thì branch đó cũng tự merge vào main branch. Lưu ý điểm này để merge khi cần thiết và tránh bị lỗi.
## **5. Tổng kết - Kinh nghiệm.**

Đây là sơ bộ toàn bộ quá trình, mong bạn đã hình dung ra được mình cần làm gì, có xem tutorial thì cũng sẽ dễ tiếp thu hơn.

Với mình, chỉ cần một trang web đơn giản, nên mình chỉ cần làm được ra sản phẩm ưng ý thôi không cần phải đầu tư học quá nhiều. Hãy để dành thời gian quý báu làm việc khác(xem video mèo trên facebook chẳng hạn).

Trong quá trình làm, bạn nhiều khả năng sẽ giống mình, gặp nhiều lỗi. Đừng rối lên nhé! bình tĩnh. Nhiều người sử dụng rồi nên người ta cũng đã gặp lỗi như bạn, hãy phân tích vấn đề ở đâu để từng bước giải quyết nó. Stackoverflow và [Hugo forum](https://discourse.gohugo.io/t/hugo-as-static-forum-generator/10733) là hai nơi mình nhận được nhiều giúp đỡ nhất.