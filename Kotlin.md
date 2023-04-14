Tạo 1 file kotlin: New ->Kotline Class/File, chọn File
Tạo biến: sử dụng val/var

`The difference between `var` and `val` is that variables declared with the `var` keyword **can be changed/modified**, while `val` variables **cannot**.`

```kotlin
var name = "John"
val birthyear = 1975

println(name)          // Print the value of name
println(birthyear)     // Print the value of birthyear
```

Nếu muốn specify kiểu dữ liệu:
```kotlin
var name: String = "John" // String
val birthyear: Int = 1975 // Int

```
```kotlin
val myNum: Int = 5                // Int
val myDoubleNum: Double = 5.99    // Double
val myLetter: Char = 'D'          // Char
val myBoolean: Boolean = true     // Boolean
val myText: String = "Hello"      // String
```

hoặc:
```kotlin
var name: String
name = "John"
```

Data types are divided into different groups:

-   Numbers : `Byte` (from -128 to 127), `Short` (-32768 to 32767) , `Int` (-2147483648 to 2147483647) and `Long` : Thường dùng Int
-   Characters: `Float` and `Double`. : Thường dùng Float (The precision of `Float` is only six or seven decimal digits, while `Double` variables have a precision of about 15 digits)
-   Booleans
-   Strings
-   Arrays

Chuyển đổi type: `toByte()`, `toShort()`, `toInt()`, `toLong()`, `toFloat()`, `toDouble()` or `toChar()`:
```kotlin
val x: Int = 5
val y: Long = x.toLong()
```

String:
```kotlin
var txt = "Hello World"
var txt1 = "Hello World"
println(txt[0]) // first element (H)
println(txt.length)
println(txt.toUpperCase())
println(txt.compareTo(txt1))  // Outputs 0 (they are equal)
var txt2 = "Please locate where 'locate' occurs!" 
println(txt2.indexOf("locate"))  // Outputs 7
var firstName = "John " 
var lastName = "Doe"
println(firstName.plus(lastName)) //hoặc dùng +
println("My name is $firstName $lastName") // Interpolation
```

Unlike Java, `if..else` can be used as a **statement** or as an **expression** (to assign a value to a variable) in Kotlin
```kotlin
if (condition1) {
  // block of code to be executed if condition1 is true
} else if (condition2) {
  // block of code to be executed if the condition1 is false and condition2 is true
} else {
  // block of code to be executed if the condition1 is false and condition2 is false
}
```
```kotlin
val time = 20
val greeting = if (time < 18) {
  "Good day."
} else {
  "Good evening."
}
```
```kotlin
fun main() {
  val time = 20
  val greeting = if (time < 18) "Good day." else "Good evening." //bỏ dấu {}
  println(greeting)
}
```
```kotlin
val day = 4

val result = when (day) { // Cách sử dụng when tương đương với switch case
  1 -> "Monday"
  2 -> "Tuesday"
  3 -> "Wednesday"
  4 -> "Thursday"
  5 -> "Friday"
  6 -> "Saturday"
  7 -> "Sunday"
  else -> "Invalid day." // giống default
}
println(result)

// Outputs "Thursday" (day 4)
```

Array: 
```kotlin
val cars = arrayOf("Volvo", "BMW", "Ford", "Mazda")
println(cars[0])
cars[0] = "Opel" // thay đổi giá trị
cars.size // kích thước array
if ("Volvo" in cars) // kiểm tra ele có trong array không 
{ println("It exists!") } 
else { println("It does not exist.") }
for (x in cars) { println(x) }
```

Cách sử dụng range:
```kotlin
for (chars in 'a'..'x') {
  println(chars)
}
```
```kotlin
for (nums in 5..15) {
  println(nums)
} 
```

function:
```kotlin
fun myFunction(fname: String) { // có thể có nhiều tham số
  println(fname + " Doe")
} 
```
call function: 
```kotlin
fun main() {
  myFunction("John") // Call myFunction
}
```
Định nghĩa kiểu return của 1 function
```kotlin
fun myFunction(x: Int, y: Int): Int {
  return (x + y)
}

fun main() {
  var result = myFunction(3, 5)
  println(result)
}
```
Shorter syntax:
```kotlin
fun myFunction(x: Int, y: Int) = x + y

fun main() {
  var result = myFunction(3, 5)
  println(result)
}
```

Tạo class
```kotlin
class Car { // tạo class có tên là Car
  var brand = "" // brand, model và year là properties
  var model = ""
  var year = 0
} 
```
Tạo object: 
```kotlin
val c1 = Car()
```
Lấy thuộc tính, gán giá trị
```kotlin
c1.brand = "Ford"
c1.model = "Mustang"
c1.year = 1969
```

Tạo constructor: 
```kotlin
class Car(var brand: String, var model: String, var year: Int)

fun main() {
  val c1 = Car("Ford", "Mustang", 1969)
}
```

Kế thừa class: sử dụng key "open"
```kotlin
// Superclass
open class MyParentClass {
  val x = 5
}

// Subclass
class MyChildClass: MyParentClass() {
  fun myFunction() {
    println(x) // x is now inherited from the superclass
  }
}

// Create an object of MyChildClass and call myFunction
fun main() {
  val myObj = MyChildClass()
  myObj.myFunction()
} 
```