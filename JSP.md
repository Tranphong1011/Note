Jsp là view để cho các bạn có thể thấy được

Sau khi lấy data từ database lên, để có thể truyền nội dung data đó ra ngoài jsp chúng ta cũng cần 1 công cụ để làm và cụ thể công cụ đó chính là Servlet

**JSP** là một kiểu Java servlet được thiết kế để tạo ra giao diện người dùng cho một ứng dụng Java web

-> Jsp chính là view còn servlet chính là server để nhận data từ view cũng như truyền data ra view từ database. Tuy nhiên 1 mình servlet không thể nào làm việc được, nó cần rất nhiều thứ khác bổ trợ như: jdbc, jpa, hibernate ... để truy vấn giữ liệu
![[Pasted image 20230324101946.png]]

Vậy để học JSP cần chuẩn bị những gì? Đó là:

-   Java core.
-   HTML.
-   Java Web Server, chẳng hạn như Apache Tomcat.

---------
servlet (Java Web Server)
Vòng đời của 1 servlet
1.  Tải lớp **Servlet** vào bộ nhớ.
2.  Tạo đối tượng **Servlet**.
3.  Gọi phương thức **init()** của **Servlet**.
4.  Gọi phương thức **service()** của **Servlet**.
5.  Gọi phương thức **destroy()** của **Servlet**.

control F10 để lựa chọn hình thức update 