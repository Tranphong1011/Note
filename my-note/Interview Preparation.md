
sql vs nosql:
![](https://i.imgur.com/R37oe9L.png)
Các server stack: xampp, lamp, wamp, mamp
![](https://i.imgur.com/UeXfvVw.png)


Các framework cho backend:
## Spring Framework + Spring boot for Java Developers
## Django for Python Developers
## Express.js for JavaScript Developers
## ASP.NET core for .NET developers
## Laravel for PHP Programmers
## Ruby on Rails for Ruby Programmers
## Fiber Framework for Golang Developers
##  CakePHP Framework for PHP Developers
## Flask Framework for Python Developers
## Play Framework for Scala Developers


**Docker** là một nền tảng để cung cấp cách để building, deploying và running ứng dụng dễ dàng hơn bằng cách sử dụng các containers (trên nền tảng ảo hóa)
Build once, run anywhere
![](https://i.imgur.com/KtWCOYZ.png)

### Build

Đầu tiên tạo một dockerfile, trong dockerfile này chính là code của chúng ta. Dockerfile này sẽ được Build tại một máy tính đã cài đặt Docker Engine. Sau khi build ta sẽ có được Container, trong Container này chứa ứng dụng kèm bộ thư viện của chúng ta.

### Push

Sau khi có được Container, chúng ta thực hiện push Container này lên cloud và lưu tại đó.

### Pull, Run

Nếu một máy tính khác muốn sử dụng Container chúng ta thì bắt buộc máy phải thực hiện việc Pull container này về máy, tất nhiên máy này cũng phải cài Docker Engine. Sau đó thực hiện Run Container này.
## Vậy khi nào sử dụng Docker?

-   Triển khai kiến trúc [Microservices](https://topdev.vn/blog/microserices-la-gi/).
-   Khi xây dựng ứng dụng và cần scale một cách linh hoạt.
-   Khi bạn muốn không tốn khá nhiều thời gian để config máy local và server cùng một môi trường để chạy được ứng dụng. Bạn chỉ cần build 1 lần chạy ở nhiều nơi mà thôi.
-   Sản phẩm của công ty bạn cần một cách tiếp cận mới về xây dựng, đẩy lên server, thực thi ứng dụng một cách nhanh chóng dễ dàng.






1. Interface with a team 
- Develop ability to clearly communicate with others
- settle down/mediate conflicts between team members 
- ability to incorporate diverse views and comments, but always for the purpose of project completement
- quickly establish close rapport with co-worker, determine their preferences
- listen actively to there concerns, encourage to share their feelings and problem and come up with nouvel solution
-> finish our project ahead of time/schedule, receive commentation from manager
![Uploading file...nvn1n]()

2. Build a project and support it
-> “thinking 100 steps ahead” but “building 10 steps ahead”
means thinking ahead but not overengineering today

3. A project you worked
- Outline the steps
- to explicitly state the reason of making certain decisions , for what tradeoffs?
- Aware of possible drawbacks and take calculated risks when necessary

4. Mention some projects - On GitHub
- Food Seller Website with HTML, CSS, Javavascript and PHP 
- Book seller with HTML, CSS , JS and PHP (Laravel Framework)
- eCommerce Website with HTML,CSS JS and Nodejs-backend
Database: Postgre and MySQL
-> In the future, I intent to build a website for my mother, Its selling medical drugs website

5. A project that completely failed
- Show what Ive learned
- demonstrate how resilient and able to resolve


https://www.indeed.com/career-advice/interviewing/software-engineering-internship-interview-questions
https://climbtheladder.com/software-developer-intern-interview-questions/

htbỏ công ty: Smartee, Go2Joy, TSB
 công ty nhất định vô: Lotte - học AWS
 , Shinhan, 
 intern fullstack web application
address ko để chi tiết
email : thêm github
skill: chia ra gồm softskill and technical

bổ sung project
full stack web developer likelion để ở Educaltion
Phân hoạt động và thời gian ra thành 2 cột

1. Is JS asyne or syne language?
2. AJAX là gì?
3. Event loop là gì?
4. Call back hill là gì?
5. Promise là gì?
6. Async vs Await?
7. First class function
8. Higher order function


array.every()
array.some()
array.forEach()
array.map()
array.reduce()
array.filter()
array.find()
arrray.findIndex()

JR runtime bao gồm Browser vs NodeJS: node ko có dom
JS engine: V8 chrome
web API bao gồm: Dom api, time api (settimeout-thực thi 1 lần, setInteval - thực thi liên tục) và window api, alert (blocking + đồng bộ)
web API có thể đồng bộ hoặc bất đồng bộ


window ->document-> hmtl -> heading
bản thân window bao gồm luôn cả document
window có vị trí tương đương với alert, nghĩa là alert có vị trí cao hơn cả document

có 2 loại data format: json và xml
dns là 1 danh bạ, lưu data dạng json bao gồm name: ip của website

1. So sánh local storage và section storage
- session storage: nếu ko có thao tác bất kì, sẽ tự out, nghĩa là tắt browser , do đó dữ liệu sẽ bị tắt, hạn mức lưu trữ 10MB
- local storage: lữu trữ dữ liệu vô thời hạn, clear khi và chỉ khi clear history, hạn mức lưu trữ dữ liệu chỉ 5MB, không gửi thông tin lên server
- cookies: Hạn mức lữu trữ tối đa 4kb , có gửi thông tin lên server

2. Các method của local storage

localStorage.getItem('index') : trả về null, hoặc value
localStorage.setItem('index','value') : set index:value : trả về undefined

localStorage.removeItem('index'): trả về undefined


<!doctype html5> : tức có nghĩa là sử dụng phiên bản html mới nhất là 5

`<html lang="en">`: khai báo ngôn ngữ trang web. tối ưu SEO : search engine optimizaton: gồm có thẻ meta(description), href, alt,..

chèn hình ảnh: img, background-img
-> sự khác nhau: trong img có alt, background-img ko có, 

thẻ tự đóng: <img> , <input> : là những thẻ ko thể tự chèn nội dung

a _target="_blank" href ="" : Thuộc tính target dùng để xác định cửa sổ hiển thị cho thẻ liên kết, nghĩa là liên kết sẽ mở trên của sổ hiện tại hay là cửa sổ mới.
▫ _blank thì nó sẽ mở liên kết trên tab mới  
▫ _self thì nó sẽ mở liên kết trên tab hiện tại  
▫ _parent thì nó sẽ mở liên kết tới tab mở tab hiện tại. Ta còn hay gọi là tab cha của tab hiện tại  
▫ _top thì nó sẽ nhảy tới tab hiện tại và thường dùng trong iframe khi muốn thoát khỏi iframe và chạy tới trang gốc luôn.



*** AWS: 


AWS cung cấp rất nhiều service, có những service bạn không mất tiền sử dụng, nhưng chẳng có miếng bánh nào miễn phí phải không các bạn. Các dịch vụ cơ bản của aws như:

-   Compute
-   Storage
-   Database
-   Networking and content delivery
-   Deleloper tools
-   Management Tools
-   Analytics
-   Internet of things
-   Machine learning
-   … etc, bạn có thể đọc thêm tại [đây](https://aws.amazon.com/)

Mỗi dịch vụ lại chia làm nhiều các dịch vụ nhỏ hơn như storage bao gồm các service Simple storage service (S3), Elastic Block Store (EBS), Elastic File System (EFS) … hay database có các service như Aurora, DynamoDB, ElasticCache, RDS(MySql, Sql, Oracle, PostgreSQL, MariaDB), Redshift …
1. AWS là gì? _dịch vụ web của Amazon_. Đơn giản hơn, đây là một dịch vụ điện toán dựa trên đám mây được thiết kế cho các máy chủ của các công ty khác nhau. Vậy _máy chủ có mục đích gì._ Mọi thứ từ lưu trữ dữ liệu đến phân phối nội dung - AWS là một nền tảng đa chức năng và cung cấp rất nhiều dịch vụ cho khách hàng.

2: Sự khác biệt giữa việc dừng và chấm dứt instance là gì?**
Khi dừng một instance, quy trình sẽ tắt theo cách thông thường và sau đó không hoạt động. Tuy nhiên, nếu instance bị chấm dứt, nó sẽ tắt bình thường nhưng sẽ tự xóa sau đó, trừ khi có cách khác.

3. S3 là gì?  **S3** (Simple Storage Service) là viết tắt của _Dịch vụ lưu trữ đơn giản, trực tuyến_ (S3 vì ba từ đều bắt đầu bằng “s”). Nó là một giao diện cho phép lưu trữ và chuyển lượng dữ liệu không giới hạn ở mọi lúc mọi nơi. Mặc dù nghe có vẻ phi thực tế, nhưng nó được sử dụng rộng rãi và được chấp nhận - đặc biệt là khi nói đến DevOps.
4: Nêu một phương pháp truy cập EBS.
Amazon Elastic Block Store (EBS) là một dịch vụ lưu trữ dạng block dễ sử dụng và hiệu năng cao, được thiết kế để sử dụng với Amazon Elastic Compute Cloud (EC2) cho các khối lượng công việc đòi hỏi tốc độ giao dịch và thông lượng cao ở mọi quy mô.

Có một vài phương pháp để truy cập nhưng cách rõ ràng nhất là truy cập trực tiếp vào khu vực.

5: Tỷ lệ mặc định của AWS là horizontal (ngang) thì có thể thay đổi instance theo vertically (dọc) không?**

Bạn có thể làm vậy. Khởi động lại instance sau khi thay đổi tỷ lệ - nếu không, nó sẽ không hoạt động.

6: AMI là gì?**

**AMI** là viết tắt của cụm từ “_Amazon Machine Image_”. Đó là một mẫu mà các nhà phát triển sử dụng để chạy các phiên bản AWS - mẫu này chứa tất cả các thông tin và dữ liệu quan trọng cần thiết để instance hoạt động chính xác.

7. 'EC2' là gì?**

Amazon **EC2** là một “_Elastic Compute Cloud”_. Các nhà phát triển AWS sử dụng nó để khởi chạy các máy chủ ảo. Nó có thể mở rộng và số lượng máy chủ không giới hạn được đưa ra và hoàn hảo cho các công ty, doanh nghiệp lớn!

9: Làm thế nào để bảo mật dữ liệu trên cloud trong khi truyền dữ liệu?**

Cloud cung cấp các **khóa bảo mật** đặc biệt có thể sử dụng để bảo mật dữ liệu trong quá trình chuyển giao. Ngoài ra, có thể thực hiện một số cách tiếp cận nguyên bản hơn cho toàn bộ quá trình và thử chia dữ liệu thành các phần khác nhau và chuyển chúng riêng biệt (tất nhiên là có khóa bảo mật trên mỗi phần).

8: Các EC2 instance có thể sử dụng S3 không?**

EC2 instance có hỗ trợ S3. Điều kiện duy nhất là các instance sử dụng S3 phải được sao lưu cục bộ (trong bộ nhớ cục bộ).


10: Thời gian khởi động một AMI mười phút có bình thường hay không?**

Đó là không bình thường. Thời gian khởi động bình thường cho một AMI là **khoảng năm phút**, mười phút là quá nhiều.

11: Các thành phần chính của AWS là gì?**

Các thành phần chính được AWS sử dụng là:

-   CloudWatch cho phép giám sát tài nguyên AWS và các ứng dụng khách hàng chạy trên cơ sở hạ tầng Amazon.
-   Route 53: Một dịch vụ Cấu trúc đặt tên miền. Nó cho phép đăng ký một tên cho trang web.
-   Dịch vụ email đơn giản Amazon Web Service là một dịch vụ gửi và nhận email có khả năng mở rộng cao. Chủ yếu được sử dụng bởi các nhà phát triển và tổ chức kinh doanh. Nó cung cấp bảo mật nâng cao và quản lý danh tính cho tài khoản AWS. Amazon SES dựa trên đám mây.
-   Elastic Compute Cloud (EC2) cung cấp dịch vụ điện toán. Giao diện dịch vụ web đơn giản của EC2 để có được và định cấu hình dung lượng với ma sát tối thiểu.  friction
-   Elastic Block Store (EBS) là bộ lưu trữ cấp khối được sử dụng với dịch vụ EC2 để lưu trữ dữ liệu liên tục.

12. ## **Amazon S3 Bucket là gì?**

Thùng Amazon S3 (Amazon S3 bucket**)** là tài nguyên lưu trữ đám mây công cộng có sẵn trong Dịch vụ lưu trữ đơn giản (Amazon S3) của Amazon Web Services, một dịch vụ lưu trữ đối tượng. Các thùng Amazon S3, tương tự như các thư mục, lưu trữ các đối tượng, bao gồm dữ liệu và siêu dữ liệu được định dạng của nó.


13. ### **13: Có thể có bao nhiêu ‘buckets’ trên mỗi tài khoản AWS?**

Theo mặc định, có thể tạo tối đa 100 ‘buckets’ cho mỗi tài khoản.

14. ### **T2 instance là gì?**

Phiên bản T2 là loại phiên bản đa dụng, chi phí thấp, cung cấp mức hiệu năng CPU cơ bản với khả năng chạy vượt mức cơ bản khi cần thiết. ới mức giá Phiên bản theo nhu cầu từ 0.0058 USD mỗi giờ, phiên bản T2 là một trong các phiên bản Amazon EC2 có chi phí thấp nhất và là lựa chọn lý tưởng cho hàng loạt ứng dụng đa dụng như các vi dịch vụ, ứng dụng tương tác độ trễ thấp, cơ sở dữ liệu vừa và nhỏ, máy tính bàn ảo, môi trường phát triển, xây dựng và thử nghiệm, kho mã và nguyên mẫu sản phẩm.

15: Các loại instance là gì?**

Các loại instance chính đó là mục đích chung, tối ưu hóa máy tính, tối ưu hóa bộ nhớ, tối ưu hóa lưu trữ, tăng tốc điện toán.
## General Purpose
## Compute Optimized
## Memory Optimized
## Accelerated Computing
## Storage Optimized





HTML ko phải là ngôn ngữ lập trình, mà là ngôn ngữ đánh dấu siêu văn bản
++Sự khác nhau giữa HTTP và HTTPs:

The only difference between the two protocols is that HTTPS uses [TLS] ([SSL]) to encrypt normal HTTP requests and responses, and to digitally sign those requests and responses. Do đó HTTPS bảo mật hơn

HTTP - request
```
GET /hello.txt HTTP/1.1
User-Agent: curl/7.63.0 libcurl/7.63.0 OpenSSL/1.1.l zlib/1.2.11
Host: www.example.com
Accept-Language: en
```

HTTP -respond

```
HTTP/1.1 200 OK
Date: Wed, 30 Jan 2019 12:14:39 GMT
Server: Apache
Last-Modified: Mon, 28 Jan 2019 11:17:01 GMT
Accept-Ranges: bytes
Content-Length: 12
Vary: Accept-Encoding
Content-Type: text/plain

Hello World!
```

HTTPS request - respond :
```
t8Fw6T8UV81pQfyhDkhebbz7+oiwldr1j2gHBB3L3RFTRsQCpaSnSBZ78Vme+DpDVJPvZdZUZHpzbbcqmSW1+3xXGsERHg9YDmpYk0VVDiRvw1H5miNieJeJ/FNUjgH0BmVRWII6+T4MnDwmCMZUI/orxP3HGwYCSIvyzS3MpmmSe4iaWKCOHQ==
```