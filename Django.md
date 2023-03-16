pwd : xem directory hiện tại

cd [tên folder]: trỏ đến directory tiếp theo

cd ..: lùi

mkdir [tên folder muốn tạo]: tạo folder, vị trí đứng vẫn như cũ

ls: list các thư mục hiện hành

 Cũng giống như máy ảo (Virtual Machine), Virtual Environment thiết lập một môi trường ảo, cho phép bạn thoải mái thực hiện cài đặt rồi xóa, cài đặt các phiên bản khác nhau với các packages của Python mà không sợ làm ảnh hưởng đến những dự án đang có sẵn.
 ![[Pasted image 20230218164100.png]]
 Giả sử ta đang đứng ở dự án sử dụng Python 2.2, Django 2. Phải set virtual environment để những ứng dụng khác chạy trên không gian ảo của chúng, vì chỉ có những không gian ảo đó tích hợp những specific features mà những dự án đó cần.
 
Lưu ý: venv: tạo package để tạo môi trường ảo

python -m venv env : trong đó env là tên thư mục do mình đặt


Cách tạo môi trường ảo: vào powerself với Admin,

gõ dòng lệnh để có thể execute: set-executionpolicy remotesigned, chọn Yes to All

sau đó vào lại terminal vsc và : env\Scripts\activate

để deactivate thì chỉ cần: deactivate (làm mất chữ màu xanh env)

dừng execute terminal: Ctrol C

cài Django: python -m pip install Django

xem list: pip list

django-admin --version : check version Django

django-admin startproject [tên project]

hoặc

django-admin startproject [tên project] .


setting: các phần cài đặt them

url: api

wsgi: tương tác server

python manage.py runserver : chạy server

python manage.py runserver [số port : 4 số] : chạy server theo port

ctrol S : save, format và chạy lại server


Ctrol Shift P: chọn terminal select default: powershelf

Start app:

python manage.py startapp [tên app]

Lưu ý: để hệ thống tự động activate env thì : ctrol shift P để mở palette, sau đó chọn select Python theo Env chứ ko phải theo python đã cài đặt mặt định

import . : các thư mục cùng directory
![[Pasted image 20221229141938.png]]
![[Pasted image 20221229141946.png]]
lệnh reverse chỉ để lấy url dựa trên name

Cách render 1 file html: 
vào settings, add install - app: myapp.app.MyappConfig
đặt tên folder trong myapp: đặt tên - templates, để django hiểu và quét vào thư mục này
folder template chứa file html
thư mục views: 
```python
def greeting(request):

    template = loader.get_template('hello.html')

    context={}

    return HttpResponse(template.render(context,request))
```

```
dùng dấu chấm để chỉ index của 1 list
<h2>{{list.0}}</h2>
```

lệnh render: 
![[Pasted image 20221229153759.png]]

if - else trong django![[Pasted image 20221229161446.png]]

for loop:

![[Pasted image 20221229161408.png]]

---------------------
built-in filter reference:
```
{{ value|add:"2" }} 
If `value` is `4`, then the output will be `6`.
```

```
{{ first|add:second }}
`first` is `[1, 2, 3]` and `second` is `[4, 5, 6]`, then the output will be `[1, 2, 3, 4, 5, 6]`.
```

addslashes:

```
{{ value|addslashes }}
If `value` is `"I'm using Django"`, the output will be `"I\'m using Django"`.
```

capfirst

```
{{ value|capfirst }}
f `value` is `"django"`, the output will be `"Django"`.
```

center: để ở giữa trong 15 kí tự

```
"{{ value|center:"15" }}"
If `value` is `"Django"`, the output will be `"     Django    "`.
```

cut

```
{{ value|cut:" " }}
If `value` is `"String with spaces"`, the output will be `"Stringwithspaces"`.
```

date:

