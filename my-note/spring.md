
****

mã số thuế cty : 037485709
Spring Boot = Presentation layer + Service layer + Data access layer


file .bat: chứa những dòng lệnh được thực thi trong terminal

File pom.xml là nơi khai báo tất cả những gì liên quan đến dự án được cấu hình qua maven, như khai báo các dependency, version của dự án, tên dự án, repossitory

cài đặt thư viện maven: `mvn spring-boot:run`

lệnh `dir`: xem directory

@restController đi kèm với @RequestMapping để xử lý các request liên quan đến server
@dùng resController thay cho @Controller để tự động order hoá objecr trả về HTTpresponse mà không cần @responsebody

SpringApplication là 1 class cung cấp các thuận tiện để khởi chạy ứng dụng từ hàm main()

**@SpringBootApplication** giúp bạn tự động cấu hình **Spring**, và tự động quét (Scan) toàn bộ project để tìm ra các thành phần Spring (Controller, Bean, Service,...)

**@SpringBootApplication** = **@Configuration** + **@EnableAutoConfiguration**  +  **@ComponentScan** (các spring truyền thống)
![[Pasted image 20221019161035.png]]

JPA là viết tắt của **Java Persistence API**, là một đặc các tiêu chuẩn của Java để làm việc với cơ sở dữ liệu quan hệ

@**entity** là một Java class tương ứng với một table trong database. sử dụng @Table annotation để chỉ rõ table tương ứng với entity name
```java
@Entity 
@Table(name = "EMPLOYEE")
```
_@EntityListeners_ annotation to specify callback listener classes. Spring Data provides its own JPA entity listener class, _AuditingEntityListener_.
```java
@Entity 
@EntityListeners(AuditingEntityListener.class) 
	public class Bar { ... }
```

@GeneratedValue **được sử dụng để Hibernate tự động tạo ra giá trị và gán vào cho một cột trong trường hợp insert mới một Entity vào database**

@Id: Entity đề phải có một id, id dùng để định danh, phân biệt giữa các bản ghi với nhau, đã là id thì nó phải unique. Id là được dùng để làm khóa chính của bảng.

_@Autowired_ cho phép Spring tự động tìm kiếm và tiêm các bean tương ứng mà chúng ta đã khai báo trong class.

các class có I đằng trước là 1 Interface, ví dụ interface: IDocumentService
khai báo `private IDocumentService documentService` thì docummentService là 1 biến

FileNotFoundException (lỗi không tìm thấy file) và _IOException_ (lỗi không đọc được file)


-- Serial - Deserial
![[Pasted image 20221020154406.png]]

Serialization trong Java là cơ chế chuyển đổi trạng thái của một đối tượng (giá trị các thuộc tính trong object) thành một chuỗi byte sao cho chuỗi byte này có thể chuyển đổi ngược lại thành một đối tượng.

Quá trình chuyển đổi chuỗi byte thành đối tượng gọi là deserialization.

Trong Java, khi trao đổi dữ liệu giữa các thành phần khác nhau (giữa các module cùng viết bằng Java) thì dữ liệu được thể hiện dưới dạng byte chứ không phải là đối tượng. Do đó ta cần có một cơ chế để hiểu các đối tượng được gửi và nhận.

![[Pasted image 20221026101912.png]] 

@jsonignore: loại bỏ 1 field ra khỏi trật tự serial hoặc deserial.  Which means if you are calling REST API from anywhere then your attribute will not be present in JSON request/responses.
Thường jsonignore chỉ dùng trong các file dto

**Generics** means **parameterized types**. The idea is to allow type (Integer, String, … etc., and user-defined types) to be a parameter to methods, classes, and interfaces.

Tự định nghĩa 1 kiểu Generic
![[Pasted image 20221020160622.png]]



@Data là cách dùng nhanh khi bạn muốn thêm tất cả các annotation:

-   [@Getter](https://viblo.asia/u/Getter) / [@Setter](https://viblo.asia/u/Setter)
-   [@ToString](https://viblo.asia/u/ToString)
-   [@EqualsAndHashCode](https://viblo.asia/u/EqualsAndHashCode)
-   [@RequiredArgsConstructor](https://viblo.asia/u/RequiredArgsConstructor)

của Lombok vào 1 class.

`@Override` means you are overriding the base class method.

@service: _It is used to mark the class as a service provider_. It used with classes that provide some business functionalities. Spring context will autodetect these classes when annotation-based configuration and classpath scanning is used.

![[Pasted image 20221020171349.png]]
![[Pasted image 20221020171415.png]]

**@Slf4j generates a logger**:
![[Pasted image 20221020173108.png]]

 **_@Value_ Spring annotation.**

This annotation can be used for injecting values into fields in Spring-managed beans, and it can be applied at the field or constructor/method parameter level.

 _@ApiResponse_ : It's a common practice to return errors using HTTP status codes. We can use the annotation to describe the concrete possible response of an operation.: Chú thích cho lỗi
```java
	@Operation(summary = "Find book by ID", description = "Returns a single book", tags = { "book" })
	@ApiResponses(value = {
			@ApiResponse(responseCode = "200", description = "successful operation", content = @Content(schema = @Schema(implementation = Book.class))),
			@ApiResponse(responseCode = "400", description = "Invalid ID supplied", content = @Content),
			@ApiResponse(responseCode = "404", description = "Book not found", content = @Content) })
	@GetMapping("/{id}")
	public ResponseEntity<Book> getBookById(@PathVariable("id") long id) {
	    Optional<Book> bookData = bookRepository.findById(id);
	    if (bookData.isPresent()) {
	      return new ResponseEntity<>(bookData.get(), HttpStatus.OK);
	    } else {
	      return new ResponseEntity<>(HttpStatus.NOT_FOUND);
	    }
	}

```


@RequestParam
![[Pasted image 20221021103308.png]]


Spring Data JPA hỗ trợ cho chúng ta sẵn các phương thức để truy cập vào database. Chúng ta chỉ cần kế thừa JPA Repository là có thể sử dụng được các phương thức mà JPA cung cấp đề lấy dữ liệu từ Database.

```java
public interface DepartmentQueryCreationRepository extends JpaRepository<Department,Integer> {}
```

![[Pasted image 20221021121105.png]]

method declaration:
![[Pasted image 20221021125738.png]]

When a method uses a class name as its return type, the class of the type of the returned object must be either a subclass of, or the exact class of, the return type.

![[Pasted image 20221021132446.png]]
A method can have the class name as its return type. Therefore it must return the object of the exact class or its subclass.

An interface name can also be used as a return type but the returned object must implement methods of that interface.
![[Pasted image 20221021140329.png]]
giải thích: lí do obj2 không phải khai báo là SumReturn obj2 = new SumReturn() vì ko có đối số, trong khi class SumReturn có hàm contructor SumReturn đẩy đối số vào.
Do vậy khi class ko có contructor thì có thể tạo object bằng cách 

`Tên class [tên object] =new()  Tên class `

hàm SumReturn addition() khai báo return type là SumReturn vì nó sử dụng các object con của class SumReturn vào bản thân nó. Ngoài ra , giá trị return của nó phải là 1 object - reference xuất hiện trong subclass



The _save()_ method INSERTs an object in the database
Unlike _save()_, the _saveAndFlush()_ method **flushes the data immediately during the execution.** (tức là mọi thay đổi sẽ áp dụng ngay lập tức cho database)

_@RequestBody_ được dùng để ánh xạ _HttpRequest body_ sang một domain object tự động.
![[Pasted image 20221021144210.png]]

{

    "emp_id": 1,

    "first_name": "Tran",

    "last_name": "Phong",

    "email_id": "ttphong1011@gmail.com"

}


config trong application-dev
thay đổi nội dung:
```yml
datasource:  
  #url: ${JDBC_DATABASE_URL:jdbc:postgresql://amore-postgres.cfq7jozskh11.ap-southeast-1.rds.amazonaws.com/amore}  
  url: ${JDBC_DATABASE_URL:jdbc:postgresql://192.168.1.13:5432/postgres}  
  
  #url: ${JDBC_DATABASE_URL:jdbc:postgresql://localhost:5432/amore}  
  username: ${JDBC_DATABASE_USERNAME:postgres}  
  #password: ${JDBC_DATABASE_PASSWORD:yz2hL4L8KN17U7cgfkLQ}  
  password: ${JDBC_DATABASE_PASSWORD:postgres123}
```
dev: thử nghiệm cho các developer
prd: thử nghiệm production
qas: thử nghiệm cho QA
stg: thử nghiệm staging

"/reports/**" phải add vào trong file GlobalSecurityConfig.java. Lí do: vì security nên khi sử dụng postman sẽ bão lỗi là ko truy vấn được
File để config security nằm trong thư mục core/config/jpa/Global...

-- LinkHashmap
Nếu như các bạn từng biết đến [HashMap](https://shareprogramming.net//hashmap-in-java/) thì nó là một cấu trúc dạng _key – value_ cho phép truy xuất các phần tử nhanh chóng dựa theo _key_. Thế nhưng HashMap lại không đảm bảo thứ tự của các phần tử nên Java cung cấp thêm LinkedHashMap ngoài các tính năng như HashMap thì nó còn đảm bảo thứ tự của các phần tử được thêm vào.

Các đặc tính quan trọng của LinkedHashMap

-   LinkedHashMap implement từ [Map interface](https://shareprogramming.net/map-interface-trong-java/) và _extends_ từ HashMap.
-   LinkedHashMap có thể chứa **một key null và nhiều value null**.
-   LinkedHashMap gần giống với HashMap ngoại trừ việc LinkedHashMap đảm bảo thứ tự khi thêm các phần tử vào.
- 
-- Các constructor của linkhashmap:

1.  **LinkedHashMap():** Constructor mặc định.
2.  **LinkedHashMap(int capacity):** Khởi tạo với sức chứa **capacity** cụ thể.
3.  **LinkedHashMap(Map m_a_p):**Khởi tạo với các phần tử trong HashMap cho trước.
4.  **LinkedHashMap(int capacity, float loadFactor):**  Khởi tạo với sức chứa **capacity** và  **loadFactor** cụ thể.
5.  **LinkedHashMap(int capacity, float loadFactor, boolean Order):** Khởi tạo với sức chứa **capacity** và  **loadFactor** cụ thể với chỉ định kiểu sắp xếp.

-- Các method bao gồm:

1.  **void clear()**: Xoá tất cả các phần tử trong LinkedHashMap.
2.  **boolean containsKey(Object key)**: Trả về true nếu key được chỉ định chứa trong LinkedHashMap, ngược lại false.=
3.  **Object get(Object key):** Trả về value tương ứng với key được chỉ định.
4.  **entrySet?():** Sẽ về entry set của LinkedHashMap.
5.  **forEach?(BiConsumer<K,V> action):** Sử dụng để duyệt LinkedHashMap.
6.  **getOrDefault?(Object key, V defaultValue):** Trả về giá trị của key được chỉ định. Nếu key không chứa trong LinkedHashMap thì method này sẽ trả về defaultValue.
7.  **keySet?():** Trả về một tập key của LinkedHashMap.
8.  **removeEldestEntry?(Map.Entry<K,V> eldest):**
9.  **replaceAll?(BiFunction<K,V> function):** Cập nhật tất các phần tử trong LinkedHashMap.
10.  **values?():** Trả về collection các giá trị trong LinkedHashMap.




Lớp StringUtils bao gồm rất nhiều phương thức hỗ trợ thao tác trên chuỗi, bên dưới là một số phương thức thường được sử dụng:

-   **abbreviate()** : trả về chuỗi viết tắt bằng cách sử dụng ellipses.
-   **capitalize()** : viết hoa chữ cái đầu tiên của chuỗi.
-   **appendIfMissing()** : trả về một chuỗi mới nếu hậu tố được thêm vào, ngược lại trả về cùng một chuỗi.
-   **prependIfMissing()** : trả về một chuỗi mới nếu tiền tố được thêm vào, ngược lại trả về cùng một chuỗi.
-   **containsAny()** : Kiểm tra nếu chuỗi chứa bất kỳ ký tự nào trong tập ký tự hay chuỗi đã cho.
-   **containsIgnoreCase()** : Kiểm tra nếu chuỗi chứa một chuỗi đã cho và không phân biệt hoa thường.
-   **countMatches()**  : Đếm bao nhiêu lần chuỗi con xuất hiện trong chuỗi
-   **defaultIfEmpty()** : trả về chuỗi mặc định nếu chuỗi được cho là empty hoặc null, nếu không thì trả về cùng một chuỗi.
-   **defaultIfBlank()** : trả về chuỗi mặc định nếu chuỗi được cho là blank hoặc null, nếu không trả về cùng một chuỗi.
-   **defaultString()** : trả về một chuỗi rỗng nếu chuỗi được cho là null, nếu không trả về cùng một chuỗi.
-   **equalsIgnoreCase()**: trả về giá trị TRUE nếu 2 chuỗi đã cho là bằng nhau không phân biệt hoa thường. Phương thức này tương tự như string.equalsIgnoreCase() nhưng nó hạn chế được lỗi NullPointerException.
-   **indexOfIgnoreCase()** : trả về chỉ mục đầu tiên của chuỗi tìm kiếm trong chuỗi ký tự đã cho không phân biệt hoa thường.
-   **isAlphanumeric()** : trả về TRUE nếu chuỗi đã cho chỉ chứa các ký tự chữ và số.
-   **isAlpha()** : trả về TRUE nếu chuỗi đã cho chỉ chứa các ký tự chữ cái.
-   **isNumeric()** : trả về TRUE nếu chuỗi đã cho chỉ chứa các ký tự số.
-   **isBlank()** : trả về TRUE nếu chuỗi đã cho là blank.
-   **isEmpty()** : trả về TRUE nếu chuỗi đã cho là empty.
-   **isNotBlank()** : trả về TRUE nếu chuỗi đã cho là không blank.
-   **isNotEmpty()** : trả về TRUE nếu chuỗi đã cho là không empty.
-   **left()**: trả về các ký tự bên trái của chuỗi đã cho với độ dài xác định.
-   **right()**: trả về các ký tự bên phải của chuỗi đã cho với độ dài xác định.
-   **leftPad()** : trả về chuỗi với các ký tự được thêm vào bên trái nếu chuỗi không đủ độ dài được chỉ định, ngược lại trả về chuỗi ban đầu.
-   **rightPad()** : trả về chuỗi với các ký tự được thêm vào bên phải nếu chuỗi không đủ độ dài được chỉ định, ngược lại trả về chuỗi ban đầu.
-   **reverse()**: đảo thứ tự các ký tự của một chuỗi.
-   **trim()** : gỡ bỏ các ký tự rỗng khỏi cả hai đầu của chuỗi này.
-   **trimToEmpty()**: Nếu chuỗi được cho là NULL nó sẽ trả về chuỗi EMPTY, nếu không sẽ trả về chuỗi đã được gỡ bỏ các ký tự rỗng khỏi cả hai đầu.
-   **trimToNull()**: Nếu chuỗi được cho là EMPTY nó sẽ trả về chuỗi NULL, nếu không sẽ trả về chuỗi đã được gỡ bỏ các ký tự rỗng khỏi cả hai đầu.





Các dạng data:
-   **Public:** nghĩa là để trao đổi, chia sẻ với bên ngoài qua REST API hoặc giao tiếp với các service khác trong microservice. Data lúc này ở dạng DTO.
-   **Private:** các data dùng trong nội bộ ứng dụng, bên ngoài không nên biết. Data lúc này nằm trong các Domain model hoặc Entity.

Tuy nhiên cũng có thể phân loại thành 3 loại Data: 
- Dto: là các class đóng gói data giữa client-server và các service trong microservice, giảm số lần gọi method giữa các tiến trình xử lý
- Domain model: là các đối tượng thuộc business
- Entity: là những domain model có thể map vào DB được

Chuyên tắt chọn Data: 
- Controller làm việc với DTO
- Service: nhận vào DTO hoặc Domain model, trả về dưới dạng DTO
- Repository: làm việc với entity
--> việc convert các loại datata được gọi là model mapping

--> Quá trình:
```java
Controller nhận DTO > Service chuyển DTO thành model hoặc entity, rồi xử lý > Repository nhận Entity đưa vào DB

Repository lấy từ DB ra Entity > Service xử lý sao đó rồi thành DTO > Controller và trả về DTO
```

![[Pasted image 20221026165923.png]]

![[Pasted image 20221026170059.png]]

`Giải pháp ở đây chính là khởi tạo một DTO object chứa tất cả các dữ liệu trong một lần gọi đến API. Nó cần phải được serializable trước khi được truyền qua connection và deserializable để nhận lại DTO ban đầu được gửi từ phía bên kia.`

http://smarteevina.ddns.net:8080/swagger-ui/index.html

--------------Pageable
-   `Pageable` sẽ chứa các thông tin phân trang như số phần tử được lấy, vị trí trang được lấy
Pageable là 1 interface, để tạo  nó ta sử dụng `PageRequest`

Ví dụ tạo pageable với thông tin là page thứ 1với 10 phần tử:

-   `Pageable pageable = PageRequest.of(1, 10);`

Ngoài ra bạn cũng có thể sắp xếp các phần tử trong page bằng cách thêm tham số `sort` vào trong `pageable`:

`-   Sort sort = Sort.by("name").descending();
`-   Pageable pageable = PageRequest.of(1, 10, sort);``

Khởi tạo `optional` object
```
Optional<String> empty = Optional.empty();
        
boolean isPresent = empty.isPresent(); // FALSE
```

```
Optional<String> optional = Optional.of("Shareprogramming.net");

boolean isPresent = optional.isPresent(); // TRUE
```
optional class bọc ngoài object, chỉ cho phép truy xuất các object được bao bọc bên trong thông qua hàm kiểm tra khác null như .isPresent() , .isEmpty() ...
Optional là một kiểu dữ liệu container, nó bao bọc chỉ một giá trị duy nhất nếu giá trị đó tồn tại. Như vậy mục đích của nó đưa ra là về sự tồn tại của dữ liệu hay không.

Toán tử instanceof trong Java **là một toán tử được sử dụng để kiểm tra xem đối tượng này có phải là instance của một class hay interface nào đó hay không**? Kết quả trả về của toán tử này sẽ là true nếu đối tượng đó là thể hiện của class mà các bạn đang check, ngược lại thì false.



spring.jpa.database-platform trong application.properties: sử dụng database nào 

Lombok đã cung cấp một annotation giúp tự sinh các constructor mặc định là `@NoArgsConstructor.`

Ví dụ: 
```
@NoArgsConstructor
public class NoArgsDemo1 {

  private Long id;
  
  private String username;
}
```

---------> 

```
public class NoArgsDemo1 {
  private Long id;
  private String username;
  public NoArgsDemo1() {
  }
}
```
----------------@Data-----------------------
```
public class Todo {

    private String title;
    private boolean complete;
    public Todo() { }         //   @NoArgsConstructor

    public Todo(String title, boolean complete) {   // @AllArgsConstructor
        this.title = title;
        this.complete = complete;
    }
    public String getTitle() {       // @Getter/@Setter
        return title;
    }

    public void setTitle(String title) {
        this.title = title;
    }
    public boolean isComplete() {
        return complete;
    }

    public void setComplete(boolean complete) {
        this.complete = complete;
    }
}
```
@ToString
``` Lomlocked
@ToString
public class LombokToStringDemo1 {

private Long id;

private String name;

private static boolean defaultStatus = false;

}
```
-----> 
``` Delumlocked
public class LombokToStringDemo1 {

private Long id;

private String name;

private static boolean defaultStatus = false;

@Override

public String toString() {

return "LombokToStringDemo1(id=" + this.id + ", name=" + this.name + ")";

}

}
```
@GeneratedValue: autogeneration để sinh ra giá trị cho khóa chính, nghĩa là phải có annotation @Id trước đó.
Mặc định là : 1,2,3,4,5,6,7,.......... Hoặc  là dãy các UUID như 8dd5f315-9788-4d00-87bb-10eed9eff566 nếu returntype của class là UUID

**@GeneratedValue (strategy = GenerationType.IDENTITY)**: giống với @GeneratedValue, khởi tạo từ 1,2,3,4,...

@GeneratedValue(generator = "sequence-generator") : giống với @GeneratedValue, những có thể thay đổi bước nhảy
Ví dụ:
![[Pasted image 20221028172958.png]]

do đó sẽ chạy từ, 4,6,8,10



-- Chú ý, nếu chỉnh sửa file dto và entity thì bắt buộc phải rebuild lại, click build -> rebuild project

****

Specification: công cụ để thực hiện truy vấn cơ sở dữ liệu với Spring hoặc Spring boot. Được xây dựng dựa trên Criteria API. Khi tạo 1 truy vấn Criteria phải xây dựng và quản lí các đối tượng
- Root
- CriteriaQuery
- CriteriaBuilder

----------
# JPA Query Language (JPQL)
JPA Query Language, sẽ định nghĩa các cây query dựa trên các entity chứ không dựa vào tên cột, bảng trong database 
Cấu trúc và cú pháp của JPA Query Language thì rất tương tự như cấu trúc và cú pháp của câu SQL
```SQL
SELECT ... FROM ...
[WHERE ...]
[GROUP BY ... [HAVING ...]]
[ORDER BY ...]
```
Khi chạy, Hibernate hay các thư viện của Implement JPA sẽ transform những câu query này sang SQL dành cho database
Lấy đối tượng Entity:
```java
EntityManagerFactory emf = Persistence.createEntityManagerFactory("jpaexample");
EntityManager em = emf.createEntityManager();
```

Sử dụng đối tượng EntityManager để lấy đối tượng Query dựa vào thông tin của entity Clazz;
```java
  
Query query = em.createQuery("SELECT c FROM Clazz c");
// c là alias
// SELECT c.name FROM Clazz c : lấy tên các cột trong
```

Lấy tất cả các Rcord trong bảng:
```1

List<Clazz> resultList = query.getResultList();
```
In ra:
```
resultList.stream().forEach(c -> System.out.println(c.getName()));
```
-------------
# Criteria API
So với JPQL, dynamite hơn, linh động và có thể tái sử dụng,và không bị `hardcode` trong một `String`
Nếu như trong JPQL: 
```sql
SELECT o FROM Office o
```
Thì trong Criteria API:
```java
CriteriaBuilder cb = em.getCriteriaBuilder();

CriteriaQuery<Office> q = cb.createQuery(Office.class);
Root<Office> c = q.from(Office.class);
q.select(c);
```


xét ví dụ sau:
```java
CriteriaBuilder builder = em.getCriteriaBuilder();

CriteriaQuery<Office> query =  builder.createQuery(Office.class);
Root<Office> root = query.from(Office.class);
query.select(root);
```
. CriteriaBuilder: giúp tạo ra đối tượng chứa câu lệnh truy vấn `CriteriaQuery` và cung cấp cơ số các phép biến đổi, phép logic, điều kiện cho câu lệnh (and, or, not, avg, greater than,v.v...)

. CriteriaQuery: đối tượng chính (được tạo ra bởi `builder.createQuery(Office.class)`). 
khai báo đối tượng bạn muốn lấy ra sau khi thực hiện query : 

```sql
SELECT `o` FROM Office o -> `o`
```
. Root: Khai báo đối tượng sẽ sử dụng trong query
```sql
SELECT o FROM `Office o` -> `Office o`

```java
query.select(root);
```
. Đẩy xuống database: (giống với JPQL)
```java
TypedQuery<Office> query = em.createQuery(query);
List<Office> results = query.getResultList();
```


Xét ví dụ sau: ```sql
SELECT o FROM Office o WHERE o.city = 'hanoi'

---> query.select(root).where(builder.equal(root.get("city"),"hanoi"))

```
Mình sử `builder` để lấy hàm `equal` (phép toán logic, như mình đề cập ở trên, chuẩn chưa nào). Tiếp tới là cái `root.get("city")`, `root` chính là đối tượng chúng ta đã khai báo, bây giờ chúng ta sẽ lấy trường `city` của nó và kiểm tra nó với `hanoi`.
```
-------
Tuy nhiên, phải tự nhó tên các column mỗi khi gọi, lại còn phải tìm các chỗ sử dụng column mỗi khi sửa đổi tên column 
-> tham chiếu các column của Table vào 1 Object, và chỉ có thể edit trong Object này. Object này đc gọi là Meta Model. Khi build jar sẽ tự động tạo Meta Model

class Meta Model của `User` sẽ tên là `User_`
User.java
```java
@Entity
@Data
@Builder
public class User {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private UserType type;
    private String name;

    public enum UserType {
        NORMAL, VIP;
    }
}
```
User_.java
```java
@Generated(value = "org.hibernate.jpamodelgen.JPAMetaModelEntityProcessor")
@StaticMetamodel(User.class)
public abstract class User_ {

	public static volatile SingularAttribute<User, String> name;
	public static volatile SingularAttribute<User, Long> id;
	public static volatile SingularAttribute<User, UserType> type;

	public static final String NAME = "name";
	public static final String ID = "id";
	public static final String TYPE = "type";

}
```
-------------
# Predicate
`Predicate` là một mệnh đề điều kiện trong câu lệnh truy vấn.
```java
        Predicate condition = builder.equal(root.get(User_.ID), id);

        query.select(root).where(condition);
```
`Predicate` có thể liên kết với nhau bằng các phép quan hệ `and`, `or`, `not`, v.v..
```java
 Predicate hasNameLike = builder.like(root.get(User_.NAME), name);
        Predicate hasType = builder.equal(root.get(User_.TYPE), type);

        Predicate condition = builder.and(hasNameLike, hasType);

        query.select(root).where(condition);
```
--------------
# Specification

được xây dựng giống Predicate trong Hibernate. Specification là 1 cách để định nghĩa các `Predicate` có thể tái sử dụng được

Với cách định nghĩa này, chúng ta có thể tái sử dụng query và tuỳ biến nó mọi lúc để phù hợp với yêu cầu.
Bản chất Specification là 1 functional interface
```java
public interface Specification<T> {
  Predicate toPredicate(Root<T> root, CriteriaQuery query, CriteriaBuilder cb);
}
```

Ví dụ: 
_User.java_
```java
@Entity
@Data
@Builder
public class User {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private UserType type;
    private String name;

    public enum UserType {
        NORMAL, VIP;
    }
}
```
_UserSpecification.java_: định nghĩa các static method, return là các implement của Specification
```java
public final class UserSpecification {
    /**
     * Lấy ra user có UserType chỉ định
     * @param type
     * @return
     */
    public static Specification<User> hasType(UserType type) {
        return (root, query, cb) -> cb.equal(root.get(User_.TYPE), type);
    }

    /**
     * Lấy ra user có id chỉ định
     * @param userId
     * @return
     */
    public static Specification<User> hasId(long userId) {
        return (root, query, cb) -> cb.equal(root.get(User_.ID), userId);
    }

    /**
     * Lấy ra user nằm trong tập ID chỉ định
     * @param userIds
     * @return
     */
    public static Specification<User> hasIdIn(Collection<Long> userIds) {
        return (root, query, cb) -> root.get(User_.ID).in(userIds);
    }
}
```

##  Để có thể sử dụng được `Specification`, bạn cần kế thừa `JpaSpecificationExecutor` từ Spring JPA

```java
public interface UserRepository extends JpaRepository<User, Long>,
                                        JpaSpecificationExecutor<User> {
}
```
Lúc này, ngoài các method truyền thống như `findAll()`, `findOne()`, `findBy()` thì bạn sẽ thấy xuất hiện các method mới có tham số đầu vào là `Specification<T>`:

```java
Optional<T> findOne(@Nullable Specification<T> var1);

List<T> findAll(@Nullable Specification<T> var1);

Page<T> findAll(@Nullable Specification<T> var1, Pageable var2);

List<T> findAll(@Nullable Specification<T> var1, Sort var2);

long count(@Nullable Specification<T> var1);
```

Sử dụng Specification.where() để xây dựng tập các điều kiện để query:
```java
// Lấy ra user nằm trong tập ID đã cho và có type là NORMAL
// hoặc lấy ra user có ID = 10
Specification conditions = Specification.where(UserSpecification.hasIdIn(Arrays.asList(1L, 2L, 3L, 4L, 5L)))
                                        .and(UserSpecification.hasType(UserType.NORMAL))
                                        .or(UserSpecification.hasId(10L));
//The **asList()** method of [**java.util.Arrays**](https://www.geeksforgeeks.org/array-class-in-java/) class is used to return a fixed-size list backed by the specified array
// L specifies an integer type, rather than a double
// Truyền Specification vào hàm findAll()
userRepository.findAll(conditions).forEach(System.out::println);
```

gọn:
```java
userRepository.findAll(Specification.where(hasIdIn(Arrays.asList(1L, 2L, 3L, 4L, 5L)))
                                    .and(hasType(NORMAL))
                                    .or(hasId(10L)))
              .forEach(System.out::println);
```


![[Pasted image 20221102144028.png]]

_existsById_(ID id) - returns boolean. Returns whether an entity with the given id exists.

**Toán tử dấu 2 chấm (::) trong Java hay còn được gọi là toán tử tham chiếu phương thức** trong java.

```java
PageRequest.of(0,5) tương đương với lấy ra page đầu tiên, và mỗi page sẽ có 5 phần tử
```

Những phần edit trong DTO sẽ hiển thị trên postman
Những phần trong Entity sẽ hiển thị trong database
Những phần vừa có trong entity, vừa có trong DTo , nếu được set(get) sẽ hiển thị data theo phương thức post (nghĩa là get từ dto- tương tác người dùng nhưng set cho database - server)

Answer có trong cột Inq-content, nhưng không tách riêng ra mà gộp chung với ask ---> query?
Không cần tạo Answer column, do đó entity không nhất thiết phải có phần @column answer.

Chỉ cần tạo AnswerList trong dto
Mục đích: phải trả về như sau:  FindOne
```
{	
	"code": 200,

    "type": "success",

    "message": "Operation Success",

    "data": { 
		    "id":"caf4e57e-3f9a-42d4-8fc3-eb5eefcc74ea
            "inquiryContent":"ask 4",
            "delFlag": "N",
			"userId": null,
            "answers":[
		
                {
                    "id":"05ae3932-0a73-4c24-b468-8fb73b94155d", // set
                    "inquiryContent":"ans 4.1",
                },
                {
                    "id":"a237d855-468b-4c19-82c6-802ae6fe9ea7",
                    "inquiryContent":"ans 4.2",
                }
			        ],
			"useYn": "Y"
			}
}
```

Phải tạo ra 1 dto mới chứa các part trên
Bây giờ phải tạo findbyInqID( ) để tìm ra , nghĩa là trong này phải có get()

if (object.get(inq_id) = object.get(id)):
	{
	answer.setdicid(object.get(id))
	answer.setdicinquiryContent(object.get(inq_content)
	}

answer.add(dic)
id = id[inq_id = id], get(Id)
inquiryContent = inq_content[inq_id = id]
```
   {
                    "id":"05ae3932-0a73-4c24-b468-8fb73b94155d",
                    "inquiryContent":"ans 4.1",
                }
```

-------


Chú ý:
Repository I`nqRepos.findOne/FindAll` : trả về Entity
`toDTO` trả về 1 phần tử
`toDTOs` trả về 1 list các phần tử
`XChecker.isNotEmpty(...) `: trả về TRUE nếu chuỗi đã cho là không empty.
`XChecker.isEmpty(..)`: trả về TRUE nếu chuỗi đã cho là empty.
`XChecker.isTrueThruMsg(boolean isFalse, String message)` : nếu sai trả về String message

spec : là 1 biến của query
find là find cái biến spec này. Ví dụ findOne(spec), findAll(spec)


inq_id : có nếu là answer, không có nếu là inquiry
Chỉ answer cho những inquiry chưa có answer. Đồng nghĩa với việc chúng không có inq_id

http://3.39.224.130/dashboards/

---------------------------
# Query
User.java
```java
@Entity
@Table(name = "user")
@Data
public class User implements Serializable {
    private static final long serialVersionUID = -297553281792804396L;

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    // Mapping thông tin biến với tên cột trong Database
    @Column(name = "hp")
    private int hp;
    @Column(name = "stamina")
    private int stamina;

    // Nếu không đánh dấu @Column thì sẽ mapping tự động theo tên biến
    private int atk;
    private int def;
    private int agi;
}
```
_  
UserRepository.java
```java
import org.springframework.data.jpa.repository.JpaRepository;
import org.springframework.data.jpa.repository.Query;
import org.springframework.data.repository.query.Param;
import org.springframework.stereotype.Repository;

@Repository
public interface UserRepository extends JpaRepository<User, Long> {
    List<User> findAllByAtk(int atk); // query mặc định , cấu trúc theo camel case

    List<User> findAllByAgiBetween(int start, int end);

	List<User> findAllByAgiGreaterThan(int agiThreshold); 
	
    @Query("SELECT u FROM User u WHERE u.def = :def") // query theo kieeir JPQL
    User findUserByDefQuery(@Param("def") Integer def);



    @Query(value = "SELECT * FROM Users u WHERE u.def = :def ", nativeQuery = true) // query theo kiểu Native SQL
    User findUserByDefQuery(@Param("def") Integer def);

    
}
```

_App.java_
```java
ApplicationContext context = SpringApplication.run(App.class, args);
UserRepository userRepository = context.getBean(UserRepository.class);
        
```
```java
serRepository.findAllByAgiBetween(25, 30).forEach(System.out::println);
```
```java
 userRepository.findAllByAgiGreaterThan(97) .forEach(System.out::println);
```
```java
userRepository.findAllByAtk(74).forEach(System.out::println);
```
```java
User user = userRepository.findUserByDefQuery(49);
System.out.println("User: " + user); // cũng giống như cách sử dụng trên
```
Tự định nghĩa Query methods: (muốn tự định nghĩa, ta dùng thêm anotation @Query), điều này chỉ xảy ra trong repository
-   The name of our query method must start with one of the following prefixes: _find…By_, _read…By_, _query…By_, _count…By_, and _get…By_.
-   If we want to limit the number of returned query results, we can add the _First_ or the _Top_ keyword before the first _By_ word. If we want to get more than one result, we have to append the optional numeric value to the _First_ and the _Top_ keywords. For example, _findTopBy_, _findTop1By_, _findFirstBy_, and _findFirst1By_ all return the first entity that matches with the specified search criteria.
-   If we want to select unique results, we have to add the _Distinct_ keyword before the first _By_ word. For example, _findTitleDistinctBy_ or _findDistinctTitleBy_ means that we want to select all unique titles that are found from the database.

```
@Transactional(propagation = Propagation.REQUIRED)
Nói với Spring rằng nếu có một transaction đang hoạt động thì nó sẽ sử dụng chung, nếu không có transaction nào đang hoạt động, method được gọi sẽ tạo một transaction mới. Đây là giá trị mặc định của _Propagation._
```

@_DecoratedWith_
Dùng để customize việc thực thi mapping
Ví dụ: Trong folder mapper sẽ có 2 file: 
CleanerDecorator:
```
public  abstract class CleanerDecorator implements CleanerMapper {  
  
    @Override
    ... (customize ra)
```

CleannerMapper: 
```
@Mapper  
@DecoratedWith(CleanerDecorator.class)  
public interface CleanerMapper extends IMapper<LoyCleanerDto, LoyCleanerEntity>
```

@Joincolumn
SQL
```
CREATE TABLE OrderItem (
    OrderItemId int NOT NULL,
    OrderNumber int NOT NULL,
    // ....
);


CREATE TABLE Item (
    ItemId int NOT NULL,
    OrderItemId int NOT NULL,
    PRIMARY KEY (ItemId ),
    FOREIGN KEY (OrderItemId ) REFERENCES OrderItem (OrderItemId )
    // ... 
);
```
```

@Entity
public class Item {
    @ManyToOne
    @JoinColumn(name = "fk_order") // đặt tên cho column muốn join
    private OrderItem orderItem;
    
    // .... link thực thể Item với primarykey từ thực thể OrderItem. Tên của cột primarykey trong thực thể Item được định danh bởi tên fk_order
}
```
![[Pasted image 20221114100306.png]]
![[Pasted image 20221114100047.png]]

Ví dụ Join Columns
![[Pasted image 20221114100732.png]]
![[Pasted image 20221114100741.png]]
![[Pasted image 20221114100945.png]]

stream() là cách thức để xử lí tập hợp dữ liệu
```
List<String> items = new ArrayList<String>();
items.add("one");
items.add("two");
items.add("three");
items.add("fore");
items.add("five");

Stream<String> stream = items.stream();

```
Gồm có :
- Cấu hình: map, filter
```
stream().filter(item -> item.startsWith("t"));
```

```
items.stream().map(item -> item.toUperCase());
```
Các tham số của bộ lọc và việc mapping được cấu hình thôi, chưa được xử lý
- Xử lý: collect, count, reduce

```
List<String> filtereds = items.stream() .filter( item -> item.startsWith("t") ) .collect(Collectors.toList()); 
// filtereds = ("two","three") 


List<String> mappeds = items.stream() .map( item -> item.toUpperCase()) .collect(Collectors.toList()); 
// mappeds = ("ONE", "TWO", "THREE", "FORE", "FIVE")
```

```
long countNum = items.stream() .filter(item -> item.startsWith("f")) .count();
```
Reduce trả về 1 giá trị đơn lẻ , gồm có Identity, Accumulator - đơn luồng  và combiner (chỉ dành cho parallel) - đa luồng 
```
String reduceds = items.stream() .reduce((acc, item) -> acc + " " + item) .get(); 
// reduceds = "one two three fore five"
//Lúc này, identity là ""
```
![[Pasted image 20221114135632.png]]

-----------
`@Deprecated` annotation được sử dụng để nói với các developer không nên sử dụng những API được chú thích bởi nó, vì có thể nó sẽ bị xoá bỏ trong tương lai hoặc không còn phù hợp hãy nên sử dụng những cái mới hơn, tiện ích hơn.

![[Pasted image 20221114155247.png]]
Khong commit các file này



```
    List<Predicate> predicates = new ArrayList<>();  
    Join<LoyCleanerEntity, SysUserEntity> customer = root.join("user", JoinType.INNER);  
    predicates.add(cb.equal(customer.get("id"), id));  
    predicates.add(cb.equal(customer.get("delFlag"), BaseConstant.KEY_NO));  
    predicates.add(cb.equal(customer.get("useYn"), BaseConstant.KEY_YES));  
    return cb.and(predicates.toArray(Predicate[]::new));  
}; // and tạo conjunction của 3 cái trên, tức là &&
```

Xem lại: 

toArray(): chuyển đổi ArrayList thành Array
Xem lại: https://www.geeksforgeeks.org/arraylist-array-conversion-java-toarray-methods/
```
.toArray(Predicate[]::new));
```

----
Có 2 kiểu create:
1. tạo 1 phần tử entity rỗng, set + get, nhét nó vào db, save nó
2. chạy for theo param là 1 list, set id nut hết và saveandflush nó

Có những kiểu update sau:
1. Tìm id, set cho nó (tuy nhiên ta phải copy sang cái khác, ví dụ: `LoyCleanerEntity tgtObj = thtUpdObj;`) 
2. Sử dụng `BeanUtils.copyProperties(source, target);`

Kiểu delete cũng giống như update, chỉ là đổi del Flag từ N thành Y

--> Cách tạo toàn bộ folder API postman được lấy từ cotnroller tạo ra từ application trong IntelliJ mà không cần phải tạo thủ công ( Lưu ý tên name nếu không có định nghĩa trong controller thì Postman sẽ tự name riêng):
B1- Link: http://localhost:8080/v3/api-docs
Link này có được là được lấy từ Swagger, gom hết tất cả các controller. Lưu ý phải add dependency của Swagger vào mới có thể lấy link này được 
Note thêm: Link swagger : http://smarteevina.ddns.net:8080/swagger-ui/index.html
B2 - Sau khi có được link, vào phần API của postman , Import Definition, sao đó dán link vào. THực ra có thể thay bằng link swagger cũng được 

-- Cách lấy thông tin của người sign in (access_token): vào  thư mục auth trong postman, nếu biết thông tin passord và username đăng nhập vào thì post thôi. Sẽ lấy được access_token.

-- Cách update cột update_by (người update - tức là người login):
Ngoài việc `tgtObj.setUpdatedBy(SecurityContextHolderCustom.getUserId());`
trong service, ta còn phải lấy thông tin của người login để update vào. Cụ thể là lấy access_token vừa lấy được, trong phần Auth của Put, chọn Type là Bearer Token, add access_token vào mục Token

-----------
```
final BeanWrapper src = new BeanWrapperImpl(source);  
java.beans.PropertyDescriptor[] pds = src.getPropertyDescriptors();
```

![[Pasted image 20221116095211.png]]
-- Lấy mô tả đặt tính cho mình bean/class đã được định nghĩa , quét bên trong và lưu chúng 


-----------
Các cách để declare string
1. String[] strAr1=new String[] {"Ani", "Sam", "Joe"}; //inline initialization  
2. String[] strAr2 = {"Ani", "Sam", " Joe"};  
3. String[] strAr3= new String[3]; //Initialization after declaration with specific size  
   strAr3[0]= "Ani";  
     strAr3[1]= "Sam";  
     strAr3[2]= "Joe";
------------
#Set trong java là một Collection không thể chứa các phần tử trùng lặp.

Set được triển khai bởi Hashset, LinkedHashset, Treeset hoặc EnumSet.

-   **HashSet** lưu trữ các phần tử của nó trong bảng băm, là cách thực hiện tốt nhất, tuy nhiên nó không đảm bảo về thứ tự các phần tử được chèn vào.
-   **TreeSet** lưu trữ các phần tử của nó trong một cây, sắp xếp các phần tử của nó dựa trên các giá trị của chúng, về cơ bản là chậm hơn HashSet.
-   **LinkedHashSet** được triển khai dưới dạng bảng băm với có cấu trúc dữ liệu danh sách liên kết, sắp xếp các phần tử của nó dựa trên thứ tự chúng được chèn vào tập hợp (thứ tự chèn).
-   **EnumSet** là một cài đặt chuyên biệt để sử dụng với các kiểu enum.

--> Khai báo:
`public` `interface` `Set<E>` `extends` `Collection<E>`
`Set<String> setA =` `new` `HashSet<String>();`

`Set setA =` `new` `EnumSet();`

`Set setB =` `new` `HashSet();`

`Set setC =` `new` `LinkedHashSet();`

`Set setD =` `new` `TreeSet();`
-- Các phương thức
![[Pasted image 20221116100317.png]]

```
public static String[] getNullPropertyNames (Object source) {  
    final BeanWrapper src = new BeanWrapperImpl(source);  // là cái LoyCleanerDto bọc toàn bộ source, nghĩa là source là tập con của src
    java.beans.PropertyDescriptor[] pds = src.getPropertyDescriptors();  
  
    Set<String> emptyNames = new HashSet<String>();  
    for(java.beans.PropertyDescriptor pd : pds) {  
        Object srcValue = src.getPropertyValue(pd.getName());  
        if (srcValue == null){  
            emptyNames.add(pd.getName());  
        };  
    }  
    String[] result = new String[emptyNames.size()];  
    return emptyNames.toArray(result);  
}
```


-----
Sử dụng #toArray: 
 --> toArray: ( được lấy từ interface Collection)
 Thông thường ta sẽ sử dụng 2 cấu trúc
 ```
 Object[] toArray() 
 <T> T[] toArray(T[] a)
```

Cấu trúc đầu không có tham số, ví dụ 
```
Object[] naturalNumbersArray = naturalNumbers.toArray();
```
phương thức toArray() phân bổ 1 mảnh mới với độ dài cùng với mảng natturalNumbersArray

Câu trúc thứ 2 có tham số:
```
Integer[] naturalNumbersArray = naturalNumbers.toArray(new Integer[naturalNumbers.size]);
```
`mảng.toArray(mảng mới nội dung : kích thước + loại )`

-----------

Phân biệt @NotNull, @NotEmpty, @NotBlank
**@NotNull**

CharSequence, Collection, Map or Array object cannot be null, however can be empty.

**@NotEmpty**

The CharSequence, Collection, Map or Array object cannot be null and not empty (size > 0).

**@NotBlank**

The string is not null and the length is greater than zero.

**Here are the examples**:

String test = null;
@NotNull: false
@NotEmpty: false
@NotBlank: false

String test = "";
@NotNull: true
@NotEmpty: false
@NotBlank: false

String test = " ";
@NotNull: true
@NotEmpty: true
@NotBlank: false

String name = "Some text";
@NotNull: true
@NotEmpty: true
@NotBlank: true

----------
Nhập /** để tạo note gồm các param và return

---------------
```
@Override  
@Transactional(readOnly = true)  
public Page<SysUserDto> findAll(Pageable paging, AdUserFilterVo filter) {  
  
    Specification<SysUserEntity> spec = (root, query, cb) -> {  
        Join<SysUserEntity, LoyMasterEntity> master = null;  
        Join<SysUserEntity, LoyCleanerEntity> cleaner = null;  
  
        List<Predicate> predicates = new ArrayList<>();  
        if ("N".equalsIgnoreCase(filter.getIsCleaner())) {  
            master = root.join("master", JoinType.INNER);  
        } else {  
            cleaner = root.join("cleaner", JoinType.INNER);  
        }  
  
        if (!XChecker.isBlank(filter.getActive())) {  
            predicates.add(cb.equal(root.get("useYn"), filter.getActive()));  
        }  
        if (!XChecker.isBlank(filter.getEmail())) {  
            predicates.add(cb.equal(root.get("email"), filter.getEmail()));  
        }  
  
        if (!XChecker.isBlank(filter.getFullName())) {  
            if (XChecker.isNotNull(master)) {  
                predicates.add(cb.equal(master.get("bioName"), filter.getFullName()));  
            }  
            if (XChecker.isNotNull(cleaner)) {  
                predicates.add(cb.equal(cleaner.get("bioName"), filter.getFullName()));  
            }  
        }  
  
        if (!XChecker.isBlank(filter.getCertNumber())) {  
            if (XChecker.isNotNull(master)) {  
                predicates.add(cb.equal(master.get("certNumber"), filter.getCertNumber()));  
            }  
            if (XChecker.isNotNull(cleaner)) {  
                predicates.add(cb.equal(cleaner.get("certNumber"), filter.getCertNumber()));  
            }  
        }  
        return cb.and(predicates.toArray(Predicate[]::new));  
        
        // Giống như : Integer[] naturalNumbersArray = naturalNumbers.toArray(new Integer[naturalNumbers.size]); //
        
    };  
    return sysUserRepo.findAll(spec, paging).map(UserMapper.INSTANCE::toDTO);  
  
}
```
Hàm findAll có 2 tham số Pageale và sử dụng AdUserFilerVo
Query Specification: Đầu tiên cho null cho các biến join là master và cleaner  khi join với sysuser
Tạo list các predicate : Predicate là một interface chức năng chung đại diện một hàm mệnh đề mà trả lại giá trị boolean. Nở trong gói java.util.function package
Check tại các cột IsCleaner phải "N" hay ko, active, email và fullname có rỗng hay ko, khi đó , add các query / boolean đó vào list predicate
++ Lưu ý: cái spec thì return về array các predicate
++ Return cuối cùng là  theo spec và paging

```
@Override  
public int deleteById(String id) {  
    final Optional<SysUserEntity> tgtDelObj = sysUserRepo.findById(id);  
    tgtDelObj.ifPresentOrElse(s -> {  
        if (BaseConstant.KEY_NO.equalsIgnoreCase(s.getDelFlag())) {  
            log.info("Disable user {}", s.getUsername());  
            SysUserEntity tgtObj = tgtDelObj.get();  
            tgtObj.setDelFlag(BaseConstant.KEY_YES);  
            sysUserRepo.save(tgtObj);  
        } else {  
            log.info("User {} already disabled", s.getUsername());  
        }  
    }, () -> {  
        throw new ServiceException(AjaxMsgTypeEnum.DATA_NOT_FOUND.getDefMessage());  
    });  
    return 1;  
}
```
Cấu trúc **ifPresentOrElse(Consumer, Runnable)**
```
ifPresentOrElse(Consumer, Runnable)
public void ifPresentOrElse(Consumer<T> action,
                            Runnable emptyAction)
```
Chỉ dùng cho Optional Object.
-> Perform cái Consumer action giá trị của Obtional object này
-> Nếu không có giá trị trong Obtional này (tức là ko có object), thì thực hiện Runnable
Một phương pháp để copy dữ liệu từ entity này sang kia:
```
Optional<SysUserEntity> tgtDelObj = sysUserRepo.findById(id);
SysUserEntity tgtObj = tgtDelObj.get();
```

```
@Override  
@Transactional  
public int updatePerInfo(SysUserDto dto) {  
    Optional<SysUserEntity> user = sysUserRepo.findById(dto.getId());  
    if (!user.isPresent()) {  
        return 0;  
    }  
  
    try {  
        if (XChecker.isNotNull(dto.getMaster())) {  
        // lấy ra những hàng của SysUserEntity, dò trong cột id cột nào đã được map trong bảng LoyMasterEntity thì lấy hết, mỗi hàng là 1 object. Trường hợp ở đây chỉ lấy 1 hàng thôi
            LoyMasterEntity masters = user.get().getMaster();
            // Ở bước này chỉ mới copy cho biến masters, chưa có set  
            BeanUtils.copyProperties(dto.getMaster(), masters);  
            masters.setUser(user.get());  
            masterRepo.save(masters);  
        }  
        if (XChecker.isNotNull(dto.getCleaner())) {  
            LoyCleanerEntity cleaner = user.get().getCleaner();  
            BeanUtils.copyProperties(dto.getCleaner(), cleaner);  
            cleaner.setUser(user.get());  
            cleanerRepo.save(cleaner);  
        }  
  
        //Delete old document: 1: certificate number  
    // hàm deleteAllByDocType dùng để quét trong documentEntity, những hàng nào có docTYpe là 1 và delFlag là "N" thì đổi delFlag thành "Y"
        documentService.deleteAllByDocType("1", dto.getId());  
        for (int i = 0; i < dto.getDocuments().size(); i++) {  
            DocumentsVo doc = dto.getDocuments().get(i);  
    // decode nội dung content trong doc (DocumentsVO)
            documentService.createDocumentByUserId(doc.getFileType(), dto.getId(), Base64.getDecoder().decode(doc.getContent()), "", "", doc.getFormat());  
        }  
    } catch (Exception ex) {  
        log.error("ERROR", ex);  
        return 0;  
    }  
    return 1;  
}
```

http://3.39.224.130/apps/expert/list/
http://localhost:8080/v3/api-docs

---------
@tag trong controller chỉ để đặt tên controller đó là gì

SecurityContextHolderCustom là 1 class, trong class này có định nghĩa 2 function getUserId  getUsername 

@JsonProperty (value = "abc") cũng tương tự như @JsonProperty ( "abc"): dùng để định nghĩa logical property
Ví dụ:
```
@JsonProperty("bookCategory")	
private String category;
```
thì thuộc tính là bookCategory, nếu không đặt name thì mặc định thuộc tính là category

-------
Document liên quan đến load file
Phương thức join
```
String gfg1 = String.join(" < ", "Four", "Five", "Six", "Seven");
```
Four < Five < Six < Seven

------

**Các loại kiểm tra sau:**

object.isPresent() : có xuất hiện object nào không

XChecker.isNotNull(dto.getMaster())
->XChecker.isNull() : hoặc isNotNull: kiểm tra object đó có null hay không. getMaster có thể trả về 1 string hoặc 1 object

StringUtils.isBlank(documentType), documentType là 1 biến String

--------
Lưu ý 1 điều:
Nếu ta gọi 
```
Optional<SysUserEntity> user = ....
```
Để copy, ta phải dùng get():
```
SysUserEntity usercopy = user.get()
```
Vì bản chất user là 1 optional, nên KHÔNG THỂ DÙNG :
```
SysUserEntity usercopy = user
```
------
UUID (Viết tắt của Universally Unique Identifier), còn được gọi là GUID (Globally Unique Identifier) là một giá trị duy nhất dài 128 bit. Một chuỗi UUID chuẩn sử dụng chữ số hex (octet):

> 0710a5ca-f57e-11e9-802a-5aa538984bd8

![](https://images.viblo.asia/74fbd277-6c7e-4d1f-9687-a52d21497c94.png)Mục đích của UUID sinh ra là bởi vì:

-   Dữ liệu lớn, kiểu khóa chính auto imcrement cần nhiều byte để lưu hơn. Và khóa chính kiểu này không phù hợp khi mà hệ thống có nhiều server, nhiều client cùng lúc truy cập trên toàn thế giới.
-   Nếu dùng khóa chính kiểu auto imcrement, có thể dễ dàng truy ra được trong database có bao nhiêu record. Thường thấy ở đường dẫn kiểu "[domain.com/user/12345](http://domain.com/user/12345)".

Bởi vậy UUID ra đời nhằm khắc phục những yếu điểm trên. Vậy nếu bạn đủ sức xây dựng một hệ thống với nhiều server, phục vụ hàng tỉ tỉ user hoặc chỉ đơn giản là không muốn để lộ id ra ngoài, hãy nghĩ tới UUID.

----------------
  
Date() -> Tạo một đối tượng Date đại diện cho ngày tháng và thời gian hiện tại.
Cách khai báo 1 root path trong service:

```
@Value("${application.document.rootPath}")  
private String rootPath;
```


```java
FileUtils.writeByteArrayToFile(outputFile, dataForWriting);
```
-> Writes a byte array to a file creating the file if it does not exist.
The _FileUtils.writeByteArrayToFile_ method is similar to the other methods that we've used in that we give it a _File_ representing our desired destination and the binary data we're writing. **If our destination file or any of the parent directories don't exist, they'll be created.**

Ví dụ
```
FileUtils.writeByteArrayToFile(new File(fullPath + "/" + _fileName + "." + format), bytes);
```

DocumentEntity document = createFile(bytes, userId, filename, format);

StringUtils.EMPTY : tức là ""

_randomAlphabetic_() is a static method of the _RandomStringUtils_ class which is used to generate random strings consisting of alphabetic characters.
VÍ dụ: `String resetToken = RandomStringUtils.randomAlphabetic(6);`

--------------
Trong thiết kế database không tồn tại quan hệ nhiều nhiều chính vì vậy mà mình có thêm một bảng trung gian ở giữa để bẻ mối quan hệ nhiều nhiều thành 2 mối quan hệ một nhiều .
--> Trong Java chúng ta sử dụng annotation **@ManyToMany** để thể hiện mối quan hệ nhiều nhiều.

Ở bảng sysuser 
```
@ManyToMany(fetch = FetchType.EAGER)  
@JoinTable(  
        name = "sys_auth_role",  
        joinColumns = @JoinColumn(name = "user_id"),  
        inverseJoinColumns = @JoinColumn(name = "role_id")  
)  
private Set<RoleEntity> roles;
```
Bảng sys_auth_role được auto tạo ra nhằm giúp liên kết 2 bảng sysuser và sysrole
ở bảng sysrole
![[Pasted image 20221129135257.png]]
```
@ManyToMany(mappedBy = "roles", fetch = FetchType.EAGER)  
private Set<SysUserEntity> users;
```
![[Pasted image 20221129135219.png]]
![[Pasted image 20221129135240.png]]

user.setRoles(roles); thì set trong bảng auth-role

--------------
```
  public interface AuthenticationManager {

  Authentication authenticate(Authentication authentication)
    throws AuthenticationException;

}
```
method authenticate(): 
1. Trả về 1 object Authentication (thường thì với trường hợp attribute authenticated=true) nếu nó kiểm tra được các giá trị input là hợp lệ. 
2. Trả về 1 exception (AuthenticationException) nếu các giá trị input không hợp lệ 
3. Trả về null nếu nó không thể xử lý.

```
 public interface AuthenticationProvider {

    Authentication authenticate(Authentication authentication)
            throws AuthenticationException;

    boolean supports(Class<?> authentication);

}
```

------------
Spring Security: có 2 thuật ngữ SecurityContext và SecurityContextHolder

-`SecurityContext` : Lưu trữ details của user đã được authenticated
-SecurityContextHolder : 
+ là 1 class cung cấp các phương thức để truy cập SecurityContext, tức là SecurityContextHolder lưu trữ SecurityContext.
+ Ngoài việc lưu trữ SecurityContext, có còn lưu trữ cách thức mà SecurityContext được dữ trữ: Ví dụ có mode `MODE_GLOBAL`, MODE_THREADLOCAL ,...
-> để lấy username, cần phải có `SecurityContext` và được lấy từ `SecurityContextHolder` nhờ vào việc gọi phương thức` getAuthentication()`

----------
@EntityListeners(AuditingEntityListener.class)
@EntityListeners: để specify các class được callback listener
-> Now we can capture auditing information by the listener upon persisting and updating the  entity.

------
![[Pasted image 20221202160848.png]]


------------
regex:

```
@Pattern(regexp="^[a-zA-Z0-9]{3}",message="length must be 3")  
private String pass;
```

-----
Chú ý:
```
@Repository  
public interface TransportRepository extends BaseRepository<TransportInfoEntity> {  
  @Query(value =  
      "select tti.*, tc1.ctry_name toCtryName, tc2.ctry_name frmCtryName "  
      + "FROM tb_transport_info tti, tb_country tc1,tb_country tc2 "  
      + "WHERE tti.frm_ctry_cde = tc1.ctry_cde "  
      + "AND tti.to_ctry_cde = tc2.ctry_cde", nativeQuery = true)  
  Page<Map<String, String>> findAllTransInf(Pageable pageable);
```

Nên dùng page map để parse dữ liệu tên cột và tên value dưới dạng String - String

-------------
[prj-delivery-service-api | Trello](https://trello.com/b/WUBjhrT7/prj-delivery-service-api)

Chú ý những thứ liên quan đến Document trong Loyal-Cleaner:

API get - detail: quét ID trong bảng loyal cleaner, trả thông tin về người này. Lấy thông tin user_id của người này, query trong bảng documentEntity để tìm ra list với thông tin user_id trùng với thông tin user_id của documentEntity

API get - basic-info: tương tự như vậy, nhưng thông tin được set vô response trong mục content đã được mã hóa dưới dạng Base64. Thông tin user_id của cleaner trùng với user_id của document. Sau đó lấy id của documentEntity vừa query được và set thông tin chứa id đó dưới dạng mã như đã nói ở trên

-------------

module : nhập vô các service, thực hiện chức năng cho controller
- Hỏi bé hà: vấn đề về ảnh -> đang resolving

Nhập 1 request gồm thông tin list các ảnh - các dtos
Quét từng dto trong dtos đó, lấy các thông số type, userID( người dùng đang truy cập), filename = "" , content và format đẩy vô cho hàm createDocumentByUserID cho nó hoạt động
```
createDocumentByUserId(
t.getFileType(), 
userId, 
Base64.getDecoder().decode(t.getFileContent()),  
"",  
t.getFileFormat());
```
->> Hàm createDocumentByUserId: 
```
createDocumentByUserId(
String documentType, 
String userId, 
byte[] bytes, 
String filename, 
String format)
```
Nếu docymentType là 5 - ảnh ava -> xóa
Sau đó thẩy các thông số cho createFile thực hiện
```
createFile(bytes, StringUtils.EMPTY, filename, format)
```
Và set UserID và documentype cho document -> lưu

->> Hàm createFile
```
createFile(byte[] bytes, String filePath, String fileName, String format)
```
Đẩy các thông số cho createIFile làm: 
```
FileCommonUtils.createFile(bytes, filePath, fileName, format)
```
set các biến format, name, path và system


---> Hàm createFile con

```
createFile(  
    byte[] bytes, String path, String fileName, String format)
```
Chú ý vô 
*** fileName, 
* nếu có thì filename_ = filename + ". " + format, 
* nếu không thì filename_ = randomUUID + ". " + format
*** folder:
+ nếu blank thì folder = năm/tháng/ngày hiện tại
+ nếu có thì folder = path
*** fullPath: rootPath/folder , với rootPath là: C:/ .....
Cuối cùng return về hàm 
```
FileInfo(_fileName, folder, fullPath, format, bytes.length)
```

kết quả trả về:
```
public FileInfo(String fileName, String path, String fullPath, String format, int size) {  
    this.fileName = fileName;  
    this.path = path;  
    this.fullPath = fullPath;  
    this.format = format;  
    this.size = size;  
}
```

-----

[Project - Progress - Dev .xlsx - Google Trang tính](https://docs.google.com/spreadsheets/d/1ZXa2KUbI5RfHBL2jcQmrRkpfaKuV1rBI/edit#gid=3537845)
http://3.35.222.15:8080/swagger-ui/index.html#/
https://www.figma.com/file/gWDiWQCON742Lk8Yyjn4mx/%5BENG%5D-Maple-Delivery?node-id=0%3A1&t=0WtW2vkTW9SgpQgI-1

Online appication form: app formjoinpurchase
Additional group application form: product
group purchases in progress: join purchase
đầu tiên fetch về, check out nhánh dev, pull về, stash cái của mình, sau đó merge về nhánh BO-Phong, sau đó đẩy lên nhánh BO- Phong, tiếp theo click vô stash để apply xem có bị lỗi gì ko, nếu có gì sửa

-----
https://www.iban.com/country-codes
code 2 và 3
https://za.zalo.me/v3/verifyv2/pc?token=OcBtoTbmK0Pa2_J4sXjGO6CDwwhV751WOmthgZCm&continue=https%3A%2F%2Fmapleposts.com%2Frate-cc%2F
http://3.35.222.15:8080/swagger-ui/index.html#/
-------------
Hàm .exists(spec) có sẵn trong thư viện của spring boot trả về boolean
ví dụ 
```
@Transactional(readOnly = true)  
public boolean existByUsername(String username) {  
  Specification<AccountEnity> spec =  
      (root, query, cb) -> cb.and(cb.equal(root.get("username"), username));  
  return repo.exists(spec);  
}
```
.count(spec) : trả về số lượng đạt yêu cầu spec
Hàm Array.asList(array nào đó) để chuyển về dạng list
[Chuỗi nào đó].split(the delimiting regular expression) : trả về dạng array bởi delimiting
![[Pasted image 20221216135859.png]]
![[Pasted image 20221216140157.png]]

Cách hoạt động của :SecurityContextHolderCustom
RequestEntity : để determine the availability of delivery
---> Pending : Quản lí việc vận chuyển
---> Doing: Quản lí mua chung

-------------
- chuyenr đổi object về dạng json
Gson().toJson()
- Dùng class # MessageFormat để format, gồm có .format(), .parse()...
https://www.geeksforgeeks.org/messageformat-format-method-in-java-with-example-set-2/?ref=rp

```
public static String format(String pattern,
                            Object... arguments)
```
kí hiệu Object... : detructoring - nghĩa là danh sách các object
Return Value: This method returns string value which will have the formatted array of object in string format.

Ví dụ: 
![[Pasted image 20221220161525.png]]
-> formatted array : 4.2


-----
http://43.201.27.152/
![[Pasted image 20221221115416.png]]

-----------
(thời gian dưới định dạng giờ phút giây-String).plusHours(3): cộng h thêm 3
![[Pasted image 20221221120536.png]]

time1.isAfter(time2) : trả về boolean
.getDayofMonth()
![[Pasted image 20221221135718.png]]

--------------
Phân biệt khái niệm encoding, encryption và hash
- **encoding**: dùng chỉ biến đổi data thành 1 format khác dựa trên một quy chuẩn nào đó. Và quy chuẩn ở trên của chúng ta sẽ là ASCii.
- **encryption**:  1 quy trình mã hóa **2 chiều**. Sau khi mã hóa, ta hoàn toàn có thể **dùng secret-key** để giải mã và lấy ra plain-text ban đầu.
- **Hashing** không có key như vậy. Và tất nhiên nó là quy trình chỉ có **1 chiều** mã hóa chứ không giải mã được.

_SHA256_ online hash function. Cách sử dụng: 
```
XEncrypUtils.SHA256(chuỗi nào đó)
```
------------

`FileUtils.writeByteArrayToFile`: Writes a byte array to a file creating the file if it does not exist.
Ví dụ: 
`FileUtils.writeByteArrayToFile(new File(fullPath, _fileName), bytes);`

Có 2 cách để new File
`new File(path)` : tức là path chính
`new File(parent path, child path)`: từ là gộp path cha và con thành path chính


https://developer.dhl.com/api-reference/warehouse-management#get-started-section/

casecadeType:
![[Pasted image 20230217161838.png]]