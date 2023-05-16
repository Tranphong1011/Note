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


## Public: Mặc định

## Protected: 

Protected members of a class are accessible from within the class and are also available to its sub-classes. No other environment is permitted access to it. This enables specific resources of the parent class to be inherited by the child class.

Python's convention to make an instance variable **protected** is to add a prefix _ (single underscore) to it. This effectively prevents it from being accessed unless it is from within a sub-class.

```python
class Student:
    _schoolName = 'XYZ School' # protected class attribute
    
    def __init__(self, name, age):
        self._name=name  # protected instance attribute
        self._age=age # protected instance attribute
```

In fact, this doesn't prevent instance variables from accessing or modifying the instance. You can still perform the following operations:

```python
>>> std = Student("Swati", 25)
>>> std._name
'Swati'
>>> std._name = 'Dipa'
>>> std._name
'Dipa'
```

However, you can define a property using [property decorator](https://www.tutorialsteacher.com/python/property-decorator) and make it protected, as shown below.

```python
class Student:
	def __init__(self,name):
		self._name = name
	@property
	def name(self):
		return self._name
	@name.setter
	def name(self,newname):
		self._name = newname
```

Above, @property decorator is used to make the `name()` method as property and `@name.setter` decorator to another overloads of the `name()` method as property setter method. Now, `_name` is protected.

```python
>>> std = Student("Swati")
>>> std.name
'Swati'
>>> std.name = 'Dipa'
>>> std.name
'Dipa'
>>> std._name # still accessible
```

Above, we used `std.name` property to modify `_name` attribute. However, it is still accessible in Python. Hence, the responsible programmer would refrain from accessing and modifying instance variables prefixed with `_` from outside its class.

## Private Members

Python doesn't have any mechanism that effectively restricts access to any instance variable or method. Python prescribes a convention of prefixing the name of the variable/method with a single or double underscore to emulate the behavior of protected and private access specifiers.

The double underscore `__` prefixed to a variable makes it **private**. It gives a strong suggestion not to touch it from outside the class. Any attempt to do so will result in an AttributeError:

Example: Private Attributes

 Copy

```python
class Student:
    __schoolName = 'XYZ School' # private class attribute

    def __init__(self, name, age):
        self.__name=name  # private instance attribute
        self.__salary=age # private instance attribute
    def __display(self):  # private method
	    print('This is private method.')
```

```python
>>> std = Student("Bill", 25)
>>> std.__schoolName
AttributeError: 'Student' object has no attribute '__schoolName'
>>> std.__name
AttributeError: 'Student' object has no attribute '__name'
>>> std.__display()
AttributeError: 'Student' object has no attribute '__display'
```

Python performs name mangling of private variables. Every member with a double underscore will be changed to `_object._class__variable`. So, it can still be accessed from outside the class, but the practice should be refrained.

```python
>>> std = Student("Bill", 25)
>>> std._Student__name
'Bill'
>>> std._Student__name = 'Steve'
>>> std._Student__name
'Steve'
>>> std._Student__display()
'This is private method.'
```


Decorator:
Consider that we have the `greet()` function, as shown below.

```python
def greet():
	print('Hello! ', end='')
```

Now, we can extend the above function's functionality without modifying it by passing it to another function, as shown below.

```python
def mydecorator(fn):
	fn()
	print('How are you?')
```

Above, the `mydecorator()` function takes a function as an argument. It calls the argument function and also prints some additional things. Thus, it extends the functionality of the `greet()` function 

```python
>>> mydecorator(greet)
Hello! How are you?
```

The `mydecorator()` is not a decorator in Python. The decorator in Python can be defined over any appropriate function using the `@decorator_function_name` syntax to extend the functionality of the underlying function.
The following defines the decorator for the above `greet()` function.
```python
def mydecorator(fn):
    def inner_function():        
        fn()
        print('How are you?')
    return inner_function
```

The `mydecorator()` function is the decorator function that takes a function (any function that does not take any argument) as an argument. The inner function `inner_function()` can access the outer function's argument, so it executes some code before or after to extend the functionality before calling the argument function. The `mydecorator` function returns an inner function.
Now, we can use `mydecorator` as a decorator to apply over a function that does not take any argument, as shown below.
```python
@mydecorator
def greet():
	print('Hello! ', end='')
```
Now, calling the above `greet()` function will give the following output.

```python
>>> greet()
Hello! How are you?
```

The `mydecorator` can be applied to any function that does not require any argument. For example:

```python
@mydecorator
def dosomething():
	print('I am doing something.', end='')
```


```python
>>> dosomething()
I am doing something. How are you?
```

The typical decorator function will look like below.

```python
def mydecoratorfunction(some_function): # decorator function
    def inner_function(): 
        # write code to extend the behavior of some_function()
        some_function() # call some_function
        # write code to extend the behavior of some_function()
    return inner_function # return a wrapper function
```


Nhập thư viện: from PIL import Image, từ đó 
```python
img1 = Image.open("shutterstock_274566236.jpg")
img1.show()
```
-> open file ảnh ở bên ngoài
Nhập thư viện
import cv2
from google.colab.patches import cv2_imshow : chỉ có thể dùng được trên google, nếu ở jupyter note thì sử dụng cv2.imshow():
Ví dụ
```python
image = cv2.imread('example/image.png')  
cv2.imshow("test", image)
# waits for user to press any key
# (this is necessary to avoid Python kernel form crashing)
cv2.waitKey(0)
  
# closing all open windows
cv2.destroyAllWindows()
```
Hàm imread có 2 tham số , tham số thứ 2:
![[Pasted image 20230420192322.png]]
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

Tách kênh màu: 
lưu ý: nếu sử dụng plt.imshow: sẽ đọc màu đỏ tương ứng index là 2
nếu sử dụng cv2.imshow: sẽ đọc màu xanh tương ứng với index là 0
(Chat GPT)

When you use the `imshow` function to display a color image, it expects the image to be in the BGR (Blue-Green-Red) format instead of the RGB (Red-Green-Blue) format. So, to display the image with proper colors, you need to convert the image from RGB to BGR. Here's an example:
Hàm imshow sử dụng từ trái sang phải là BGR. Lớp cắt đầu tiên của các lớp là lớp Blue, cắt cắt thứ 2 là lớp Green. Và lớp cuối cùng là lớp Red. Tuy nhiên, khi display trên plt thì sẽ sử dụng hệ màu RGB
Nếu vẽ plot luôn hàm `img[:,:,2]` thì mặc định sử dụng thang grey scale
-> Do đó phải cắt + gép
```python
blue_img = img[:,:,1]
tmp_img = np.zeros_like(img)
tmp_img[:,:,1] = blue_img
plt.imshow(tmp_img)
```
Chú ý cách đọc shape: 
```python
arr = np.array([[[1, 2,3], [3, 4,4]], [[1,5, 6], [7, 0,8]], [[1,5, 6], [7, 0,8]], [[1,5, 6], [7, 0,8]]])
arr.shape
```
-> (4, 2, 3)
4 lớp, mỗi lớp 2 hàng, mỗi hàng 2 cột
![[Pasted image 20230420205226.png]]
![[Pasted image 20230422075943.png]]
Lấy 1 vùng ảnh: 
```python
partial = img[200:400, 100:300]
```

BGR is a commonly used color space in computer vision and image processing. In this color space, colors are represented using three channels: blue, green, and red. Each channel is represented by an 8-bit value (0-255). The BGR color space is used in OpenCV, which is a popular library for computer vision.

HSV, on the other hand, is a color space that represents colors using three parameters: hue, saturation, and value. Hue represents the color, saturation represents the intensity of the color, and value represents the brightness. The HSV color space is more intuitive for humans than the BGR color space, and it is often used for color segmentation and detection in computer vision.

Blurring:
```
blur_img = cv2.GaussianBlue(img,(5,5),0) colab
```
Resizing:
```
resize_img = cv2.resize(img,(260,260),interpolation = cv2.INTER_AREA)
```

Xử lý văn bản:
Tách câu - > sử dụng hàm sent_tokenize
```python
import nltk # thư viện nltk để xử lí văn bản
```
```python
nltk.download('punkt') # tải dữ liệu chứa các từ kí tự dùng để phân tách
from nltk.tokenize import sent_tokenize
tokenized_text = sent_tokenize(text)
```
Tách từ:
```python
from nltk.tokenize import word_tokenize # dùng hàm này
tokenized_words = word_tokenize(text)
```

Loại bỏ từ không quan trọng
```python
nltk.download('stopwords') # tải dữ liệu chứa các stopwords
from nltk.corpus import stopwords
```

```python
filtered_sent = []
stop_words = set(stopwords.words("english"))
for  w in tokenized_words:
	if w.lower() not in stop_words:
		filtered_sent.append(w)
```
`stopwords.words("english")` is a function call to retrieve the list of stopwords for the English language from the NLTK (Natural Language Toolkit) library in Python.
(giá trị trả về dưới dạng list, sau đó chueyenr về set)\

Hoặc có thể dùng hàm :
```python
filtered_words = [word for word in tokenized_words if word.lower() not in stopwords.words('english')]
```

Chuẩn hoá từ 
2 Cách để chuẩn hoá từ là Stemmer (ít chính xác + nhanh) và Lemmatizer (chính xác + chậm)
Chuẩn hoá từ là loại bỏ các hậu tố như ed, s, ing

```python
from nltk.stem import PorterStemmer
from ntlk.stem.wordnet import WordNetLemmatizer

ps = PorterStemmer()
wl = WordNetLemmatizer()

# đối với phương pháp Stemmer:
ps.stem('goes') # trả về goe, expect là go thôi
# đối với phương pháp Lemmatizer
nltk.download('wordnet')
wl.lemmatize('goes', "v") # kết quả là go, "v" là duuoiws dạng động từ 

```

Bag of Words

```python
from sklearn.feature_extraction.text import CountVectorizer
corpus = [ 
		  'This is the first document', 
		  'This document is the second document', 
		  ' And this is the third one', 
		  'Is this the first document'
		]
vectorizer = CountVectorizer() ## Create CountVectorizer object
x= vectorizer.fit_transform(corpus)

```
```python
vectorizer.get_feature_names_out() # Use fit_transform to generate the document-term matrix
#array(['and', 'document', 'first', 'is', 'one', 'second', 'the', 'third', 'this'], dtype=object)
```
```python
x.toarray()   
# Print the document-term matrix
```
array([[0, 1, 1, 1, 0, 0, 1, 0, 1],
       [0, 2, 0, 1, 0, 1, 1, 0, 1],
       [1, 0, 0, 1, 1, 0, 1, 1, 1],
       [0, 1, 1, 1, 0, 0, 1, 0, 1]], dtype=int64)
Trong từng hàng , đếm số lượng từ. Ví dụ trong câu đầu 'This is the first document' thì 'and' ko xuất hiện ->0

Xử lý âm thanh:
`%matplotlib inline` is a command in Jupyter Notebook and JupyterLab that allows the resulting plots of data visualizations to be displayed directly in the notebook interface.

```python
import librosa.display
import IPython.display
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline
```

```python
data, sr = librosa.load("test.mp3") # load file audio
```
data: chứa dữ liệu sau lấy mẫu của đoạn âm thanh. bản chất đay chỉ là dữ liệu theo trục thời gian (dạng array)
sr: tần suất lấy mẫu của dữ liệu âm thanh

Tái tạo bản âm thanh:
```python
IPython.display.Audio(data =data, rate = sr)
```

Tách hoạ âm (harmonic) và nhạc cụ (percussive):
```python
y_h, y_p = librosa.effects.hpss(data)
IPython.display.Audio(data =y_h, rate=sr)
IPython.display.Audio(data =y_p, rate=sr)
```

Thay đổi cao độ bài nhack
```python
y_shift = librosa.effects.pitch_shift(data, sr, 7) # max là 12
IPython.display.Audio(data =y_shift, rate=sr)
```

Thay đổi tốc độ bài nhạc:
```python
y_slow = librosa.effects.time_stretch(data, 0.5)
IPython.display.Audio(data =y_slow, rate=sr)
```

Đại số tuyến tính:
Scalar - tensor : có 2 thông số ndim (chiều) và shape (kích thước)
Tích 2 ma trận : `A.dot(B)`
Ma trận chuyển vị: `A.T`
Định thức của ma trận: `np.linalg.det(A)`
Ma trận nghịch đảo: `np.linalg.inv(A)`
Ma trận đường chéo: `np.diag([1, 2, 3])`
Hạng của ma trận: `np.linalg.matrix_rank(a)`
```python
[[1 0 0]
 [0 2 0]
 [0 0 3]]
```
Ma trận đơn vị cấp 3: `np.eye(3)`
Tạo ma trận : `np.zeros((x,y,z))` x lớp, y số hàng mỗi lớp, z số cột mỗi lớp
![[Pasted image 20230422083852.png]]
Tính chất định thức ma trận:
![[Pasted image 20230422085835.png]]
 Trị riêng:
 ![[Pasted image 20230422090037.png]]
Gradien:
![[Pasted image 20230422090804.png]]

![[Pasted image 20230422092457.png]]

Tạo dãy n phần tử: `np.arange(n)`
Đổi dãy n phần tử về ma trận: `reshape((x, y))` , với n = x*y , x hàng, y cột

Tạo list gồm n phần tử từ số 0: list(range(n))
Ví dụ về hàm train_test_split:
```python
>>> import numpy as np
>>> from sklearn.model_selection import train_test_split
>>> X, y = np.arange(10).reshape((5, 2)), range(5)
>>> X
array([[0, 1],
       [2, 3],
       [4, 5],
       [6, 7],
       [8, 9]])
>>> list(y)
[0, 1, 2, 3, 4]
```
```python
>>> X_train, X_test, y_train, y_test = train_test_split(
...     X, y, test_size=0.33, random_state=42)
...
>>> X_train
array([[4, 5],
       [0, 1],
       [6, 7]])
>>> y_train
[2, 0, 3]
>>> X_test
array([[2, 3],
       [8, 9]])
>>> y_test
[1, 4]
```
```python
>>> train_test_split(y, shuffle=False) # tức là không xáo trộn
[[0, 1, 2], [3, 4]]
```

Support vector machine:
```python 
from sklearn import datasets
from sklearn.model_selection import train_test_split
from sklearn.svm import SVC
from sklearn.metrics import accuracy_score

# Load the iris dataset
iris = datasets.load_iris()
X = iris.data
y = iris.target
#-   `iris.data` contains the features (i.e., petal length, petal width, sepal length, and sepal width) for each instance in the dataset.
#-   `iris.target` contains the target variable (i.e., the class labels) for each instance in the dataset.

# Split the dataset into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)
#`X` and `y` are the feature matrix and target variable, respectively.
#`test_size` parameter is set to 0.3, which means that 30% of the data will be used for testing.
#`random_state` parameter is set to 42, which ensures that the same random split is obtained every time the code is run. Hàm này giống như seed()

# Create a Support Vector Machine classifier
clf = SVC(kernel='linear')
#`kernel` parameter is set to `'linear'`, which means that a linear kernel function will be used.

# Train the classifier on the training set
clf.fit(X_train, y_train)

# Make predictions on the testing set
y_pred = clf.predict(X_test)
#`predict` method is used to make predictions on the testing set.

# Calculate the accuracy of the classifier
accuracy = accuracy_score(y_test, y_pred)
#`accuracy_score` function is used to calculate the accuracy of the classifier by comparing the predicted labels (`y_pred`) with the true labels (`y_test`).

print(f"Accuracy: {accuracy}")
```
Accuracy: 1.0


Vẽ ảnh Support vector machine: 
Khái niệm meshgrid: use Numpy meshgrid to create a rectangular grid of x and y values.
![[Pasted image 20230506170112.png]]

Cách sử dụng hàm `np.c_`
```python
a = np.array([1, 2, 3, 4, 5])
b = np.array([6, 7, 8, 9, 10])
c = np.c_[a, b]
```
![[Pasted image 20230506171127.png]]

Cách sử dụng hàm `.ravel()`: trả về mảng 1 chiều, giống hàm `.flatten()`
```python
a = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]]])
b = a.ravel()
```
Flattened array: [1 2 3 4 5 6 7 8]

Cách sử dụng hàm linspace: 
```python
np.linspace(start, stop, num)
x = np.linspace(0, 1, 10)
```
![[Pasted image 20230506173901.png]]
Công thức : step = (stop - start) / (num-1)


```python
import numpy as np
import matplotlib.pyplot as plt
from sklearn import svm, datasets

# Load Iris dataset
iris = datasets.load_iris()
X = iris.data[:, :2]  # We only take the first two features for visualization
y = iris.target

# Create an instance of SVM with linear kernel
C = 1.0  # SVM regularization parameter
clf = svm.SVC(kernel='linear', C=C)

# Fit SVM on data
clf.fit(X, y)

# Create a meshgrid of points to plot decision boundary
x_min, x_max = X[:, 0].min() - 1, X[:, 0].max() + 1
y_min, y_max = X[:, 1].min() - 1, X[:, 1].max() + 1
xx, yy = np.meshgrid(np.arange(x_min, x_max, 0.02),
                     np.arange(y_min, y_max, 0.02))
Z = clf.predict(np.c_[xx.ravel(), yy.ravel()])

# Plot decision boundary and data points
Z = Z.reshape(xx.shape)
plt.contourf(xx, yy, Z, cmap=plt.cm.coolwarm, alpha=0.8)
plt.colorbar()
plt.scatter(X[:, 0], X[:, 1], c=y, cmap=plt.cm.coolwarm)
plt.colorbar()
plt.xlabel('Sepal length - xx')
plt.ylabel('Sepal width - yy')
plt.xlim(xx.min(), xx.max())
plt.ylim(yy.min(), yy.max())
plt.xticks(np.arange(x_min, x_max, 1))
plt.yticks(np.arange(y_min, y_max, 0.5))
plt.title('Linear Kernel SVM')
plt.show()
```
![[Pasted image 20230506182415.png]]]]