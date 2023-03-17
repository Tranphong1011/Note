sematic versioning:
Major.Minor.Patch
Nếu ^1.1.1 thì Major giữ nguyên

Chương trình cơ bản: 
```csharp
using System;

namespace HelloWorld
{
  class Program
  {
    static void Main(string[] args) // is a method
    {
      Console.WriteLine("Hello World!");    
    }
  }
}
```

nếu ko khai báo using System thì phải System.Console.WriteLine()

Các file phải có đuôi .cs

Console.WriteLine thì xuống hàng
Console.Write thì ko

Comment: dùng //, comment nhiều: dùng /**/

Các kiểu dữ liệu:
```csharp
int myNum = 5;
double myDoubleNum = 5.99D;
char myLetter = 'D';
bool myBool = true;
float myNum = 5.75F;
string myText = "Hello";
```

Casting: 
```csharp
double myDouble = 9.78;
int myInt = (int) myDouble;  
-> 9
```
hoặc
```csharp
int myInt = 10;
double myDouble = 5.25;
bool myBool = true;

Console.WriteLine(Convert.ToString(myInt));    // convert int to string
Console.WriteLine(Convert.ToDouble(myInt));    // convert int to double
Console.WriteLine(Convert.ToInt32(myDouble));  // convert double to int
Console.WriteLine(Convert.ToString(myBool));   // convert bool to string
```

Nhập dữ liệu:
```csharp
string userName = Console.ReadLine();
```
Nhớ: Dữ liệu nhập vào luôn là string, do đó:
```csharp
Console.WriteLine("Enter your age:");
int age = Convert.ToInt32(Console.ReadLine());
Console.WriteLine("Your age is: " + age);
```

Các hàm 

```csharp
Math.Max(5,10)
Math.Min(5, 10);
```
```csharp
Math.Sqrt(64);
```
```csharp
Math.Abs(-4.7);
```
```csharp
Math.Round(9.99);
```

Thao tác chuỗi : 
txt.Lenght ,txt.ToUpper(), txt.ToLower()
string.Concat(a,b)
myString[1], myString.IndexOf("e")
substring:
```csharp
// Full name
string name = "John Doe";

// Location of the letter D
int charPos = name.IndexOf("D");

// Get last name
string lastName = name.Substring(charPos);

// Print the result
Console.WriteLine(lastName);->Doe
```
Interpolation: thay thế biến
$"{a}"

esscape character: ![[Pasted image 20230313172622.png]]

Cấu trúc if-else:
```csharp
if (condition1)
{
  // block of code to be executed if condition1 is True
} 
else if (condition2) 
{
  // block of code to be executed if the condition1 is false and condition2 is True
} 
else
{
  // block of code to be executed if the condition1 is false and condition2 is False
}
```

ternary:
```csharp
variable = (condition) ? expressionTrue :  expressionFalse;
```

switch case:
```csharp
switch(expression) 
{
  case x:
    // code block
    break;
  case y:
    // code block
    break;
  default:
    // code block
    break;
}
```

while loop
```csharp
while (condition) 
{
  // code block to be executed
}
```

do while
```csharp
do 
{
  // code block to be executed
}
while (condition);
```

for loop:
```csharp
for (int i = 0; i < 5; i++) 
{
  Console.WriteLine(i);
}
```

foreach loop:
```csharp
string[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
foreach (string i in cars) 
{
  Console.WriteLine(i);
}
```

Array:
```csharp
string[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
```
```csharp
int[] myNum = {10, 20, 30, 40};
```
-Access:
```csharp
cars[0];
```
-Change:
```csharp
cars[0] = "Opel";
```
-Length:
```csharp
cars.Length
```
Các cách tạo mảng:
```csharp
// Create an array of four elements, and add values later
string[] cars = new string[4];

// Create an array of four elements and add values right away 
string[] cars = new string[4] {"Volvo", "BMW", "Ford", "Mazda"};

// Create an array of four elements without specifying the size 
string[] cars = new string[] {"Volvo", "BMW", "Ford", "Mazda"};

// Create an array of four elements, omitting the new keyword, and without specifying the size
string[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
```