```
{{ value|date:"D d M Y" }}

```
If `value` is a [`datetime`](https://docs.python.org/3/library/datetime.html#datetime.datetime "(in Python v3.11)") object (e.g., the result of `datetime.datetime.now()`), the output will be the string `'Wed 09 Jan 2008'`.

`{{ value|date:"D d M Y" }}`

-> If `value` is a [`datetime`](https://docs.python.org/3/library/datetime.html#datetime.datetime "(in Python v3.11)") object (e.g., the result of `datetime.datetime.now()`), the output will be the string `'Wed 09 Jan 2008'`.

** các loại format spefifier:  [`DATE_FORMAT`](https://docs.djangoproject.com/en/4.1/ref/settings/#std-setting-DATE_FORMAT), [`DATETIME_FORMAT`](https://docs.djangoproject.com/en/4.1/ref/settings/#std-setting-DATETIME_FORMAT), [`SHORT_DATE_FORMAT`](https://docs.djangoproject.com/en/4.1/ref/settings/#std-setting-SHORT_DATE_FORMAT) or [`SHORT_DATETIME_FORMAT`](https://docs.djangoproject.com/en/4.1/ref/settings/#std-setting-SHORT_DATETIME_FORMAT)
Mặc định là  [`DATE_FORMAT`](https://docs.djangoproject.com/en/4.1/ref/settings/#std-setting-DATE_FORMAT)
Ví dụ: 
`{{ value|date:"SHORT_DATE_FORMAT" }}`
-> "09/01/2008" 

`{{ value|date }}`
-> 9 de Enero de 2008

Kết hợp date + time:
`{{ value|date:"D d M Y" }} {{ value|time:"H:i" }}`

default:
```
{{ value|default:"nothing" }}
```
-> If `value` is `""` (the empty string), the output will be `nothing`.

default_if_none:
```
{{ value|default_if_none:"nothing" }}
```
-> If `value` is `None`, the output will be `nothing`.

dictsort:
```
{{ value|dictsort:"name" }}
```
![[Pasted image 20221230094633.png]]

```
{% for book in books|dictsort:"author.age" %}
    * {{ book.title }} ({{ book.author.name }})
{% endfor %}
```
![[Pasted image 20221230095132.png]]

```
{{ value|dictsort:0 }}
```
![[Pasted image 20221230095348.png]]

dictsortreversed >< dictsort

divisibleby:

```
{{ value|divisibleby:"3" }}
```
-> If `value` is `21`, the output would be `True`.

first: 
```
{{ value|first }}
```
-> If `value` is the list `['a', 'b', 'c']`, the output will be `'a'`.

join:

```
{{ value|join:" // " }}
```
-> If `value` is the list `['a', 'b', 'c']`, the output will be the string `"a // b // c"`.

length:

```
{{ value|length }}
```
-> If `value` is `['a', 'b', 'c', 'd']` or `"abcd"`, the output will be `4`.

length_is:
```
{{ value|length_is:"4" }}
```
-> If `value` is `['a', 'b', 'c', 'd']` or `"abcd"`, the output will be `True`.

linenumbers:
```
{{ value|linenumbers }}
```
![[Pasted image 20221230100947.png]]

make_list: 

```
{{ value|make_list }}
```
-> If `value` is the string `"Joel"`, the output would be the list `['J', 'o', 'e', 'l']`
https://docs.djangoproject.com/en/4.1/ref/templates/builtins/#built-in-filter-reference

forloop.counter:
mặc định là counter1 : tức là chạy từ index 1 chứ ko phải 0

```
{{forloop.counter}}
```
-> return index

-----
Comment:
![[Pasted image 20221230101758.png]]

url:

```
{% url 'đường dẫn'  %}
```
```
{{% url 'đường dẫn' forloop.counter0 %}}, chỉ được dùng trong vòng lặp for
```
đường dẫn có thể name của 1 path được định nghĩa trong file urls

--------
![[Pasted image 20221230205536.png]]

cách sử dụng lệnh: 
python [tên file chạy app] + [chức năng migrate]
lưu ý: sqlmigrate + tên app + mã số migrate

Cách tạo 1 instance: 
![[Pasted image 20221231100345.png]]

hoặc 
```
JobPost.objects.create(title = "Second job post", description = "Example 2", salary = 10000)
```

`exit()` để logout python shell

fetch all:
`JobPost.objects.all()`
hoặc gán:
`all_posts=JobPost.objects.all() `
`print(all_posts)`

filter: 
`JobPost.objects.filter(title = "", description = "Example")`
trả về kết quả dưới dạng list object
trong đó, description và title là trường cần filter
nếu ko có -> trả về list rỗng
nếu có 2 kết quả -> vẫn trả về list 2 phần tử
có thể limit bằng cách sử dụng các phương thức của list: 
`JobPost.objects.filter(title = "", description = "Example")[1:2]`

hoặc
`JobPost.objects.get(title = "")` phương thức get để fetch a single object
trả về kết quả dưới dạng object duy nhất
nếu ko có - > trả về lỗi
nếu có 2 kết quả -> trả về lỗi

hàm ngược với filter là exclude

order_by
trả về danh sách , có thể multi para
`JobPost.objects.order_by("?")` trả về random

------------
lookup fields : tương đương với mệnh đề WHERE trong query: filter(), exclude() and get().

* exact:
![[Pasted image 20230102095850.png]]

+ iexact: case-insensitive
![[Pasted image 20230102100052.png]]

+ contains: 
![[Pasted image 20230102100132.png]]

+ icontains: case-insensitive:
![[Pasted image 20230102100202.png]]

+ in:
![[Pasted image 20230102100457.png]]

+ nested queries: 
```
inner_qs = Blog.objects.filter(name__contains='Cheddar')
entries = Entry.objects.filter(blog__in=inner_qs)
```
=
```
SELECT ... WHERE blog.id IN (SELECT id FROM ... WHERE NAME LIKE '%Cheddar%')
```

Cách 2:  truyền 1 cái tên là "name" rồi câu trên query theo name
```
inner_qs = Blog.objects.filter(name__contains='Ch').values('name')
entries = Entry.objects.filter(blog__name__in=inner_qs)
```
-> Lưu ý: chỉ đc dùng 1 name

+ gt: greater than
![[Pasted image 20230102102251.png]]

+ gte : >= 
+ lt : < 
+ lte: <=
+ startswith
![[Pasted image 20230102102422.png]]

+ istartswith
+ endswith
+ iendswith
+ range: là BETWEEN trong sql
![[Pasted image 20230102102654.png]]

+ isnull : 
![[Pasted image 20230102102901.png]]

+ regex:
![[Pasted image 20230102103018.png]]

+ iregex:
![[Pasted image 20230102103108.png]]

--------
gán:
`job_post_1 = JobPost.objects.filter()[0]`
có thể lấy content của từng phần tử:
`job_post_1.title`
`job_post_1.salary`

lưu:
```
job_post_1.save
```

--> Lưu ý: có thể combine: ví dụng `filter().exclude()`

--------------
` Python: *args và **kwargs`

arg : là 1 tuple, ko phải là 1 list
```
>>> def foo(numbers):
...     result = 0
...     for n in numbers:
...         result += n
...     return result
...
>>> foo([1, 2])
3
>>> foo([1, 2, 3])
6

```
```
>>> def foo(*args):
...     result = 0
...     for x in args:
...         result += x
...     return result
...
>>> foo(1, 2)
3
>>> foo(1, 2, 3)
6

```

kết hợp arg với các tham số khác: 
```
>>> def foo(a, b, *args):
...     print('normal arguments', a, b)
...     for x in args:
...         print('another argument through *args', x)
...
>>> foo(1, 2, 3, 4)
normal arguments 1 2
another argument through *args 3
another argument through *args 4

```

kwargs: là dạng keyword args

```
>>> def foo(a=0, b=1):
...     return a + b
...
>>> foo()
1
>>> foo(1, 2)
3
>>> foo(b=3, a=4)
7

```
```
>>> def foo(a):
...     for key, value in a.items():
...         print(key, value)
...
>>> foo({'a': 1, 'b': 2})   phải truyền vào là 1 dạng dictionary
a 1
b 2

```
```
>>> def foo(**kwargs):
...     for key, value in kwargs.items():
...         print(key, value)
...
>>> foo(a=1, b=2)
a 1
b 2

```

Unpack
```
>>> x = (1, 2, 3)
>>> print(x)
(1, 2, 3)
>>> print(*x)
1 2 3

```
```
>>> def foo(a, b, c):
...     print("a = %d, b = %d, c = %d" % (a, b, c))
...
>>> foo(1, 2, 3)
a = 1, b = 2, c = 3

```
```
>>> x = (4, 5, 6)
>>> foo(*x)
a = 4, b = 5, c = 6
>>> y = {'a': 7, 'b': 8, 'c': 9}
>>> foo(**y)
a = 7, b = 8, c = 9

```
-----
slug:

tạo hàm slug  save trong models:
```
    def save(self, *args, **kwargs):

        self.slug = slugify(self.title)

        return super(JobPost, self).save(*args, **kwargs)
```

get all toàn bộ : JobPost.objects.get()
muốn update slug: JobPost.objects.get()[0].slug rồi .save()
JobPost.objects.count() : đếm

để dùng Avg, nhập import: `from Django.db.models import Avg`
`JobPost.objects.aggregate(Avg("salary")`) 

import Max tương tự như Avg
`JobPost.objects.aggregate(Max("salary")`) 
-> `{'salary__avg': 41000.0}`

đặt tên:
`JobPost.objects.aggregate(mymax = Max("salary")`) `
-> `{'mymax': 41000.0}`

phải đặt tên-alias khi tính toán nhiều hàm trở lên
`JobPost.objects.aggregate(mymax = Max("salary") - Avg("salary")`) `
-> `{'mymax': 8415.0}`

.delete() : xóa, trả về count các phầm tử bị xóa và phần tử bị xóa

Xóa sạch data
```python
Reporter.objects.all().delete()
```
---------
thiết lập tài khoản: 
`python manage.py createsuperuser`

nếu quên tài khoản, mật khẩu: 
```python
python manage.py shell
```

```python
from django.contrib.auth.models import User
User.objects.filter(is_superuser=True)
```
thiết lập lại mật khẩu:

```csharp
usr = User.objects.get(username='your username')
usr.set_password('raw password')
usr.save()
```

thiết lập admin panel cho app của chúng ta:
`admin.site.register(JobPost)` trong myapp/admin

![[Pasted image 20230110141459.png]]
models.Model : dùng để quản lí tất cả các column trong database
admin.ModelAdmin : dùng để quản lí các column trong database, dành riêng cho admin
-- List_display là 1 tuple, do đó nếu có 1 phần tử thì: ('title',) , tức là phải có dấu phẩy

search + search note:
```
    search_fields = ('title',)

    search_help_text = "Type the search keywords"
```

show các fields của 1 instance: 
`fields = (('title', 'description'), 'expiry')` : trong đó title và description nhóm lại với nhau
![[Pasted image 20230110144415.png]]

ko show: exclude()

thiết lập fieldset:
```
    fieldsets = (

        ('Basic information', {'fields':('title', 'description')}),

        ('More information', {'fields':(('salary', 'expiry'),'slug')}))
```
![[Pasted image 20230110150003.png]]

collapse: muốn collapse chỗ nào thì bỏ vô chỗ đó: (wide ko quan trọng)
`('More information', {'classes':('collapse','wide'), 'fields':(('salary', 'expiry'),'slug')})`
![[Pasted image 20230110150659.png]]

------
references:
->class JobPost:
`location = models.OneToOneField(Location, on_delete=models.CASCADE, null = True)`
-   `CASCADE`: When the referenced object is deleted, also delete the objects that have references to it (when you remove a blog post for instance, you might want to delete comments as well). SQL equivalent: `CASCADE`.
-   `PROTECT`: Forbid the deletion of the referenced object. To delete it you will have to delete all objects that reference it manually. SQL equivalent: `RESTRICT`.
-   `RESTRICT`: _(introduced in Django 3.1)_ Similar behavior as `PROTECT` that matches SQL's `RESTRICT` more accurately. (See [django documentation example](https://docs.djangoproject.com/en/stable/ref/models/fields/#django.db.models.RESTRICT))
-   `SET_NULL`: Set the reference to NULL (requires the field to be nullable). For instance, when you delete a User, you might want to keep the comments he posted on blog posts, but say it was posted by an anonymous (or deleted) user. SQL equivalent: `SET NULL`.
-   `SET_DEFAULT`: Set the default value. SQL equivalent: `SET DEFAULT`.
-   `SET(...)`: Set a given value. This one is not part of the SQL standard and is entirely handled by Django.
-   `DO_NOTHING`: Probably a very bad idea since this would create integrity issues in your database (referencing an object that actually doesn't exist). SQL equivalent: `NO ACTION`. **(2)**

query 2 bảng:
`JobPost.objects.get(location=l1)`, l1 đc đặt tên trong command line
`JobPost.objects.get(location__street="absadac")`: lưu ý dùng 2 dấu gạch dưới
`JobPost.objects.get(location__street__startwith = "a")`

query ngược:
`Location.objects.get(jobpost=job1)` , trong đó `job1`: đc đặt tên trong command line

có thể gán trực tiếp author
`job6 = JobPost(title="Sixth job post", description = "Example 6", salary = "152000", author = author1)`


tạo jobpost có luôn author
`job7 = author1.jobpost_set.create(title="Seventh job post", description = "Example 7", salary="25000")`

bổ sung thêm job có author là author1
`author1.jobpost_set.add(job1) `

đếm số job có author là author1:
`author1.jobpost_set.count()  `

show all:
`author1.jobpost_set.all()  `

filter những jobpost có author là author1:
`author1.jobpost_set.filter(...)  `

lấy những jobpost có id hay pk (pk là primary key = id)
`JobPost.objects.filter(author__pk=1)  ``

lấy những jobpost có id trong phạm vi 1,2:
`JobPost.objects.filter(author__in=[1,2])`

Cách sử dụng các mối quan hệ database: ForeignKey là many to one
![[Pasted image 20230116115708.png]]
manytomany : có bảng riêng

![[Pasted image 20230116221731.png]]
-> tức là skills__id=1

distinct: lấy những unit
`JobPost.objects.filter(skills__in=[1,2,3]).distinct()`

remove:
`job1.skills.remove(skill_1)`
`skill_1.jobpost_set.remove(job1)`

set skill cho jobpost, nếu chưa  có sẽ thêm, nếu set ít hơn cái đã có -> xóa
`job5.skills.set([skill_1,skill_2,skill_3]) `

xóa toàn bộ skills
`job5.skills.clear()`

add nhiều job cho 1 skill:
`skill_3.jobpost_set.add(job6,job4)`

_CSRF là_ một kiểu tấn công gây sự nhầm lẫn tăng tính xác thực và cấp quyền của nạn nhân khi gửi một request giả mạo đến máy chủ.

Nguyên lí làm việc của form:

form được load lần đầu : là Get chứ không phải post. 
do đó lượt bỏ qua hết những phần khoang vùng
![[Pasted image 20230118111004.png]]
![[Pasted image 20230121123430.png]]
form đưuọc submit (tức là phương thức get) ->quay ngược lại  url trong urls -> thực hiện function subscribe. Submit là chạy lại url (từ đầu), trong khi refresh là giữ nguyên màn hình
Lúc này mệnh đề if đc thực thi

Tạo dạng form mới tự động: import forms 

`Form.is_valid`() 
kết quả trả về true/false : thông tin đã được validate chưa. Ví dụ :
![[Pasted image 20230118203243.png]]
field subject thiếu dữ liệu -> false

thông tin để móc nối dữ liệu dựa trên attribute: name

remigration thì nhớ select 1 rồi 0

các hình thức render form trong html: form.as_p, form.as_table, form.as_ul

form option: max_length, required= False/True, label =  " " - hiển thị label thay vì label của biến đã đc,  help_text = " " - hướng dẫn , disable = True - bị disable

 sử dụng validate:
tạo hàm `clean_tên field` hoặc thêm option validators

cách sử dụng attributes fields: {{  attributes  }}
`field.tên field`: render fiedl từ form
`field.errors`: render validation errors
`field.label`: render label đã được set sẵn trong form
`field.id_for_label`: trả về id của field cho label tag
`field.help_text`: cho phép tiếp cận help text trong form
`field.label_tag`: tạo ra label tg

dùng modelForm thì data input sẽ đc clean, đồng thời ko cần phải định nghĩa từng fields trong views

Kiểm tra thông tin validators: 
```
from register.forms import RegisterForm
email = Register().field["email"]
email.validators

```

Cách để tạo 1 file style riêng
đặt tên folder : static, tạo file css trong folder static
add file: 
```
{% load static %} -> chú ý phải load folder

<!DOCTYPE html>

<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta http-equiv="X-UA-Compatible" content="IE=edge">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Register Form</title>

    <link rel="stylesheet" type= "text/css" href="{% static 'style.css' %}" >

</head>
```
restart lại server: 
`python manage.py runserver`

upload file ảnh + add in database
edit setting: các file sẽ được tự động cập nhật trong folder uploads
![[Pasted image 20230130095832.png]]
lưu ý: ảnh sẽ được lưu vào thư mực images, là subfolder của uploads
thiết lập views:
```
def uploadapp(request):

    form = uploadappForm()

    if request.POST:

        form = uploadappForm(request.POST, request.FILES)

        if form.is_valid():  

            form.save()

            return redirect(reverse('thank_you'))

    context = {"form": form}

    return render(request, 'uploadapp/add_image.html', context)

  

def thank_you(request):

    context = {}

    return render(request, 'uploadapp/thank.html', context)
```
thiết lập html:
```
    <form method="post" enctype="multipart/form-data" >

     {% csrf_token %}  

    {{form.as_p}}

    <button type="submit">Upload</button>
```
![[Pasted image 20230205114158.png]]
phân biệt MEDIA_ROOT : là nơi luu giữ những hình ảnh mà user submit
MEDIA_URL : nơi mà các ảnh được uploaded được serverd, cách để tiếp cận các hình ảnh uploaded


