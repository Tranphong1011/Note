https://student.deepracer.com/home
1 Investigation of thermoelectric behaviour and for identifying new candidate thermoelectric materials

jupiter shortcut:
-   `Shift + Enter` run the current cell, select below
-   `Ctrl + Enter` run selected cells
-   `Alt + Enter` run the current cell, insert below
-   `Ctrl + S` save and checkpoint
**-While in command mode (press `Esc` to activate):**

-   `Enter` take you into edit mode
-   `H` show all shortcuts
-   `Up` select cell above
-   `Down` select cell below
-   `Shift + Up` extend selected cells above
-   `Shift + Down` extend selected cells below
-   `A` insert cell above
-   `B` insert cell below
-   `X` cut selected cells
-   `C` copy selected cells
-   `V` paste cells below
-   `Shift + V` paste cells above
-   `D, D (press the key twice)` delete selected cells
-   `Z` undo cell deletion
-   `S` Save and Checkpoint
-   `Y` change the cell type to _Code_
-   `M` change the cell type to _Markdown_
-   `P` open the command palette.

**While in edit mode (press`Enter` to activate)**

-   `Esc` take you into command mode
-   `Tab` code completion or indent
-   `Shift + Tab` tooltip
-   `Ctrl + ]` indent
-   `Ctrl + [` dedent
-   `Ctrl + A` select all
-   `Ctrl + Z` undo
-   `Ctrl + Shift + Z` or `Ctrl + Y` redo
-   `Ctrl + Home` go to cell start
-   `Ctrl + End` go to cell end
-   `Ctrl + Left` go one word left
-   `Ctrl + Right` go one word right
-   `Ctrl + Shift + P` open the command palette
-   `Down` move cursor down
-   `Up` move cursor up

Python - OOP
Use the __init__() function to assign values to object properties, or other operations that are necessary to do when the object is being created:
```python
class Person:  
  def __init__(self, name, age):  
    self.name = name  
    self.age = age  
  
p1 = Person("John", 36)  
  
print(p1.name)  
print(p1.age)
```
-----------The `__init__()` function is called automatically every time the class is being used to create a new object.---------------

The __str__() function controls what should be returned when the class object is represented as a string.
```python
class Person:  
  def __init__(self, name, age):  
    self.name = name  
    self.age = age  
  
  def __str__(self):  
    return f"{self.name}({self.age})"  # f"" : nhúng biểu thức vào
  
p1 = Person("John", 36)  
  
print(p1)
#John(36)
```
Thường sẽ trả về <__main__.Person object at 0x15039e602100>. Nhưng nếu định nghĩa __str__ sẽ trả về cái mà class đại diện dưới dạng string

Từ khóa self: có thể thay thế bằng từ khác cũng đưuọc, miễn là param đầu tiên cảu bất kì function nào của class. Vì self - từ khóa khác : Đại diện cho instance hiện tại của clas:
```python
class Person:  
  def __init__(mysillyobject, name, age):  
    mysillyobject.name = name  
    mysillyobject.age = age  
  
  def myfunc(abc):  
    print("Hello my name is " + abc.name)  
  
p1 = Person("John", 36)  
p1.myfunc()
```

Có thể modify
```
p1.age = 40

```
Có thể xóa properties:
```
del p1.age
```

Có thể xóa objects:
```
del p1
```

pass 1 class:  Use the `pass` keyword when you do not want to add any other properties or methods to the class.
```
class Person:  
  pass
```

Inheritance:
parent class: class đưuọc inherited , còn được gọi là base class
child class: gọi là derived class
----> Cách tạo child class: truyền tên class cha vào param của class con:
```python
class Student(Person):  
  pass
```
Ví dụ: 
```python
class Person:
  def __init__(self, fname, lname):
    self.firstname = fname
    self.lastname = lname

  def printname(self):
    print(self.firstname, self.lastname)

class Student(Person):
  pass

x = Student("Mike", "Olsen")
x.printname()

```
----> Do vậy Student class có cùng properites và methods so với class cha là Person

Có thể thêm `__init__()` vào class con, nhưng lúc đó sẽ không còn inherit hàm `__init__()`  của class cha
-> overrides lại hàm `__init__()`  của class cha
-> Nếu muốn dữ lại thì dùng như sau: gọi lại function innit của class cha
```python
class Student(Person):  
  def __init__(self, fname, lname):  
    Person.__init__(self, fname, lname)
```

Hàm super() trong class con : inherit all the methods and properties from its parent:
```python
class Student(Person):  
  def __init__(self, fname, lname):  
    super().__init__(fname, lname)
```

Bổ sung properties ` self.graduationyear = 2019` vào class con
```python
class Person:
  def __init__(self, fname, lname):
    self.firstname = fname
    self.lastname = lname

  def printname(self):
    print(self.firstname, self.lastname)

class Student(Person):
  def __init__(self, fname, lname):
    super().__init__(fname, lname)
    self.graduationyear = 2019

x = Student("Mike", "Olsen")
print(x.graduationyear)

```
Tuy nhiên, ta có thể add "year" param: 
```python
class Person:
  def __init__(self, fname, lname):
    self.firstname = fname
    self.lastname = lname

  def printname(self):
    print(self.firstname, self.lastname)

class Student(Person):
  def __init__(self, fname, lname, year):
    super().__init__(fname, lname)
    self.graduationyear = year

x = Student("Mike", "Olsen", 2019)
print(x.graduationyear)

```

Thêm method:
```python
class Person:
  def __init__(self, fname, lname):
    self.firstname = fname
    self.lastname = lname

  def printname(self):
    print(self.firstname, self.lastname)

class Student(Person):
  def __init__(self, fname, lname, year):
    super().__init__(fname, lname)
    self.graduationyear = year

  def welcome(self):
    print("Welcome", self.firstname, self.lastname, "to the class of", self.graduationyear)

x = Student("Mike", "Olsen", 2019)
x.welcome()

```

other: Tham chiếu đến đối tượng khác
Ví dụ: 
```python
class Rectangle:
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height

    def compare_area(self, other):
        if self.area() > other.area():
            return "This rectangle has a larger area."
        elif self.area() < other.area():
            return "This rectangle has a smaller area."
        else:
            return "This rectangle has the same area."

rectangle1 = Rectangle(5, 10)
rectangle2 = Rectangle(8, 6)

print(rectangle1.compare_area(rectangle2))  # In ra: This rectangle has a smaller area.

```

-------------
Nhập thư viện
import cv2
from google.colab.patches import cv2_imshow : chỉ có thể dùng được trên google, nếu ở jupyter note thì sử dụng cv2.imshow():
Ví dụ
```python
image = cv2.imread('example/image.png')  
cv2.imshow("test", image)
```

Định dạng mặc định IMREAD_COLOR thì ảnh đọc lên sẽ có ma trận (Height, Width, Channel) với Channel là 3 tương ứng với kênh màu Blue , Green và Red

Kiểm tra kích thước ma trận:
```python
img.shape
# (512,512,3) : với 3 là số kênh màu
```

Chuyển ảnh thành màu xám:
```python
gray_img = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
```

Lưu ảnh vào thư mục hiện hành:
```python
cv2.imwrite("gray_image.jpg", gray_img)
```
trả về True là thành công