Chú ý:
![[Pasted image 20230316074601.png]]
-Sort:
```csharp
Array.Sort(cars);
```
-Sử dụng Min max sum thì phải sử dụng thư viện System.Ling
```csharp
using System.Linq;
.
.
int[] myNumbers = {5, 1, 8, 9};
myNumbers.Max()
```
-Mảng 2 chiều:
```csharp
int[,] numbers = { {1, 4, 2}, {3, 6, 8} };
```
-Mảng 3 chiều :int[,,]
-Method:
```csharp
class Program
{
  static void MyMethod() 
  {
    // code to be executed
  }
}
```
-Method truyền 2 tham số:
```csharp
static void MyMethod(string fname, int age) 
{
  Console.WriteLine(fname + " is " + age);
}

static void Main(string[] args)
{
  MyMethod("Liam", 5);
  MyMethod("Jenny", 8);
  MyMethod("Anja", 31);
}
```
-Tham số mặc định
```csharp
static void MyMethod(string country = "Norway") 
{
  Console.WriteLine(country);
}

static void Main(string[] args)
{
  MyMethod("Sweden");
  MyMethod("India");
  MyMethod();
  MyMethod("USA");
}

// Sweden
// India
// Norway
// USA
```
-Method overloading:
```csharp
int MyMethod(int x)
float MyMethod(float x)
double MyMethod(double x, double y)
```
---------
oop
class-object
```csharp
class Car 
{
  string color = "red";

  static void Main(string[] args)
  {
    Car myObj = new Car();
    Console.WriteLine(myObj.color);
  }
}
```
Chú ý: a `static` method can be accessed without creating an object of the class, while `public` methods can only be accessed by objects.
Hàm constructor:
```csharp
// Create a Car class
class Car
{
  public string model;  // Create a field

  // Create a class constructor for the Car class
  public Car()
  {
    model = "Mustang"; // Set the initial value for model
  }

  static void Main(string[] args)
  {
    Car Ford = new Car();  // Create an object of the Car Class (this will call the constructor)
    Console.WriteLine(Ford.model);  // Print the value of model
  }
}

// Outputs "Mustang"
```
Access Modifiers: 
![[Pasted image 20230316113038.png]]
The meaning of **Encapsulation**, is to make sure that "sensitive" data is hidden from users. To achieve this, you must:

-   declare fields/variables as `private`
-   provide `public` `get` and `set` methods, through **properties**, to access and update the value of a `private` field
```csharp
class Person
{
  private string name; // field

  public string Name   // --------------->property là sự kết hợp valuable + method
  {
    get { return name; }   // get method
    set { name = value; }  // set method
  }
}
```
Giải thích:

The `get` method returns the value of the variable `name`.

The `set` method assigns a `value` to the `name` variable. The `value` keyword represents the value we assign to the property.
```csharp
class Person
{
  private string name; // field
  public string Name   // property
  {
    get { return name; }
    set { name = value; }
  }
}

class Program
{
  static void Main(string[] args)
  {
    Person myObj = new Person();
    myObj.Name = "Liam"; // set name
    Console.WriteLine(myObj.Name); // get name
  }
}
```
so sánh với Java:
```java
public class Person {
   private String name;

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
    Person myObj = new Person();
    myObj.setName("John"); // Set the value of the name variable to "John"
    System.out.println(myObj.getName());
  }
}
```
Ghi ngắn gọn get set cho C#;
```csharp
class Person
{
  public string Name  // property
  { get; set; }
}

class Program
{
  static void Main(string[] args)
  {
    Person myObj = new Person();
    myObj.Name = "Liam";
    Console.WriteLine(myObj.Name);
  }
}
```

Inheritance: Dùng dấu : để kết thừa từ cha sang con
```csharp
class Vehicle  // base class (parent) 
{
  public string brand = "Ford";  // Vehicle field
  public void honk()             // Vehicle method 
  {                    
    Console.WriteLine("Tuut, tuut!");
  }
}

class Car : Vehicle  // derived class (child)
{
  public string modelName = "Mustang";  // Car field
}

class Program
{
  static void Main(string[] args)
  {
    // Create a myCar object
    Car myCar = new Car();

    // Call the honk() method (From the Vehicle class) on the myCar object
    myCar.honk();

    // Display the value of the brand field (from the Vehicle class) and the value of the modelName from the Car class
    Console.WriteLine(myCar.brand + " " + myCar.modelName);
  }
}
```
---> Không muốn kế thừa, dùng sealed:
![[Pasted image 20230316115941.png]]

