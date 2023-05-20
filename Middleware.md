String url = "http://localhost:8090/test";
Connect Cissco
Staging
Test postman cho stagin;
[https://stg-gecp-middleware.amorepacific.com/middleware/api/getUserData](https://stg-gecp-middleware.amorepacific.com/middleware/api/getUserData)
test postman cho prd
[https://gecp-middleware.amorepacific.com/middleware/api/getUserData](https://gecp-middleware.amorepacific.com/middleware/api/getUserData)

https://stg-gecp-middleware-adm.amorepacific.com/ap-admin/main/users/signin.fo
![[Pasted image 20230222131030.png]]
username: test01
password: password

password moba: Phongtran97


đăng nhập git: https://gitlab.apdigit.tech/
Gitlab 계정 아이디 : tranthanh.cj 
Gitlab 계정 패스워드: rW&daW6&R4

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

I/O error on POST request for "http://PRV-BO-LB-PRD-EAI-NLB-EAIAPP-6cb2ab6089253ccf.elb.ap-northeast-2.amazonaws.com:5510/restv2/restSDI8177_MALL_GECP_INNI_SAP_P": Connection refused (Connection refused); nested exception is java.net.ConnectException: Connection refused (Connection refused)
![[Pasted image 20230327094001.png]]
![[Pasted image 20230327094024.png]]


<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN"> <html><head> <title>503 Service Unavailable</title> </head><body> <h1>Service Unavailable</h1> <p>The server is temporarily unable to service your request due to maintenance downtime or capacity problems. Please try again later.</p> </body></html>

{"AUTH_KEY":"1b2h3i3o","localeCd":"en","API_ID":"IF_MY_004","API_USER_ID":"MY_LNG_Magento","salOrgCd":"MY10","salOffCd":"MY10","cstmIntgSeq":"MY10210010679"}

{"AUTH_KEY":"1b2h3i3o","localeCd":"en","API_ID":"IF_MY_004","API_USER_ID":"MY_LNG_Magento","salOrgCd":"MY10","salOffCd":"MY10","cstmIntgSeq":"MY10210010679"}

{"AUTH_KEY":"1b2h3i3o","localeCd":"en","API_ID":"IF_MY_004","API_USER_ID":"MY_LNG_Magento","salOrgCd":"MY10","salOffCd":"MY10","cstmIntgSeq":"MY10210010679"}

<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN"> <html><head> <title>503 Service Unavailable</title> </head><body> <h1>Service Unavailable</h1> <p>The server is temporarily unable to service your request due to maintenance downtime or capacity problems. Please try again later.</p> </body></html>

I/O error on POST request for "http://PRV-BO-LB-PRD-EAI-NLB-EAIAPP-6cb2ab6089253ccf.elb.ap-northeast-2.amazonaws.com:5510/restv2/restSDI8177_MALL_GECP_INNI_SAP_P": Connection refused (Connection refused); nested exception is java.net.ConnectException: Connection refused (Connection refused)

{"response":{"header":{"rtn_MSG":"[Error] - [ART.117.4002] Adapter Runtime (Adapter Service): Unable to invoke adapter service AP_SD_02.ZSD_IF_RCV_MALL_ORDER_CONFIRM.adapter.sap:tgtSAP_ZSD_IF_RCV_MALL_ORDER_CONFIRM.\n[ART.117.4012] Ada","rtn_TYPE":"F"},"output":null}}

![[Pasted image 20230328115655.png]]

GPT-4, DALL-E 2, and Midjourney
https://www.refraction.dev/app/unit-tests : tạo test case, refractor 
https://www.producthunt.com/
https://www.coursera.org/learn/material-informatics#syllabus
https://link.springer.com/article/10.1007/s43939-021-00012-0

```json
  "statusMessage": "nested exception is org.apache.ibatis.exceptions.PersistenceException: \n### Error updating database. Cause: java.lang.reflect.UndeclaredThrowableException\n### The error may involve API001.API0100701I-Inline\n### The error occurred while setting parameters\n### SQL: INSERT INTO GSAL01MT_EC(salOrgCd , salOffCd , saledate , orderID , rcptNO , cstmIntgSeq , orderType , promotionKey , prdCD , qty , price , salAmt , dcAmt , netSalAmt , salItem , flag , regDate , regEmpID , REDEMPTION_FLAG , POINT_ACCOUNT , COMPANY , TAXID , ADDRESS , EMAIL , MOBILE ) VALUES (?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, SYSDATE, ?,?,?,?,?,?,?,? )\n### Cause: java.lang.reflect.UndeclaredThrowableException"
```
{"saletime":"13:50:22","promotionKey":"SWSNEW","orderType":"000030","orderID":"CSWS000004404","rcptNO":"I6000003027","salOffCd":"HK20","AUTH_KEY":"123456","ffReferralCode":"","API_ID":"IF_HK_007","API_USER_ID":"HK_SWS_Magento","saledate":"20230403","orderInfo":[{"prdCD":"111174319","qty":1,"price":"1960.00","salAmt":"1960.00","dcAmt":"196.00","netSalAmt":"1764.00","redemptionFlag":"N","pointAccount":0},{"prdCD":"111247878","qty":2,"price":"0.00","salAmt":"0.00","dcAmt":"0.00","netSalAmt":"0.00","redemptionFlag":"N","pointAccount":0},{"prdCD":"111247536","qty":2,"price":"0.00","salAmt":"0.00","dcAmt":"0.00","netSalAmt":"0.00","redemptionFlag":"N","pointAccount":0}],"salOrgCd":"HK20","baReferralCode":"SWS GECP","cstmIntgSeq":"HK20210001769"}

{"statusCode":"","statusMessage":"nested exception is org.apache.ibatis.exceptions.PersistenceException: \n### Error updating database. Cause: java.lang.reflect.UndeclaredThrowableException\n### The error may involve API001.API0100701I-Inline\n### The error occurred while setting parameters\n### SQL: INSERT INTO GSAL01MT_EC(salOrgCd , salOffCd , saledate , orderID , rcptNO , cstmIntgSeq , orderType , promotionKey , prdCD , qty , price , salAmt , dcAmt , netSalAmt , salItem , flag , regDate , regEmpID , REDEMPTION_FLAG , POINT_ACCOUNT , COMPANY , TAXID , ADDRESS , EMAIL , MOBILE ) VALUES (?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, SYSDATE, ?,?,?,?,?,?,?,? )\n### Cause: java.lang.reflect.UndeclaredThrowableException"}

{"statusMessage":"\n### Error updating database. Cause: java.sql.SQLException: ORA-12899: value too large for column \"IGPOWN\".\"GCTR40DT\".\"DATA1\" (actual: 4835, maximum: 4000)\nORA-06512: at \"IGPOWN.P_SETLOG\", line 75\nORA-06512: at \"IGPOWN.P_SETLOG\", line 53\nORA-06512: at \"IGPOWN.P_SETLOG\", line 47\nORA-06512: at line 1\n\n### The error may involve query.inf029.INF0030088P-Inline\n### The error occurred while setting parameters\n### SQL: {call P_SETLOG( ?, ?, ?, ?, ?, ?, ?, ? )}\n### Cause: java.sql.SQLException: ORA-12899: value too large for column \"IGPOWN\".\"GCTR40DT\".\"DATA1\" (actual: 4835, maximum: 4000)\nORA-06512: at \"IGPOWN.P_SETLOG\", line 75\nORA-06512: at \"IGPOWN.P_SETLOG\", line 53\nORA-06512: at \"IGPOWN.P_SETLOG\", line 47\nORA-06512: at line 1\n\n; uncategorized SQLException; SQL state [72000]; error code [12899]; ORA-12899: value too large for column \"IGPOWN\".\"GCTR40DT\".\"DATA1\" (actual: 4835, maximum: 4000)\nORA-06512: at \"IGPOWN.P_SETLOG\", line 75\nORA-06512: at \"IGPOWN.P_SETLOG\", line 53\nORA-06512: at \"IGPOWN.P_SETLOG\", line 47\nORA-06512: at line 1\n; nested exception is java.sql.SQLException: ORA-12899: value too large for column \"IGPOWN\".\"GCTR40DT\".\"DATA1\" (actual: 4835, maximum: 4000)\nORA-06512: at \"IGPOWN.P_SETLOG\", line 75\nORA-06512: at \"IGPOWN.P_SETLOG\", line 53\nORA-06512: at \"IGPOWN.P_SETLOG\", line 47\nORA-06512: at line 1\n","statusCode":"E"}

![[Pasted image 20230404113345.png]]


Date of work : 2024.04.04  
Name :  Phong
Name (Korean) :  민재 (Min Jae)
Name (English) :  Will 
Birthday :  10-11-1997
AP E-mail  : tranthanh.cj@amorepacific.com
PC Mac Address : E0-0A-F6-95-0D-3F

I/O error on POST request for "https://g-ext.innisfreepos.com/v1/directmall/member/search": g-ext.innisfreepos.com; nested exception is java.net.UnknownHostException: g-ext.innisfreepos.com




```groovy
plugins {
    id 'org.springframework.boot' version '2.5.6'
    id 'io.spring.dependency-management' version '1.0.11.RELEASE'
    id 'java'
    id 'war'
}
```

```groovy
dependencies {
    implementation 'com.fasterxml.jackson.core:jackson-core:2.12.5'
}
```

It's important to notice that some of your dependencies are duplicated, and it's a good practice to keep only the latest version of each dependency to avoid conflicts or unexpected behaviors.  
  
Here are the recommended upgrades based on your [build.gr](http://build.gr/)adle file:  
  
Update the Spring Boot version to the latest stable version: 2.6.1  
id '[org.springframework.bo](http://org.springframework.bo/)ot' version '2.6.1'  
Remove the redundant gson dependency; Jackson is already being used:  
implementation '[com.google.code.gs](http://com.google.code.gs/)on:gson:2.8.6' // remove this line  
Update the Jackson version and use the same version for all Jackson dependencies:  
implementation '[com.fasterxml.jackson.co](http://com.fasterxml.jackson.co/)re:jackson-core:2.13.0'  
compile group: '[com.fasterxml.jackson.co](http://com.fasterxml.jackson.co/)re', name: 'jackson-databind', version: '2.13.0'  
compile group: 'com.fasterxml.jackson.jaxrs', name: 'jackson-jaxrs-json-provider', version: '2.13.0'  
compile group: '[com.fasterxml.jackson.co](http://com.fasterxml.jackson.co/)re', name: 'jackson-core', version: '2.13.0'  
Update the Apache CXF version:  
compile group: '[org.apache.cx](http://org.apache.cx/)f', name: 'cxf-core', version: '3.5.0'  
compile group: '[org.apache.cx](http://org.apache.cx/)f', name: 'cxf-spring-boot-starter-jaxrs', version: '3.5.0'  
Update the json-lib version:  
compile group: 'net.sf.json-lib', name: 'json-lib', version: '2.4', classifier: 'jdk15'  
Remove the redundant JSON library:  
compile group: 'org.json', name: 'json', version: '20190722' // remove this line  
Remove the redundant Jackson Mapper:  
compile group: '[org.co](http://org.co/)dehaus.jackson', name: 'jackson-mapper-asl', version: '1.5.0' // remove this line  
Update Tomcat to the latest version:  
implementation group: '[org.apache.to](http://org.apache.to/)mcat.embed', name: 'tomcat-embed-jasper', version: '10.0.13'  
Apply these changes to your [build.gr](http://build.gr/)adle file, and you should have the latest compatible versions of your dependencies. Remember to always check for compatibility between library versions before upgrading to ensure a smooth transition.  


  
vn-master" nhánh của admin
vn-front: nhánh của frontpage
querydsl

![[Pasted image 20230418164106.png]]
![[Pasted image 20230418164146.png]]

link deploy:
[https://dev-jenkins.amorepacific.com/](https://dev-jenkins.amorepacific.com/)

link deploy staging:
[https://jenkins.amorepacific.com/job/STG-GECP-WAS/](https://jenkins.amorepacific.com/job/STG-GECP-WAS/)


vn front và vn admin : build mới nhất
pwd
/data/logs/vn

igvapp: insert, update, select
igvon: thay đổi table

{"lastName":"Roslan","birthDay":"19970116","homeZip":"20400","sex":"F","if_flag":"U","smsYN":"Y","prtnrid":"MY300028","callYN":"N","homeState":"","salOffCd":"MY13","statusCD":"01","mobileNo":"0193779615","emailYN":"Y","AUTH_KEY":"1m2k3o4p","localeCd":"en","firstName":"Nur Aishah Shahirah binti","dmYN":"N","homeAddr1":"Kuarters JKR 178 Jalan Negara","API_ID":"IF_MY_002","API_USER_ID":"MY_INNI_Magento","homeCity":"SGR","salOrgCd":"MY13","cstmIntgSeq":"5279240100006133","email":"nuraishahshahirahroslan1@gmail.com"}
{"lastName":"Roslan","prtnrid":"MY300028","callYN":"N","salOffCd":"MY13","statusCD":"01","localeCd":"en","homeAddr1":"No 53 Jalan Desa 2/6, Bandar Country Homes","API_USER_ID":"MY_INNI_Magento","homeCity":"SGR","salOrgCd":"MY13","email":"nuraishahshahirahroslan1@gmail.com","birthDay":"19970116","empID":"","homeZip":"48000","sex":"F","if_flag":"I","smsYN":"Y","homeState":"MY-321","mobileNo":"0193779615","emailYN":"N","AUTH_KEY":"1m2k3o4p","firstName":"Nur Aishah Shahirah binti","dmYN":"N","API_ID":"IF_MY_002","cstmIntgSeq":"5279240100006133"}

java.lang.IllegalStateException: Expected BEGIN_OBJECT but was STRING at line 1 column 1 path $

{"AUTH_KEY":"1m2k3o4p","localeCd":"en","API_ID":"IF_MY_006","API_USER_ID":"MY_INNI_Magento","salOrgCd":"MY13","salOffCd":"MY13","cstmIntgSeq":"5279240100005967"}


![[Pasted image 20230425141357.png]]

![[Pasted image 20230425143334.png]]

{"lastName":"Sze Leng","birthDay":"20020726","homeZip":"31300","sex":"F","if_flag":"U","smsYN":"Y","prtnrid":"MY300028","callYN":"N","homeState":"","salOffCd":"MY13","statusCD":"01","mobileNo":"0125003942","emailYN":"Y","AUTH_KEY":"1m2k3o4p","localeCd":"en","firstName":"Teoh","dmYN":"N","homeAddr1":"13，hala Pulai Jaya 5 Bandar Pulai Jaya","API_ID":"IF_MY_002","API_USER_ID":"MY_INNI_Magento","homeCity":"PRK","salOrgCd":"MY13","cstmIntgSeq":"5279240100006156","email":"szeleng112@gmail.com"}

{"lastName":"Sze Leng","prtnrid":"MY300028","callYN":"N","salOffCd":"MY13","statusCD":"01","localeCd":"en","homeAddr1":"13，hala Pulai Jaya 5 Bandar Pulai Jaya","API_USER_ID":"MY_INNI_Magento","homeCity":"PRK","salOrgCd":"MY13","email":"szeleng112@gmail.com","birthDay":"20020726","empID":"","homeZip":"31300","sex":"F","if_flag":"I","smsYN":"Y","homeState":"MY-230","mobileNo":"0125003942","emailYN":"N","AUTH_KEY":"1m2k3o4p","firstName":"Teoh","dmYN":"N","API_ID":"IF_MY_002","cstmIntgSeq":"5279240100006156"}

```
plugins {
    id 'org.springframework.boot' version '2.6.6'
    id 'io.spring.dependency-management' version '1.0.8.RELEASE'
    id 'java'
    id 'war'
}

group = 'com.amorepacific'
version = '0.0.1-SNAPSHOT'
sourceCompatibility = '1.8'

repositories {
    maven {
        url "https://i-nexus.apdigit.tech/repository/maven-central/"
    }
    maven {
        url "https://i-nexus.apdigit.tech/repository/maven-releases/"
    }
}

configurations.all {
    resolutionStrategy.eachDependency { DependencyResolveDetails details ->
        if (details.requested.group == 'org.apache.logging.log4j') {
            details.useVersion '2.17.1'
        }
    }
}

dependencies {
    implementation 'org.springframework.boot:spring-boot-starter-web'
    implementation 'org.springframework.boot:spring-boot-starter-thymeleaf'
    implementation 'org.springframework.boot:spring-boot-starter-aop'
    implementation 'org.springframework.boot:spring-boot-starter-validation'
    implementation 'org.springframework.boot:spring-boot-starter-data-jpa'
    implementation 'org.springframework.boot:spring-boot-starter-security'
    implementation 'com.google.code.gson:gson:2.8.6'
    implementation 'com.fasterxml.jackson.core:jackson-core:2.13.2'
    implementation 'mysql:mysql-connector-java:8.0.27'
    implementation 'javax.servlet:jstl:1.2.7'
    implementation 'org.mybatis.spring.boot:mybatis-spring-boot-starter:2.0.1'
    implementation group: 'org.apache.cxf', name: 'cxf-core', version: '3.3.6'
    implementation group: 'org.apache.cxf', name: 'cxf-spring-boot-starter-jaxrs', version: '3.3.6'
    implementation group: 'com.fasterxml.jackson.jaxrs', name: 'jackson-jaxrs-json-provider', version: '2.9.8'
    implementation group: 'net.sf.json-lib', name: 'json-lib', version: '2.4', classifier: 'jdk15'
    implementation group: 'org.json', name: 'json', version: '20190722'
    implementation group: 'com.fasterxml.jackson.core', name: 'jackson-core', version: '2.11.3'
    implementation group: 'org.codehaus.jackson', name: 'jackson-mapper-asl', version: '1.5.0'

    implementation group: 'org.slf4j', name: 'slf4j-api', version: '1.7.32'
    implementation group: 'org.slf4j', name: 'jul-to-slf4j', version: '1.7.32'
    implementation group: 'ch.qos.logback', name: 'logback-core', version: '1.3.0-alpha5'
    implementation group: 'ch.qos.logback', name: 'logback-classic', version: '1.3.0-alpha5'

    compileOnly 'org.projectlombok:lombok'
    annotationProcessor 'org.springframework.boot:spring-boot-configuration-processor'
    annotationProcessor 'org.projectlombok:lombok'
    testImplementation('org.springframework.boot:spring-boot-starter-test') {
        exclude group: 'org.junit.vintage', module: 'junit-vintage-engine'
    }
}

```

Cách sử dụng lệnh gradle:
./gradlew build 
./gradlew --version

The `gradlew` command is used to run Gradle tasks with the Gradle Wrapper. It is a script that handles the Gradle setup and execution, ensuring that the correct Gradle version is used for your project.

IF_EC_001:
{"AUTH_KEY":"123456","localeCd":"en","firstName":"Hoang","lastName":"Phan","API_ID":"IF_EC_001","API_USER_ID":"TW_SWS_Magento","mobileNumber":"0941069901","salOrgCd":"TW10","salOffCd":"TW20"}
IF_EC_004:
{"AUTH_KEY":"123456","localeCd":"en","API_ID":"IF_EC_004","API_USER_ID":"TW_LNG_Magento","salOrgCd":"TW10","salOffCd":"TW10","cstmIntgSeq":""}
IF_EC_005:
{"AUTH_KEY":"123456","localeCd":"en","API_ID":"IF_EC_005","API_USER_ID":"TW_LNG_Magento","salOrgCd":"TW10","salOffCd":"TW10","page":1,"cstmIntgSeq":"TW10210001071"}
IF_EC_006:
{"AUTH_KEY":"123456","localeCd":"en","API_ID":"IF_EC_006","API_USER_ID":"TW_LNG_Magento","salOrgCd":"TW10","salOffCd":"TW10","page":1,"cstmIntgSeq":"TW10210001071"}
IF_MY_001:
{"AUTH_KEY":"123456","localeCd":"en","firstName":"sontn","lastName":"sontn","API_ID":"IF_MY_001","API_USER_ID":"MY_LNG_Magento","mobileNumber":"0998123321","salOrgCd":"MY10","salOffCd":"MY10"}
IF_MY_004:
{"AUTH_KEY":"123456","localeCd":"en","API_ID":"IF_MY_004","API_USER_ID":"MY_LNG_Magento","salOrgCd":"MY10","salOffCd":"MY10","cstmIntgSeq":"MY10210000157"}
IF_MY_006:{"AUTH_KEY":"123456","localeCd":"en","API_ID":"IF_MY_006","API_USER_ID":"MY_LNG_Magento","salOrgCd":"MY10","salOffCd":"MY10","page":1,"cstmIntgSeq":"MY10210000157"}
IF_HK_001:
{"AUTH_KEY":"123456","firstName":"nguyễn","lastName":"anh","API_ID":"IF_HK_001","API_USER_ID":"HK_LNG_Magento","mobileNumber":"12345677","countryCode":"1458003","salOrgCd":"HK20","salOffCd":"HK10"}
IF_HK_004:
{"AUTH_KEY":"123456","API_ID":"IF_HK_004","API_USER_ID":"HK_LNG_Magento","salOrgCd":"HK20","salOffCd":"HK10","cstmIntgSeq":"HK10210006245"}
IF_HK_006:
{"AUTH_KEY":"123456","API_ID":"IF_HK_006","API_USER_ID":"HK_SWS_Magento","salOrgCd":"HK20","salOffCd":"HK20","cstmIntgSeq":"HK20210001754"}

{"statusCode":"1","statusMessage":"Database Error::Member information does not exist.(HK10210013912)"}



{"saletime":"12:09:34","promotionKey":"CASETIFY50","orderType":"000010","orderID":"SWS000018374","rcptNO":"I6000012656","salOffCd":"HK20","AUTH_KEY":"1v2g3u4i","ffReferralCode":"","API_ID":"IF_HK_007","API_USER_ID":"HK_SWS_Magento","saledate":"20230425","orderInfo":[{"prdCD":"270320578","qty":1,"price":"280.00","salAmt":"280.00","dcAmt":"140.00","netSalAmt":"140.00","redemptionFlag":"N","pointAccount":0},{"prdCD":"270320591","qty":1,"price":"840.00","salAmt":"840.00","dcAmt":"420.00","netSalAmt":"420.00","redemptionFlag":"N","pointAccount":0}],"salOrgCd":"HK20","baReferralCode":"SWS GECP","cstmIntgSeq":"HK20210004945"}


{"statusMessage":"Database Error::Member information does not exist.(HK20210004945)","statusCode":"1"}

{"promotionKey":null,"orderType":"000010","orderID":"4000007387STG","rcptNO":"I4000004846STG","salOffCd":"TW10","redemptionFlag":"N","AUTH_KEY":"123456","localeCd":"en","ffReferralCode":"0927272727","API_ID":"IF_EC_007","API_USER_ID":"TW_LNG_Magento","PointAccount":0,"saledate":"20230516","orderInfo":[{"prdCD":"270281209","qty":3,"price":131,"salAmt":393,"dcAmt":21,"netSalAmt":372,"redemptionFlag":"N","pointAccount":0},{"prdCD":"111975603-3","qty":1,"price":1350,"salAmt":1350,"dcAmt":67,"netSalAmt":1283,"redemptionFlag":"N","pointAccount":0},{"prdCD":"111989270","qty":3,"price":2350,"salAmt":7050,"dcAmt":352,"netSalAmt":6698,"redemptionFlag":"N","pointAccount":0},{"prdCD":"111975629-1","qty":1,"price":1100,"salAmt":1100,"dcAmt":55,"netSalAmt":1045,"redemptionFlag":"N","pointAccount":0},{"prdCD":"270287188","qty":1,"price":0,"salAmt":0,"dcAmt":0,"netSalAmt":0,"redemptionFlag":"N","pointAccount":0}],"salOrgCd":"TW10","baReferralCode":"AP GECP APAC","cstmIntgSeq":"TW10210001000"}

{"saletime":"12:06:34","promotionKey":null,"orderType":"000010","orderID":"APB000004835","rcptNO":"I000003287","salOffCd":"HK30","AUTH_KEY":"1e2r3t4y","ffReferralCode":"","API_ID":"IF_HK_007","API_USER_ID":"HK_AP_Magento","saledate":"20230518","orderInfo":[{"prdCD":"279067386","qty":4,"price":"290.00","salAmt":"1160.00","dcAmt":"585.00","netSalAmt":"575.00","redemptionFlag":"N","pointAccount":0},{"prdCD":"111388251","qty":2,"price":"0.00","salAmt":"0.00","dcAmt":"0.00","netSalAmt":"0.00","redemptionFlag":"N","pointAccount":0},{"prdCD":"111388255","qty":2,"price":"0.00","salAmt":"0.00","dcAmt":"0.00","netSalAmt":"0.00","redemptionFlag":"N","pointAccount":0}],"salOrgCd":"HK20","baReferralCode":"AP GECP","cstmIntgSeq":"HK30201871021"}

