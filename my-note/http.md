giao thức để cho phép tương tác giữa client và servers
client sent HTTP request to server ------ server return response to the client

++ get: GET is used to request data from a specified resource.
dữ liệu truyền vào chính đường link URL
Không được dùng GET để gửi thông tin sensitive
/test/demo_form.php?***name1=value1&name2=value2***
-   GET requests can be cached (dự trữ cho sử dụng tương lai)
-   GET requests remain in the browser history
-   GET requests can be bookmarked
-   GET requests should never be used when dealing with sensitive data
-   GET requests have length restrictions
-   GET requests are only used to request data (not modify)

++ post: send data to a server to create/update a resource.
The data sent to the server with POST is stored in the request body of the HTTP request

POST /test/demo_form.php HTTP/1.1  
Host: w3schools.com  
  
name1=value1&name2=value2


-   POST requests are never cached
-   POST requests do not remain in the browser history
-   POST requests cannot be bookmarked
-   POST requests have no restrictions on data length


++ put: giống post nhưng put mang tính idempotent. Nghĩa là:
cùng gọi PUT request sẽ trả cùng kết quả
cùng gọi POST trả kết quả y chang nhau nhiều lần

++ head: giống get nhưng ko có response body

++ delete: xóa  specified resource