Polymorphism:
Sử dụng virtual cho method ở class cha, sử dụng overrice cho method class con:
```csharp
class Animal  // Base class (parent) 
{
  public virtual void animalSound() 
  {
    Console.WriteLine("The animal makes a sound");
  }
}

class Pig : Animal  // Derived class (child) 
{
  public override void animalSound() 
  {
    Console.WriteLine("The pig says: wee wee");
  }
}

class Dog : Animal  // Derived class (child) 
{
  public override void animalSound() 
  {
    Console.WriteLine("The dog says: bow wow");
  }
}

class Program 
{
  static void Main(string[] args) 
  {
    Animal myAnimal = new Animal();  // Create a Animal object
    Animal myPig = new Pig();  // Create a Pig object
    Animal myDog = new Dog();  // Create a Dog object

    myAnimal.animalSound();
    myPig.animalSound();
    myDog.animalSound();
  }
}
```

Abstract 
-Abstract class: ko được dùng để tạo object, chỉ được inherit từ class khác
-Abstract method: chỉ được sử dụng trong abstract calss, không có body , phần body sẽ được xử lý trong hàm khác (inherited) 
-Sử dụng dấu : cho class, override cho method
```csharp
// Abstract class
abstract class Animal
{
  // Abstract method (does not have a body)
  public abstract void animalSound();
  // Regular method
  public void sleep()
  {
    Console.WriteLine("Zzz");
  }
}

// Derived class (inherit from Animal)
class Pig : Animal
{
  public override void animalSound()
  {
    // The body of animalSound() is provided here
    Console.WriteLine("The pig says: wee wee");
  }
}

class Program
{
  static void Main(string[] args)
  {
    Pig myPig = new Pig(); // Create a Pig object
    myPig.animalSound();  // Call the abstract method
    myPig.sleep();  // Call the regular method
  }
}
```

Interface: cũng như Abstract class
-không tạo object, không chứa body, body được thực thi chỗ khác
-1 khi overrice calss, thì phải overide hết toàn bộ method
-Không chưa constructor
-Tên của Interface bắt đầu bằng "I"
-Interface chỉ chứa properties, method, ko chứa fields
-Inherit class dùng ":", inherit method ko cần dùng "override"
```java
// Interface
interface IAnimal 
{
  void animalSound(); // interface method (does not have a body)
}

// Pig "implements" the IAnimal interface
class Pig : IAnimal 
{
  public void animalSound() 
  {
    // The body of animalSound() is provided here
    Console.WriteLine("The pig says: wee wee");
  }
}

class Program 
{
  static void Main(string[] args) 
  {
    Pig myPig = new Pig();  // Create a Pig object
    myPig.animalSound();
  }
}
```
Multi Interface:
```java
interface IFirstInterface 
{
  void myMethod(); // interface method
}

interface ISecondInterface 
{
  void myOtherMethod(); // interface method
}

// Implement multiple interfaces
class DemoClass : IFirstInterface, ISecondInterface 
{
  public void myMethod() 
  {
    Console.WriteLine("Some text..");
  }
  public void myOtherMethod() 
  {
    Console.WriteLine("Some other text...");
  }
}

class Program 
{
  static void Main(string[] args)
  {
    DemoClass myObj = new DemoClass();
    myObj.myMethod();
    myObj.myOtherMethod();
  }
}
```
Enum - bản chất là 1 class
![[Pasted image 20230316123555.png]]
Có thể tạo enum bên trong 1 class

Files 
Nhập 
```csharp
using System.IO

```

Các method của File:
![[Pasted image 20230316123954.png]]
Ví dụ:
```java
using System.IO;  // include the System.IO namespace

string writeText = "Hello World!";  // Create a text string
File.WriteAllText("filename.txt", writeText);  // Create a file and write the content of writeText to it

string readText = File.ReadAllText("filename.txt");  // Read the contents of the file
Console.WriteLine(readText);  // Output the content
```
Exception:
```csharp
try
{
  int[] myNumbers = {1, 2, 3};
  Console.WriteLine(myNumbers[10]);
}
catch (Exception e)
{
  Console.WriteLine("Something went wrong.");
}
finally
{
  Console.WriteLine("The 'try catch' is finished.");
}
```
->Something went wrong.  
The 'try catch' is finished.
Throw: `ArithmeticException`, `FileNotFoundException`, `IndexOutOfRangeException`, `TimeOutException`
Ví dụ:
```csharp
static void checkAge(int age)
{
  if (age < 18)
  {
    throw new ArithmeticException("Access denied - You must be at least 18 years old.");
  }
  else
  {
    Console.WriteLine("Access granted - You are old enough!");
  }
}

static void Main(string[] args)
{
  checkAge(15);
}
```
->System.ArithmeticException: 'Access denied - You must be at least 18 years old.'

--------
Dotnet 
Create a new project: chọn ASP.NET Core web app (Model-View-Controller)
