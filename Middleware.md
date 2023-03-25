Connect Cissco
Staging
Test postman cho stagin;
[https://stg-gecp-middleware.amorepacific.com/middleware/api/getUserData](https://stg-gecp-middleware.amorepacific.com/middleware/api/getUserData)


https://stg-gecp-middleware-adm.amorepacific.com/ap-admin/main/users/signin.fo
![[Pasted image 20230222131030.png]]
username: test01
password: password

đăng nhập git: https://gitlab.apdigit.tech/
Gitlab 계정 아이디 : tranthanh.cj 
Gitlab 계정 패스워드: h!EwUxN9Wk

Production
https://gecp-middleware-adm.amorepacific.com/ap-admin/main.fo?lang=en#
username: test01
password: password


Connect database: sử dụng OpenVPN
url: jdbc:mysql://apse1-dspdstg-gecp-mysql-01.cqfcqogsoebk.ap-southeast-1.rds.amazonaws.com:3368/gecpstg?characterEncoding=utf8  
username: gecpown  
password: amore@2021

url: jdbc:mysql://apse1-apprd-gecp-mysql-01.ccv7hpoxvym6.ap-southeast-1.rds.amazonaws.com:3368/gecpprd?characterEncoding=utf8
username: gecpown
password: gecpown!23

    url: jdbc:mysql://localhost:3306/gecpstg?characterEncoding=utf8
    username: root
    password: Phong093528@


Đăng nhập email: 
https://ap-on.amorepacific.com/
ID: AC932196 
Pass: cjons932196

Đăng nhập vdi:
http://coa-vdi.amorepacific.com
ID: AC932196
Pass: Theguardian1011

Đăng nhập vào mạng PRD:
ID: AC932196 
Pass: Amore123!@#

C:\Users\ttpho\OneDrive\Documents\dumps\Dump20230224.sql


wiki-digit
http://wiki-digit.amorepacific.com:8090/display/amore12345/Setup+process
ID: AC932196 
Pass: cjons932196

đăng nhập ca-pam:
ID: AC932196 
Pass: cjons932196

tài khoản oracle:
username: ttphong1011@gmail.com
password: Phong093528@

jira:
http://jira-digit.amorepacific.com:8080/projects/ITO0310/issues/ITO0310-54?filter=allopenissues
ID: AC932196 
Pass: cjons932196


realtime intermax PRD:
http://172.28.1.139:8083/intermax/RTM/
아이디 : AC932196
비밀번호 : Amore123!@#

realtime intexmax STG:
http://172.28.0.49:8082/intermax/RTM/
아이디 : AC932196
비밀번호 : Amore123!@#

it help desk:
https://itservice.amorepacific.com/hc/ko

daily monitoring:
http://wiki-digit.amorepacific.com:8090/display/amore12345/Daily+Monitoring

format json:
https://jsonformatter.org/

Thông tin được gửi đến 1 nguồn, sau đó trả về phía client được xem là 1 MIME media type ở trong phần header của HTTP
Sử dụng Consumes và Produces để specify loại MIME nào mà 1 resource có thể respond hoặc produce
@Produce chỉ định loại MIME 1 resource có thể produce hoặc trả về khách hàng Có 2 mức: class và method.
Nếu không có method có thể tạo ra MIME trong request của client, thì lỗi 406 Not Acceptable

```java
@Path("/myResource")
@Produces("text/plain")
public class SomeResource {
	@GET
	public String doGetAsPlainText() {
		...
	}

	@GET
	@Produces("text/html")
	public String doGetAsHtml() {
		...
	}
}
```
The doGetAsPlainText method defaults to the MIME media type of the @Produces annotation at the class level. The doGetAsHtml method's @Produces annotation overrides the class-level @Produces setting, and specifies that the method can produce HTML rather than plain text.


@Consumes: để specify loại MIME media types nào mà một resource có thể consume từ phía client. Có 2 mức: class và method. Nếu resource mo thể consume được MIME từ client request thì sẽ trả về loiix 415 Unsupported Media Type
```java
@Path("/myResource")
@Consumes("multipart/related")
public class SomeResource {
	@POST
	public String doPost(MimeMultipart mimeMultipartData) {
		...
	}

	@POST
	@Consumes("application/x-www-form-urlencoded")
	public String doPost2(FormURLEncodedProperties formData) {
		...
	}
}
```
The doPost method defaults to the MIME media type of the @Consumes annotation at the class level. The doPost2 method overrides the class level @Consumes annotation to specify that it can accept URL-encoded form data.

Kiểu dữ liệu Hashmao tồn tại dưới dạy keyvalue
```java
HashMap<String, String> capitalCities = new HashMap<String, String>();
```

ObjectMapper provides functionality for reading and writing JSON

```
aPIInfoList có dạng Map<String,Object>
aPIUserList có dạng Map<String,Object>
aPIUseList có dạng List<HashMap>
```

Tìm hiểu thuật ngữ Apache Tomcat, Servelet:
Servelet:
Công nghệ Servlet được sử dụng để tạo ra ứng dụng web (nằm ở phía máy chủ và tạo ra trang web động). Sử dụng Servlet, bạn có thể thu thập thông tin đầu vào từ người dùng thông qua các trang web, hiển thị các bản ghi từ một cơ sở dữ liệu hoặc một nguồn khác.
JSP thường được **làm view trong ứng dụng mvc pattern**. Thực ra, JSP vẫn có thể  đáp ứng những yêu cầu khác nhưng để thuận tiện cho việc debug hay tái sử dụng các đoạn mã thì người ta thường dùng làm view còn servlet sẽ làm controller

```
aPIInfoList = {aPIID: Map<String, Object>,............}
tempAPIInfo = {"EXT_OPEN_YN":"1"}
```
![[Pasted image 20230223163434.png]]
Attribute  có thể được thiết lập và GET từ một trong những phạm vi sau đây:
1.  request
2.  session
3.  application
![[Pasted image 20230223172721.png]]

```
tempAPIUser = {"IP_LIM_YN": "0", "AUTH_KEY":authKey, "ALLW_IP": ...}
```

```
private Map<String, Object> aPIInfoList = null;  
private Map<String, Object> aPIUserList = null;  
private List<HashMap> aPIUseList = null;
```
Shortcut mở task manager: Ctrol- Shift-ESC

users cho mysql:
usename: phong
pass: Phong093528@

username: root
pass: Phong093528@

Cách sử dụng git.
Tạo 1 thư mục folder, vô trong thư mục này, click chuột phải và chọn git bash
-B1: Clone về , trên nhánh main, sử dụng git clone + https (xem trên git/git lab)
-B2:  cd vào thư mục vừa mới tải về: cd ap-commerce/
-B3: check out nhánh làm việc của mình: git checkout dev_vn
-B4: cuối cùng là pull về (tức là pull nhánh dev_vn về): git pull pul

Chú ý:
== WAS ==
Home directory : /data/was/tomcat9

== WEB == 
Home directory : /data/web/apache

Command liệt kê các file trong directory: ls

Liệt kê các file kể cả những file có dấu chấm hoặc 2 chấm đầu: ls -a
![[Pasted image 20230227153632.png]]

Liệt kê các file và phân loại: `ls -la`
hoặc `ll`

ctrol + z để stop view
ctrol + c để ngưng quá trình quét dữ liệu 
Các cách để view file : view + file (recommend) / vim + file

Chạy các process trong linux: top , thoát chạy: q
Chú ý các lệnh sau:
```
zgrep -C 5 "External IF URL" catalina.out-2023-02-25-log.gz 
-> filter các lỗi trong dấu "" , C - Center (trên 5 dưới 5) , A - After(Dưới 5), B - Before (Trên 5); 5- số dòng hiển thị

grep -C 10 "2023-02-28" catalina.out | grep "ERROR" : filter 2 lần

zcat catalina.out-2023-02-25-log.gz | tail -n10 > test.txt
-> Đọc file log.gz , lấy 10 dòng cuối cùng, sau đó lưu vào file test.txt
Chú ý:
Khi đọc file test: 
->cat test.txt
khi xóa file test: 
-> dùng lệnh rm -rf test.txt

zcat catalina.out-2023-02-25-log.gz | head -n10
-> Đọc file log.gz nhưng lấy 10 dòng đầu tiên

gzip -d catalina.out-2023-02-26-log.gz
-> Giải nén file zip

tail/head -n10 catalina.out-2023-02-26-log
Đọc file log đối với những file đã bị giải nén rồi

(Chú ý: thay vì đánh hết tên file, ta có thể đánh vài từ đầu s, sau đó nhấn Tab hoặc click chuột phải vào tên file có trong ls)


```
![[Pasted image 20230228141715.png]]
 10h và 18h (giờ server, tức 9h và 17h Việt Nam)
<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN"> <html><head> <title>503 Service Unavailable</title> </head><body> <h1>Service Unavailable</h1> <p>The server is temporarily unable to service your request due to maintenance downtime or capacity problems. Please try again later.</p> </body></html>

![[Pasted image 20230228155517.png]]

**504** gateway time out **là** một **lỗi** do server máy chủ không phản hồi trong một thời gian nhất định.

Cách debug:
Step over: F8
Step into: F7
Step out: Shift F8
Run to cursor: F9
Evaluate Expression: Alt F8
Resumer Program: F9, chuyển qua vị trí đánh dấu mới

`A instanceof B`: Kiểm trả xem A có phải là 1 instance của class B hay không
Tổ hợp phím để tìm trong intellij: Ctrol + Shift + F
Cách để móc data từ mapper:
![[Pasted image 20230303144850.png]]
sau đó định nghĩa các hàm này dưới dạng các câu lệnh SQL:
![[Pasted image 20230303145011.png]]

substring:
![[Pasted image 20230303155956.png]]

![[Pasted image 20230306112340.png]]

so với map, thì multivalueMap sẽ có thể có nhiều value cho 1 key

Lệnh concat có thể ghép các cột lại với nhau , hoặc các chuỗi với nhau tạo thành 1 cột![[Pasted image 20230306145611.png]]

Cách sử dụng LPAD:
Left-pad the string with "ABC", to a total length of 20
```sql
SELECT LPAD("SQL Tutorial", 20, "ABC");
```
-> ABCABCABSQL Tutorial
```sql
SELECT LPAD("SQL Tutorial", 5, "ABC");
```

![[Pasted image 20230307105232.png]]
checking IF_MY_002 -> ko dùng đến postdata
quy trình chuẩn làm việc git
https://viblo.asia/p/quy-trinh-lam-viec-chuan-chi-voi-git-eW65G10RZDO
học git: https://www.youtube.com/watch?v=gjQDyND-vN8&list=PLwJr0JSP7i8D041yrTcWB_qEdzijIUX-q


replace 1 value của 1 key trong hashmap:
gọi 1 hashmap A
A.replace(key, newvalue)

Cấu trúc CTE không đệ quy:
![[Pasted image 20230313111606.png]]
Cấu trúc CTE có đệ quy:
![[Pasted image 20230313111627.png]]
Ví dụ:
table employees:
![[Pasted image 20230313111915.png]]
![[Pasted image 20230313111834.png]]![[Pasted image 20230313111935.png]]

Chú ý các dữ kiện sau:
Laneige Taiwan: TW10
Sulwhasoo Taiwan: TW20
Laneige Vietnam: VN10

TW: pos, HK: poshk, MY: posmy
BRAND (品牌)  
SWS, LNG, AP

1. when the referral value is null => default value  
2. when the referral value is friend referral code => default value  
3. when the referral value is BC referral code => interface the BC referral code to POS
![[Pasted image 20230317102850.png]]


org.springframework.web.client.HttpClientErrorException$BadRequest: 400 Bad Request
org.springframework.web.client.HttpClientErrorException$NotFound: 404 Not Found

connect ko đc :  Search anyconnect để kết nối
Hoặc renew  lại ip config: ipconfig /renew, igpconfig /all
![[Pasted image 20230321115807.png]]

hoặc là vô [AMOREPACIFIC GROUP](https://ap-on.amorepacific.com/), bỏ s sau http, vô sẽ có link drive để tải card về, restart và kết nối

IF_EC_007 : EC-POS  magento from Taiwan to POS
IF_HK_007: EC_POS  magento from Hongkon to POS
IF_MY_007: EC_POS  magento from Malaysia to POS

4000049039
4000049096
4000049090
4000049078
