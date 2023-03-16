** The name of the java file **must match** the class name, tên phải được viết hoa chữ cái đầu
dùng terminal chạy : javac [tên file].java
Sau đó chạy: java [tên file]
System.out.print thì in ngang, trong khi println thì new line

** lưu ý final đóng vai trò như const
```java
final int myNum = 15;
myNum = 20;  // will generate an error: cannot assign a value to a final variable
```
```java
char myLetter = 'D';
```
```java
String myText = "Hello";
```

** declare multi values:
````java
int x = 5, y = 6, z = 50;
````
** nên khai báo float và double có chữ f và d phía sau

```java
float myNum = 5.75f;
```
** widen casting :
```java
int myInt = 9;
    double myDouble = myInt; -> 9.0
```
narrow casting"
```java
double myDouble = 9.78d;
    int myInt = (int) myDouble; -> 9
```

** string: 
(string là 1 chuỗi nào đó)
string.length()
string.toUpperCase()
string.toLowerCase()
string.indexOf()
text1.concat(text2) : có dấu cách

**
![](https://i.imgur.com/TSwMLgI.png)

** Math:

Math.max(x,y)
Math.min(x,y)
Math.sqrt(x)
Math.abs(x)
Math.random() trả về 0<= x < 1
Ví dụ trả về random trong khoảng từ 0 đến 100: 
```java
int randomNum = (int)(Math.random() * 101)
```

Math.floor()
Math.cell()
Math.round()

** Ternary operator:
```java
variable = (condition) ? expressionTrue :  expressionFalse;
```
** switch case: 
```java
switch(expression) {
  case x:
    // code block
    break;
  case y:
    // code block
    break;
  default:
    // code block
}
```

** while / do while/for: 
```java
int i = 0;
while (i < 5) {
  System.out.println(i);
  i++;
}
```
```java
int i = 0;
do {
  System.out.println(i);
  i++;
}
while (i < 5);
```
```java
for (int i = 0; i < 5; i++) {
  System.out.println(i);
}
```

** for-each loop chỉ dành cho array
```java
for (type variableName : arrayName) {
  // code block to be executed
}
```

** array:
```java
.length()
```
```java
String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
```
```java
cars[0] = Volvo
```
tạo mảng 2 chiều:
```java
int[][] myNumbers = { {1, 2, 3, 4}, {5, 6, 7} };
int x = myNumbers[1][2];
System.out.println(x); // Outputs 7
```

** method: 
```java
public class Main {
  static void myMethod() { // static tức là method myMethod thuộc về class Main, ko phải thuộc về object của class Main. Void tức là ko return
    // code to be executed
  }
}
```
method nếu gán biến: phải có type
```java
myMethod(String fname)
```

nếu có return, bỏ void, thay vào đó :
```java
public class Main {
  static int myMethod(int x) {
    return 5 + x;
  }

  public static void main(String[] args) {
    System.out.println(myMethod(3));
  }
}
```

** method overloading:  tên trùng nhau, miễn khai báo parameter khác nhau
```csharp
int myMethod(int x)
float myMethod(float x)
double myMethod(double x, double y)
```

** biến chỉ tồn tại trong scope : method scope và block scope
**Sự khác nhau giữa static và public:
```java
public class Main {
  // Static method
  static void myStaticMethod() {
    System.out.println("Static methods can be called without creating objects");
  }

  // Public method
  public void myPublicMethod() {
    System.out.println("Public methods must be called by creating objects");
  }

  // Main method
  public static void main(String[ ] args) {
    myStaticMethod(); // Call the static method
    // myPublicMethod(); This would output an error

    Main myObj = new Main(); // Create an object of Main
    myObj.myPublicMethod(); // Call the public method
  }
}

```
The `static` keyword is a non-access modifier used for methods and attributes. Static methods/attributes can be accessed without creating an object of a class.
** OOP
- gọi
```java
public class Main { // khai báo class
  int x = 5;

  public static void main(String[] args) {
    Main myObj = new Main(); // khai báo object
    System.out.println(myObj.x);
  }
}
```

- multiple class:
![](https://i.imgur.com/VcKNo0y.png)
phải chạy
`javac Main.java` để tạo Main.class
`javac Second.java` để tạo Second.class
sau đó chạy `java Second`

- attribute:
```java
public class Main {
  int x = 5; //là 1 attribute
  int y = 3; // là 1 attribute
}
```

- Sự khác nhau static và public cho method và cho class 
**static method thì gọi trực tiếp, public phải tạo object mới gọi đc nó**
```java
myStaticMethod(); // Call the static method
    // myPublicMethod(); This would compile an error

    Main myObj = new Main(); // Create an object of Main
    myObj.myPublicMethod(); // Call the public method on the object
```

- class constructor:
```java
// Create a Main class
public class Main {
  int x;

  // Create a class constructor for the Main class
  public Main() {  // bản chất là 1 method, dùng để thiết lập initial values, phải có tên viết hoa y chang class, ko đc return (giống method có void)
    x = 5;
  }

  public static void main(String[] args) {
    Main myObj = new Main();
    System.out.println(myObj.x);
  }
}

```
khi gán para vào method constructor, thì lúc tạo object call method này phải có đối số

- modifier:
![](https://i.imgur.com/fHmSRnC.png)
![](https://i.imgur.com/Zu2Bq5d.png)


- encapsulation: 
các variables và attributes là private
```java
public class Person {
  private String name; // private = restricted access

  // Getter
  public String getName() {
    return name;
  }

  // Setter
  public void setName(String newName) {
    this.name = newName;
  }
}
```
```java
public class Main {
  public static void main(String[] args) {
    Person myObj = new Person(); // myObj.name = "John";  // error
    myObj.setName("John"); // Set the value of the name variable to "John"
    System.out.println(myObj.getName());
  }
}
```

- import class/package:
```java
import package.name.Class;   // Import a single class
import package.name.*;   // Import the whole package
```
```java
import java.util.Scanner; //java.util là package, Scanner là class
//package java.util gồm có date and time facilities, random-number generator and other utility classes.
```
[https://docs.oracle.com/javase/8/docs/api/](https://docs.oracle.com/javase/8/docs/api/).
- nhập thông tin:


```java
import java.util.Scanner; // import the Scanner class 

class Main {
  public static void main(String[] args) {
    Scanner myObj = new Scanner(System.in);
    String userName;
    
    // Enter username and press Enter
    System.out.println("Enter username"); 
    userName = myObj.nextLine();   // đọc toàn bộ line, nexLine là method
       
    System.out.println("Username is: " + userName);        
  }
```

- package tự định nghĩa : 
tạo 1 file java, sau đó code: 
```java
package mypack;
class MyPackageClass {
  public static void main(String[] args) {
    System.out.println("This is my package!");
  }
}
```
chạy terminal: javac MyPackageClass.java
sau đó : javac -d . MyPackageClass.java để tạo thư mục ngay tại folder chứa file java đó luôn, folder này chính là package
chạy file: java mypack.MyPackageClass

- Inheritant:  lets us inherit attributes and methods from another class.
```java
class Vehicle
class Car extends Vehicle 
```

- inner class:
```java
class OuterClass {
  int x = 10;

  class InnerClass {
    int y = 5;
  }
}

public class Main {
  public static void main(String[] args) {
    OuterClass myOuter = new OuterClass();
    OuterClass.InnerClass myInner = myOuter.new InnerClass(); // chú ý
    System.out.println(myInner.y + myOuter.x);
  }
}
```

- polymophism: uses those methods to perform different tasks
- Tinhs tuu tượng:
--   **Abstract class:** ko được sử dụng để tạo object, it must be inherited from another class
  
--   **Abstract method:** can only be used in an abstract class, and it does not have a body. The body is provided by the subclass (inherited from).
```java
// Abstract class
abstract class Animal {
  // Abstract method (does not have a body)
  public abstract void animalSound();
  // Regular method
  public void sleep() {
    System.out.println("Zzz");
  }
}

// Subclass (inherit from Animal)
class Pig extends Animal {
  public void animalSound() {
    // The body of animalSound() is provided here
    System.out.println("The pig says: wee wee");
  }
}

class Main {
  public static void main(String[] args) {
    Pig myPig = new Pig(); // Create a Pig object
    myPig.animalSound();
    myPig.sleep();
  }
}
```

- interface: abtract class thuần , class con dùng implements thay vì extends
```java
// interface
interface Animal {
  public void animalSound(); // interface method (does not have a body)
  public void run(); // interface method (does not have a body)
}
class Pig implements Animal 
```
Multiple Interfaces: 
```java
class DemoClass implements FirstInterface, SecondInterface
```

- Class chứa các giá trị hằng:
```java
enum Level {
  LOW,
  MEDIUM,
  HIGH
}
```
-> `Level myVar = Level.MEDIUM;`

- Các loại input:
![](https://i.imgur.com/OG5gVTf.png)

- Date: 
package: java.time
class: 
![](https://i.imgur.com/j65OCNE.png)

method: .new() là thời điểm hiện tại
ĐỔI FORMAT:
```java
import java.time.LocalDateTime; // Import the LocalDateTime class
import java.time.format.DateTimeFormatter; // Import the DateTimeFormatter class

public class Main {
  public static void main(String[] args) {
    LocalDateTime myDateObj = LocalDateTime.now();
    System.out.println("Before formatting: " + myDateObj);
    DateTimeFormatter myFormatObj = DateTimeFormatter.ofPattern("dd-MM-yyyy HH:mm:ss");

    String formattedDate = myDateObj.format(myFormatObj);
    System.out.println("After formatting: " + formattedDate);
  }
}
```

- Array vs Array List: 
Element trong AL là object, Ele trong Array là varies
Array List có thể thêm xoá , Array thì ko
Arrlist: [a,b,c]  ------   Array: {a,b,c}
```java
import java.util.ArrayList;

public class Main {
  public static void main(String[] args) {
    ArrayList<String> cars = new ArrayList<String>(); //tạo mảng rổng
    cars.add("Volvo"); // thêm phần tử vào mảng
    cars.add("BMW");
    cars.add("Ford");
    cars.add("Mazda");
    System.out.println(cars);
  }
}
```

Access của ArrayList:` cars.get(0);`
Access của Array: `cars[0]`

Change của ArrayList: `cars.set(0, "Opel");`
Change của Array: `cars[0] = "Opel";`

Remove của ArrayLisst: `cars.remove(0);`

Clear sạch của ArrayList: `cars.clear();`

Size của ArrayList: `cars.size();`
Size của Array: `cars.length`

Loop của ArrayList = Loop của List :
```java
for (int i : myNumbers) {
      System.out.println(i);
    }
```

Sort của ArrayList: dùng .sort()
```java
import java.util.ArrayList;
import java.util.Collections;
...
Collections.sort(cars);
```

- LinkedList vs ArrayList: giống toàn bộ, khác nhau ở vài method chỉ có ở LinkedList
```java
import java.util.LinkedList;

public class Main {
  public static void main(String[] args) {
    LinkedList<String> cars = new LinkedList<String>();
```
![](https://i.imgur.com/ecErOsz.png)

- Hashmap: giống như dictionary {key1=value1,key2=value2,..}

```java
import java.util.HashMap; // import

public class Main {
  public static void main(String[] args) {
    // Create a HashMap object called capitalCities
    HashMap<String, String> capitalCities = new HashMap<String, String>();
// hoặc <String, Int> tuỳ
    // Add keys and values (Country, City)
    capitalCities.put("England", "London");
    capitalCities.put("Germany", "Berlin");
    capitalCities.put("Norway", "Oslo");
    capitalCities.put("USA", "Washington DC");
    System.out.println(capitalCities);
  }
}
```
->  

{USA=Washington DC, Norway=Oslo, England=London, Germany=Berlin}

Access: 
```java
capitalCities.get("England");
```
Remove:
```java
capitalCities.remove("England");
```
Clear:
```java
capitalCities.clear();
```
Size:
```java
capitalCities.size();
```
.keySet() và capitalCities.values() trả về ArrayList

- HashSet: các phần tử unique
```java
import java.util.HashSet; // Import the HashSet class

HashSet<String> cars = new HashSet<String>();
```
Add:
```java
 cars.add("Volvo");
```
Remove: 
```java
cars.remove("Volvo");
```
Clear:
```java
cars.clear();
```
Size:
```java
cars.size();
```
Check có hay ko:
```java
cars.contains("Mazda");
```
Loop:
```java
for (String i : cars) {
  System.out.println(i);
}
```

- Iterator: 
Duyệt các phần tử từ đầu đến cuối của một collection.
Iterator cho phép xóa phần tử khi lặp một collection.
![](https://i.imgur.com/4VEqXNw.png)

```java
import java.util.ArrayList;
import java.util.Iterator;

public class Main {
  public static void main(String[] args) {

    // Make a collection
    ArrayList<String> cars = new ArrayList<String>();
    cars.add("Volvo");
    cars.add("BMW");
    cars.add("Ford");
    cars.add("Mazda");

    // Get the iterator
    Iterator<String> it = cars.iterator();

    // Print the first item
    System.out.println(it.next()); // trả về Volve : tức là phần tử hiện tại
  }
}
```

```java
import java.util.ArrayList;
import java.util.Iterator;

public class Main {
  public static void main(String[] args) {
  
    // Make a collection
    ArrayList<String> cars = new ArrayList<String>();
    cars.add("Volvo");
    cars.add("BMW");
    cars.add("Ford");
    cars.add("Mazda");
  
    // Get the iterator
    Iterator<String> it = cars.iterator();
    
    // Loop through a collection
    while(it.hasNext()) {
      System.out.println(it.next()); // trả về volve, bmw, ford, mazda không có gộp chugn trong 1 arraylish
    }
  }
}

```

remove phần tử đối với 1 collection đang ngày càng size nhỏ 
```java
import java.util.ArrayList;
import java.util.Iterator;

public class Main {
  public static void main(String[] args) {
    ArrayList<Integer> numbers = new ArrayList<Integer>();
    numbers.add(12);
    numbers.add(8);
    numbers.add(2);
    numbers.add(23);
    Iterator<Integer> it = numbers.iterator();
    while(it.hasNext()) {
      Integer i = it.next();
      if(i < 10) {
        it.remove();
      }
    }
    System.out.println(numbers);
  }
}
```

- wrapper class: chuyển kiểu dữ liệu nguên thuỷ về dạng object
![](https://i.imgur.com/OZo79S8.png)

```java
ArrayList<Integer> myNumbers = new ArrayList<Integer>();
```
wrapper object: 
```java
 Integer myInt = 5;
```
Lấy dữ liệu liên quan đến wrapper object sử dụng các method sau:
``intValue()`, `byteValue()`, `shortValue()`, `longValue()`, `floatValue()`, `doubleValue()`, `charValue()`, `booleanValue()`.`

```java
public class Main {
  public static void main(String[] args) {
    Integer myInt = 5;
    Double myDouble = 5.99;
    Character myChar = 'A';
    System.out.println(myInt.intValue());
    System.out.println(myDouble.doubleValue());
    System.out.println(myChar.charValue());
  }
}
```

Ngoài ra còn có `toString()` dùng để chuyển thành string
```java
public class Main {
  public static void main(String[] args) {
    Integer myInt = 100;
    String myString = myInt.toString();
    System.out.println(myString.length()); // trả về 3
  }
}
```

- Cấu trúc try-catch 
```java
try {
  //  Block of code to try
}
catch(Exception e) {
  //  Block of code to handle errors
}
```
```java
public class Main {
  public static void main(String[ ] args) {
    try {
      int[] myNumbers = {1, 2, 3};
      System.out.println(myNumbers[10]);
    } catch (Exception e) {
      System.out.println("Something went wrong.");
    }
  }
}
```

- Finally thực thi code sau try-catch:
```java
public class Main {
  public static void main(String[] args) {
    try {
      int[] myNumbers = {1, 2, 3};
      System.out.println(myNumbers[10]);
    } catch (Exception e) {
      System.out.println("Something went wrong.");
    } finally {
      System.out.println("The 'try catch' is finished.");
    }
  }
}
```
-> Something went wrong.  
The 'try catch' is finished.

- Throw để tạo 1 custom error
- Các exception type : `ArithmeticException`, `FileNotFoundException`, `ArrayIndexOutOfBoundsException`, `SecurityException`

- Re-ex: 
Package: java.util.regex
Class included: Pattern , Matcher, PatternSyntaxException
```java
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class Main {
  public static void main(String[] args) {
    Pattern pattern = Pattern.compile("w3schools", Pattern.CASE_INSENSITIVE); 
    // Case_insensitive: bất kể lowercase và uppercase
    //complle() tạo 1 patterm có tên "w3schools" cho regex
    Matcher matcher = pattern.matcher("Visit W3Schools!");
    //.macher() trả về object đầu tiên match thông tin
    boolean matchFound = matcher.find();
    // .find() trả về true nếu có, false nếu ko
    if(matchFound) {
      System.out.println("Match found");
    } else {
      System.out.println("Match not found");
    }
  }
}
// Outputs Match found
```

* thread: https://topdev.vn/blog/lap-trinh-da-luong-trong-java-java-multi-threading/
Tạo luồng bằng cách extend từ lớp Thread: extend từ class Thread, override phương thức run() từ Thread. Tạo tối tượng , và start. Chú ý start là chuyenr luồn từ new sang runnable
![[Pasted image 20230216160242.png]]
Tạo luồng bằng cách implement từ Interface Runnable: ko cần tạo class mới như cách trên, chỉ cần thực thi từ class Runnable, và còn lại tương tự như cách trên
![[Pasted image 20230216160309.png]]
--------------------
Phân tích kết quả

![[Pasted image 20230216160016.png]]
Sẽ chạy theo cách: ưu tiên chạy xong hết các câu lệnh trong luồng chính (luồng main)  sau đó mới chạy song hành 2 luồng 1 và 2
* lamda expression:
````java
(parameter1, parameter2) -> { code block }
````
```java
import java.util.ArrayList;

public class Main {
  public static void main(String[] args) {
    ArrayList<Integer> numbers = new ArrayList<Integer>();
    numbers.add(5);
    numbers.add(9);
    numbers.add(8);
    numbers.add(1);
    numbers.forEach( (n) -> { System.out.println(n); } );
  }
}
```
```java
import java.util.ArrayList;
import java.util.function.Consumer;

public class Main {
  public static void main(String[] args) {
    ArrayList<Integer> numbers = new ArrayList<Integer>();
    numbers.add(5);
    numbers.add(9);
    numbers.add(8);
    numbers.add(1);
    Consumer<Integer> method = (n) -> { System.out.println(n); };
    numbers.forEach( method );
  // Consumer chứa lambda expression
  }
}
```

* Tạo file:
```java
import java.io.File;  // Import the File class
import java.io.IOException;  // Import the IOException class to handle errors

public class CreateFile {
  public static void main(String[] args) {
    try {
      File myObj = new File("filename.txt"); // chỉ định
      if (myObj.createNewFile()) { //true nếu tạo ok, false nếu tạo ko ok (existed)
        System.out.println("File created: " + myObj.getName());
      } else {
        System.out.println("File already exists.");
      }
    } catch (IOException e) {
      System.out.println("An error occurred.");
      e.printStackTrace();
    }
  }
}
```

chỉ định đường dẫn: 
```java
File myObj = new File("C:\\Users\\MyName\\filename.txt");
```

- ghi file:
```java
import java.io.FileWriter;   // Import the FileWriter class
import java.io.IOException;  // Import the IOException class to handle errors

public class WriteToFile {
  public static void main(String[] args) {
    try {
      FileWriter myWriter = new FileWriter("filename.txt");
      myWriter.write("Files in Java might be tricky, but it is fun enough!");
      myWriter.close();
      System.out.println("Successfully wrote to the file.");
    } catch (IOException e) {
      System.out.println("An error occurred.");
      e.printStackTrace();
    }
  }
}
```

- đọc file:
```java
import java.io.File;  // Import the File class
import java.io.FileNotFoundException;  // Import this class to handle errors
import java.util.Scanner; // Import the Scanner class to read text files

public class ReadFile {
  public static void main(String[] args) {
    try {
      File myObj = new File("filename.txt");
      Scanner myReader = new Scanner(myObj);
      while (myReader.hasNextLine()) {
        String data = myReader.nextLine();
        System.out.println(data);
      }
      myReader.close();
    } catch (FileNotFoundException e) {
      System.out.println("An error occurred.");
      e.printStackTrace();
    }
  }
}
```

- lấy thông tin file:
```java
import java.io.File;  // Import the File class

public class GetFileInfo {   public static void main(String[] args) {
    File myObj = new File("filename.txt");
    if (myObj.exists()) {
      System.out.println("File name: " + myObj.getName());
      System.out.println("Absolute path: " + myObj.getAbsolutePath());
      System.out.println("Writeable: " + myObj.canWrite());
      System.out.println("Readable " + myObj.canRead());
      System.out.println("File size in bytes " + myObj.length());
    } else {
      System.out.println("The file does not exist.");
    }
  }
}
```

- xóa file:
```java
import java.io.File;  // Import the File class

public class DeleteFile {
  public static void main(String[] args) { 
    File myObj = new File("filename.txt"); 
    if (myObj.delete()) { 
      System.out.println("Deleted the file: " + myObj.getName());
    } else {
      System.out.println("Failed to delete the file.");
    } 
  } 
}
```
chỉ định đường dẫn folder sẽ xóa folder:
```java
 File myObj = new File("C:\\Users\\MyName\\Test"); 
```
--------------------------------------
# Spring boot
https://loda.me/courses/spring-boot
Lưu ý khái niệm tight-coupling và loosed-coupling:
tight-coupling: liên kết ràng buộc
```java

public interface SortAlgorithm {
    /**
     * Sắp xếp mảng đầu vào
     * @param array
     */
    public void sort(int array[]);
}

public class BubbleSortAlgorithm implements SortAlgorithm{

    @Override
    public void sort(int[] array) {
        // TODO: Add your logic here
        System.out.println("Đã sắp xếp bằng thuật toán sx nổi bọt");
    }
}


public class VeryComplexService {
    private SortAlgorithm sortAlgorithm;
    public VeryComplexService(){
        sortAlgorithm = new BubbleSortAlgorithm();
    }

    public void complexBusiness(int array[]){
        sortAlgorithm.sort(array);
        // TODO: more logic here
    }
}

```

loosely-coupling (liên kết không ràng buộc) : lớp SortAlgorithm được sử dụng làm interface, các lớp con Bubble và quick chỉ cần implement nó. Tạo 1 lớp VeryComplex để thực thi 2 lớp con đó
```java
public interface SortAlgorithm {
    /**
     * Sắp xếp mảng đầu vào
     * @param array
     */
    public void sort(int array[]);
}

public class BubbleSortAlgorithm implements SortAlgorithm{

    @Override
    public void sort(int[] array) {
        // TODO: Add your logic here
        System.out.println("Đã sắp xếp bằng thuật toán sx nổi bọt");
    }
}

public class QuicksortAlgorithm implements SortAlgorithm {
    @Override
    public void sort(int[] array) {
        // TODO: Add your logic here
        System.out.println("Đã sắp xếp bằng thuật sx nhanh");

    }
}

public class VeryComplexService {
    private SortAlgorithm sortAlgorithm;
    public VeryComplexService(SortAlgorithm sortAlgorithm){
        this.sortAlgorithm = sortAlgorithm;
    }

    public void complexBusiness(int array[]){
        sortAlgorithm.sort(array);
        // TODO: more logic here
    }
}

public static void main(String[] args) {
    SortAlgorithm bubbleSortAlgorithm = new BubbleSortAlgorithm();
    SortAlgorithm quickSortAlgorithm = new QuicksortAlgorithm();
    VeryComplexService business1 = new VeryComplexService(bubbleSortAlgorithm);
    VeryComplexService business2 = new VeryComplexService(quickSortAlgorithm);
}
```

Giảm sự phụ thuộc, tăng khả năng tùy biến, linh hoạt code:
```java
public class Girl{
    private Outfit outfit;
    public Girl(){
      outfit = new Bikini();
    }
}
```
--> thay bikini bằng anything
```java
public class Girl {
	private Outfit outfit;
	public Girl(Outfit anything){
		this.outfit = anything}
}
```
Tức là inject cái outfit vào girl

```



một trong những nhiệm vụ chính của **Spring** là tạo ra một cái _**Container**_ chứa các _**Dependency**_ cho chúng ta.

`SpringApplication.run(App.class, args)` chính là câu lệnh để tạo ra _**container**_. Sau đó nó tìm toàn bộ các _**dependency**_ trong project của bạn và đưa vào đó.

```java
@SpringBootApplication
public class App {
    public static void main(String[] args) {
        // ApplicationContext chứa toàn bộ dependency trong project.
        ApplicationContext context = SpringApplication.run(App.class, args);
    }
}
```
`@Component` là một [Annotation](https://loda.me/articles/huong-dan-tu-tao-mot-annotations) (chú thích) đánh dấu trên các `Class` để giúp **Spring** biết nó là một `Bean`.
`
![[Pasted image 20221108101142.png]]
```java
@SpringBootApplication
public class App {
    public static void main(String[] args) {
        // ApplicationContext chính là container, chứa toàn bộ các Bean
        ApplicationContext context = SpringApplication.run(App.class, args);

        // Khi chạy xong, lúc này context sẽ chứa các Bean có đánh
        // dấu @Component.

        // Lấy Bean ra bằng cách
        Outfit outfit = context.getBean(Outfit.class);

        // In ra để xem thử nó là gì
        System.out.println("Instance: " + outfit);
        // xài hàm wear()
        outfit.wear();
    }
}
```

Các bước:
Chạy ứng dụng Spring Application
-> Dò tìm Class cùng cấp với App
-> Phát hiện các Component và xem nó là 1 bean
-> Đẩy (inject) vào container là Application context
Có 2 định nghĩa: Application context là 1` container,` trong khi đó dependency là các` Bean`

Tất cả những `Bean` được quản lý trong `ApplicationContext` đều chỉ được tạo ra **một lần duy nhất** và khi có `Class` yêu cầu `@Autowired` thì nó sẽ lấy đối tượng có sẵn trong `ApplicationContext` để _inject_ vào.

Trong trường hợp bạn muốn mỗi lần sử dụng là một instance hoàn toàn mới. Thì hãy đánh dấu `@Component` đó bằng `@Scope("prototype")`

```java
@Component
@Scope("prototype")
public class Bikini implements Outfit {
    @Override
    public void wear() {
        System.out.println("Mặc bikini");
    }
}
```

@Primary` và `@Qualifier` xử lí vấn đế nếu có nhiều component thì dùng component nào 
Ví dụ:
Đối với primary
```java
public interface Outfit {
    public void wear();
}

/*
 Đánh dấu class bằng @Component
 Class này sẽ được Spring Boot hiểu là một Bean (hoặc dependency)
 Và sẽ được Spring Boot quản lý
  */
@Component
public class Bikini implements Outfit {
    @Override
    public void wear() {
        System.out.println("Mặc bikini");
    }
}

@Primary
@Component
public class Naked implements Outfit {
    @Override
    public void wear() {
        System.out.println("Đang không mặc gì");
    }
}

@Component 
public class Girl { 
@Autowired 
Outfit outfit; 
// GET // SET 
}
```
Đối với qualifiers
```java
```java
@Component("bikini")
public class Bikini implements Outfit {
    @Override
    public void wear() {
        System.out.println("Mặc bikini");
    }
}

@Component("naked")
public class Naked implements Outfit {
    @Override
    public void wear() {
        System.out.println("Đang không mặc gì");
    }
}

@Component
public class Girl {

    Outfit outfit;

    // Đánh dấu để Spring inject một đối tượng Outfit vào đây
    public Girl(@Qualifier("naked") Outfit outfit) {
        // Spring sẽ inject outfit thông qua Constructor đầu tiên
        // Ngoài ra, nó sẽ tìm Bean có @Qualifier("naked") trong context để ịnject
        this.outfit = outfit;
    }

    // GET
    // SET
```

@postContruct:`@PostConstruct` được đánh dấu trên một method duy nhất bên trong `Bean`. `IoC Container` hoặc `ApplicationContext` sẽ gọi hàm này **sau khi** một `Bean` được tạo ra và quản lý.

### **@PreDestroy**

`@PreDestroy` được đánh dấu trên một method duy nhất bên trong `Bean`. `IoC Container` hoặc `ApplicationContext` sẽ gọi hàm này **trước khi** một `Bean` bị xóa hoặc không được quản lý nữa.
![[Pasted image 20221106230004.png]]

```makefile
> Trước khi IoC Container được khởi tạo
> Trước khi IoC Container được khởi tạo
	>> Đối tượng Girl sau khi khởi tạo xong sẽ chạy hàm này
> Sau khi IoC Container được khởi tạo
> Trước khi IoC Container destroy Girl
	>> Đối tượng Girl trước khi bị destroy thì chạy hàm này
> Sau khi IoC Container destroy Girl
```
-----

```java
public class Girl {
    private String name;

    public Girl(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    @Override
    public String toString() {
        return "Girl(" + this.name + ")";
    }
}
```

Tạo ra một interface `GirlRepository` để giao tiếp với DB.

```java
public interface GirlRepository {
    /**
     * Tìm kiếm một cô gái trong database theo tên
     * @param name
     * @return
     */
    Girl getGirlByName(String name);
}
```

Kế thừa `GirlRepository` và đánh dấu nó là `@Repository`

```java
@Repository
public class GirlRepositoryImpl implements GirlRepository {

    @Override
    public Girl getGirlByName(String name) {
        // Ở đây tôi ví dụ là database đã trả về
        // một cô gái với tên đúng như tham số

        // Còn thực tế phải query trong csđl nhé.
        return new Girl(name);
    }
}
```

Tạo ra một class `GỉrlService` để giải quyết các logic nghiệp vụ. Lớp `GirlService` sẽ giao tiếp với DB thông qua `GirlRepository`.

```java
import org.apache.commons.lang3.RandomStringUtils;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Service;

@Service
public class GirlService {
    @Autowired
    private GirlRepository girlRepository;

    public Girl getRandomGirl(){
        // Random 1 cái tên độ dài 10
        String name = randomGirlName(10);

        // Gọi xuông tầng repository để query lấy một cô gái tên là "name" trong database
        return girlRepository.getGirlByName(name);
    }

    public String randomGirlName(int length) {
        // Random một string có độ dài quy định
        // Sử dụng thư viện Apache Common Lang
        return RandomStringUtils.randomAlphanumeric(length).toLowerCase();
    }
}
```

Chạy chương trình:

```java
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.context.ApplicationContext;

@SpringBootApplication
public class App {

    public static void main(String[] args) {
        ApplicationContext context = SpringApplication.run(App.class, args);

        // Lấy ra bean GirlService
        GirlService girlService = context.getBean(GirlService.class);
        // Lấu ra random một cô gái từ tầng service
        Girl girl = girlService.getRandomGirl();
        // In ra màn hình
        System.out.println(girl);

    }
}
```

Output: trả về dưới dạng toString của 1 object

```
Girl(ulmvchvgkf)
```

--------
![[Pasted image 20230113134456.png]]
về mặt bản chất , cả 3 anotation này đánh dấu biết class đó là bean, nhưng mục đích thì khác nhau

`@ComponentScan("thư mục cùng cấp với app aplication")`


![[Pasted image 20221108100234.png]]

Ví dụ: scan chỉ định
```java
@ComponentScan("me.loda.spring.componentscan.others")
@SpringBootApplication
public class App {
    public static void main(String[] args) {
        ApplicationContext context = SpringApplication.run(App.class, args);
```

```java
// Hoặc 
@SpringBootApplication(scanBasePackages = "me.loda.spring.componentscan.others") 
```

Multiple package scan:
```java
@ComponentScan({"me.loda.spring.componentscan.others2","me.loda.spring.componentscan.others"})
```
hoặc
```java
@SpringBootApplication(scanBasePackages = {"me.loda.spring.componentscan.others", "me.loda.spring.componentscan.others2"})
```

### **@Configuration và @Bean**

@Configuration đánh dấu trên CLASS để spring biết đây là nơi để ĐỊNH NGHĨA các bean
@Bean đánh dấu trên METHOD để spring biết đây là các BEAN  và đưa BEAN này vào context (tức là Application Context)
`@Bean` sẽ nằm trong các class có đánh dấu `@Configuration`.

có thể thay @component thay cho bộ đôi @configuration và @bean, tuy nhiên nếu dùng bộ đôi này thì sẽ dễ config những chương trình phức tạp


```java
@Bean("mysqlConnector")
    DatabaseConnector mysqlConfigure() {
        DatabaseConnector mySqlConnector = new MySqlConnector();
        mySqlConnector.setUrl("jdbc:mysql://host1:33060/loda");
        // Set username, password, format, v.v...
        return mySqlConnector;
    }

    @Bean("mongodbConnector")
    DatabaseConnector mongodbConfigure() {
        DatabaseConnector mongoDbConnector = new MongoDbConnector();
        mongoDbConnector.setUrl("mongodb://mongodb0.example.com:27017/loda");
        // Set username, password, format, v.v...
        return mongoDbConnector;
    }

    @Bean("postgresqlConnector")
    DatabaseConnector postgresqlConfigure(){
        DatabaseConnector postgreSqlConnector = new PostgreSqlConnector();
        postgreSqlConnector.setUrl("postgresql://localhost/loda");
        // Set username, password, format, v.v...
        return postgreSqlConnector;
    }
```
Nếu method được đánh dấu bởi `@Bean` có tham số truyền vào, thì **Spring Boot** sẽ tự inject các Bean đã có trong `Context` vào làm tham số.
->
```java

        DatabaseConnector mysql = (DatabaseConnector) context.getBean("mysqlConnector");
        mysql.connect();

        DatabaseConnector mongodb = (DatabaseConnector) context.getBean("mongodbConnector");
        mongodb.connect();

        DatabaseConnector postgresql = (DatabaseConnector) context.getBean("postgresqlConnector");
        postgresql.connect();
```
---------

super: thừa hưởng method của cha
cấu trúc.: super.[tên method của class cha]
```
class Animal { // Superclass (parent)
  public void animalSound() {
    System.out.println("The animal makes a sound");
  }
}

class Dog extends Animal { // Subclass (child)
  public void animalSound() {
    super.animalSound(); // Call the superclass method
    System.out.println("The dog says: bow wow");
  }
}

public class Main {
   public static void main(String[] args) {
      Animal myDog = new Dog(); // Create a Dog object
      myDog.animalSound(); // Call the method on the Dog object
   }
}

```

**Thymeleaf** là một Java Template Engine. Có nhiệm vụ xử lý và generate ra các file HTML, XML:
cú pháp: bắt đầu bằng chữ 'th'. Ví dụ:
![[Pasted image 20230217105428.png]]