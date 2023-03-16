![](https://i.imgur.com/7kPxkJ4.png)

1. Các giá trị truthy : ko phải falsy: false, 0 , -0 , 0n, null, undefined, NaN, "", ``, ''
truthy (1) && truthy (2) => trả về truthy (2)

Falsy: 
falsy (1) && falsy(2) => trả về falsy (1)

2. `array.map(function)`: _array_.map(_function(currentValue, index, arr), thisValue_)
nếu function trong map là điều kiện dạng `a>b` hay `a<b` thì trảng về mảng toàn bộ là [true,false,....]


`array.filter(function)`: _array_.filter(_function(currentValue, index, arr), thisValue_)
nếu function trong map r`return value` thì filter trả về các truthy


`array.reduce(function)`: _array_.reduce(function(total, currentValue, currentIndex, arr), initialValue)

![](https://i.imgur.com/5q4y2wi.png)

`array.sort(function)`
Lưu ý, sort chỉ dành cho string, nếu sort theo số: 
`points.sort(function(a, b){return a - b})` sort tăng
`points.sort(function(a, b){return b-a })` sort giảm

3. **Template litera**l khai báo string thực thi  biến, biểu thức, hàm ... : `  ``
${  }
use back-ticks (``)
4. text.toUpperCase()
text.toLowerCase()
text.repeat(4) : Hello world!Hello world!Hello world!Hello world!
`string.repeat(count)`

5. `string.split(separator, limit)` : trả về array, ko đổi mảng
If (" ") is used as separator, the string is split between words.
`array.slice(start, end)` : lấy từ phần tử start tới end-1, trả về mảng , ko đổi mảng, nếu chỉ có start thì lấy hết 
`array.splice(index, howmany, item1, ....., itemX)` : thêm hoặc xoá: nếu thêm thì howmany là 0, bổ sung các item. Nếu xoá thì howmany cho khác ko, ko có các item
**trả về phần tử bị remove**, thay đổi mảng 
`array.push(item1, item2, ..., itemX)`: **Trả về length mới**, thay đổi mảng 
`array.pop()` : và về phần tử bị pop (cuối mảng), thang đổi mảng
`array.shift()`: trả về phần tử bị remove (đầu bảng), thay đổi mảng
`array.unshift(item1, item2, ..., itemX)` : thêm phần tử vào đầu mảng, thay đỏi mảng , trả về length
`string.substring(start, end)` : lấy chuỗi con từ start đến end-1, trả về chuổi bị lấy 
`string.substr(start, end)` : lấy chuỗi con từ start đến end, trả về chuổi bị lấy 
`string.trim`: xoá khoảng trắng 2 bên, trả về chuỗi đã bị xoá khoảng trắng
```js
let text = "       Hello World!        ";  
let result = text.trim();
```
`string/array.includes(ele)`: trả về true/ false

6.
`array.find(function(currentValue, index, arr),thisValue)`
Trả về phần tử đầu tiên pass the test, trả về `undefined` nếu ko có ele thoả, ko làm đổi mảng 

`array.findIndex(function(currentValue, index, arr), thisValue)`
Tương tự: trả về index của phần tử đầu tiên thoả, trả về -1 nếu ko có

`string.indexOf(searchvalue, start)`:  index của giá trị search value, trả về -1 nếu ko có


`string.charAt(index)` : trả về kí tự tại index

++match : trả về array các matches
```js
let text = "The rain in SPAIN stays mainly in the plain";
test.match("ain") : trả về ain
text.match(/ain/);: trả về ain
text.match(/ain/g); : trả về array các matches vì g là global
text.match(/ain/gi); : trả về array các matches kể cả uppercase
```

++ `string.search(searchValue)` :trả về index của match đầu tiên , tương tự như `match()`, search được cả string và reg-ex, nhưng `indexOf` thì reg-ex ko đc
8. == cùng giá trị
=== : cùng giá trị, cùng kiểu

9.-   Primitive values ([null](https://www.javascripttutorial.net/object/javascript-null/), [undefined](https://www.javascripttutorial.net/javascript-undefined/), [boolean](https://www.javascripttutorial.net/javascript-boolean-type/), [number](https://www.javascripttutorial.net/javascript-number/), [string](https://www.javascripttutorial.net/string/), [symbol](https://www.javascripttutorial.net/es6/symbol/), and [BigInt](https://www.javascripttutorial.net/es-next/javascript-bigint/))
-   Reference values that refer to objects.

10. destructuring:
`[a, b, ...rest] = [10, 20, 30, 40, 50]`

spread operator:
```jsx
const numbersOne = [1, 2, 3];
const numbersTwo = [4, 5, 6];
const numbersCombined = [...numbersOne, ...numbersTwo];
```
=> trả về 1,2,3,4,5,6

rest parameters: 
```
function f(a, b, ...theArgs) {
  // …
}
```
ví dụ: 
```
function restTest(...args) {
  console.log(args)
}

restTest(1, 2, 3, 4, 5, 6);// [1, 2, 3, 4, 5, 6]

```


11. declare arrow funcion:
`let myFunction = (a, b) => a * b;`

hello = () => {  
  return "Hello World!";  
} 
có thể bỏ dấu () nếu có 1 biến :
hello = val => "Hello" + val;

![](https://i.imgur.com/css0MC5.png)

12. `Math.random()` returns a random number between 0 (inclusive),  and 1 (exclusive):
// Returns a random integer from 0 to 9:  
`Math.floor(Math.random() * 10);`

- floor làm tròn xuống, cell làm tròn lên
// Returns a random integer from 0 to 10:  
`Math.floor(Math.random() * 11);`

`Math.round()`: làm tròn theo quy tắt làm tròn

13. `const d = new Date();`: trả về thười gian hiện hành 

```jsx
new Date()  
new Date(_year, month, day, hours, minutes, seconds, milliseconds_)  
new Date(_milliseconds_)  
new Date(_date string_)
```


14 
object: gồm có **name:value**
Khai báo: _`objectName.propertyName`_  hoặc `objectName["propertyName"]`
```js
const person = {  
  firstName: "John",  
  lastName: "Doe",  
  age: 50,  
  eyeColor: "blue"  
};
```


JSON:  data là các cặp **name:value**, data cách nhau bởi `,` bọc các object bằng `{}`, bọc các mảng bằng `[]`
```js
const data = {  
"employees":[  
  {"firstName":"John", "lastName":"Doe"},  
  {"firstName":"Anna", "lastName":"Smith"},  
  {"firstName":"Peter", "lastName":"Jones"}  
] ,
"total": 100,
  "skip": 0,
  "limit": 30
}
```
Trong ví dụ trên json gồm 1 object "employees", object này là 1 array gồm 3 object con
Các JSON name phải được thêm ""
Khai báo:
`data.employees[1].firstName` : trả về Anna


-- Khi gửi data lên server, data phải dưới dạng string. 
Chuyển đổi object --> string dùng `JSON.stringify()`
`const obj = {name: "John", age: 30, city: "New York"};`
`const myJSON = JSON.stringify(obj);`
 ->> trả về chuỗi string {name: "John", age: 30, city: "New York"}

-- Khi nhận data từ server, data dưới dạng string 
Chuyển đổi string --> object dùng `JSON.parse()`
`'{"name":"John", "age":30, "city":"New York"}'`
`const obj = JSON.parse('{"name":"John", "age":30, "city":"New York"}');`
trả về obj

-- Json to object: https://www.convertsimple.com/convert-json-to-javascript/
-- Object to json: https://www.convertsimple.com/convert-javascript-to-json/



15. Thao tác object
-- Kiểm tra ele có trong object : dùng `in`, trả true hoặc false
```js
const myname = { name: 'John', age: 36}

console.log("age" in myname)

```

-- Lấy các keys:
```js
const myname = { name: 'John', age: 36};

console.log(Object.keys(myname))
```
--- Lấy các value:
```jsx
const myname = { name: 'John', age: 36};

console.log(Object.values(myname))
```


16. Settimeout 

`setTimeout(function, milliseconds, param1, param2, ...)`
`setTimeout(()=>console.log("Hello world!"),2000);`
setinterval: chạy liên tục 

`setInterval(_function, milliseconds, param1, param2, ..._)`
`setInterval(()=>console.log("Hello world!"),2000);`

clearinterval: ngưng chạy liên tục

```js
let time = 1;

const interval = setInterval(() => {

  console.log(time);

  time++;

  if (time === 10) {

    clearInterval(interval);

  }

}, 1000);
```












----------------------------------------------------------------------------1

** Import và export
- Cách 1:  *Theo kiểu object*
**math.js**: `exports.math = "hello   world";` exports là 1 object rỗng { }
**index.js**: 
```js
const hello = require('./math');

console.log(hello);
```
--> kết quả trả về object: `{ math: 'hello   world' }`

- Cách 2: *Theo kiểu thường*

**math.js** : 
```js
const math = "hello"

module.exports = math;
```

--> kết quả trả về "hello"
Lưu ý import theo thiểu thường, có thể đặt tên tuỳ thích và gán biến theo tên đó. Ví dụ hello(2,3)


** Lưu ý cách ghi url: require("./ [tên folder]") thì mặc định chỉ lấy file tên là index.js. Nếu là file khác thì phải thêm file đó vào . Nếu tên file trùng tên folder sẽ ưu tiên tên file

../ là ngược folder, ../../ là ngược 2 folder.
nếu ko có ./ , ví dụ   `require ("math")` thì được hiểu là import packet math chứ ko phải folder


** lưu ý: đầu tiên phải chạy 
`npm init -y` tạo package 
`npm i` tạo package- lock
`npm i nodemon ` để khỏi reload server. Cấu hình như sau: trong script add
`"start": "nodemon index.js"` . Sau đó chạy npm start. Nếu thay start bằng cái khác ví dụ như `"abc"` thì phải `npm run abc` chứ ko phải `npm abc`

** cài các package:
![](https://i.imgur.com/iiUjwmS.png)


** Cấu trúc của server
```js
const http = require('http');
const server = http.createServer((req, res) => {
  console.log('server starte'); chỉ hiển thị trong terminal, refresh browser để xem
  res.write("Hello, world!"); hiển thị trên browser
  res.end(); để endserver , nếu ko có res.end() thì browser sẽ chạy liên tục
}).listen(8080)
```

** install express để tạo API:
`npm i express`
```js
const express = require('express')

  

const app = express()

app.listen(3000 , () => {

  console.log('Server is running on port 3000');

});
```

** Cách sử dụng param.id
`app.get('/users/:id' , (req,res) => {`
`const id = req.params.id})`
lúc này sẽ lấy được id trên trên browser

**  /users/:id/:pass
trong params: `  params: { id: '1', action: '2' }`


** thao tác file:
`const fs =require("fs")`
```
fs.writeFile(tên file, comment, callbackfunction) : thêm file mới + nội dung
fs.appendFile : thêm nội dung vào cuối file, + "\n" : là newline
fs.readFile(tên file, (err,data)=>{}), data.toString() : trả về nội dung
hoặc  fs.readFile(tên file).toString() sẽ trả về nội dung 
fs.existsSync(tên file) : trả về true hoặc false
fs.unlinkSync( path ) : xoá file
```

sự khác nhau : writeFile là dạng bất đồng động, và có callback
```javascript
fs.writeFileSync( file, data, options )

fs.writeFile( file, data, options, callback)
```
** sử dụng middleware 
app.use(express.text());
app.use(express.json())
nhờ middleware, nó mới lấy dữ liệu trong post và gắn vô trong req.body. middleware tạo body trong req
```jsx
const app = express();

app.use(express.text());
app.post("/users", (req, res) => {

  const data = req.body;

  console.log(data);

  fs.writeFileSync("test.txt", data);

  res.send("successfullyyyy");

});
```
Cách sử dụng khác của middle , trong đó next là cho phép mình thực thi tiếp nếu pass và tới middle tiếp theo
![](https://i.imgur.com/lMu4yVa.png)

** 
_array_.some(_function(value, index, arr), this_) : trả về boolean, có hay ko

**
`try {  
  _Block of code to try  
}  
catch(_err_) {  
  _Block of code to handle errors  
}`

**
`  errno: -4058,
  syscall: 'open',
  code: 'ENOENT',
  path: 'test.txt'`
Error: ENOENT: no such file or directory
=> kiểm tra file có tồn tại ko thì dùng : error.code === "ENOENT"

![](https://i.imgur.com/aLLrN7T.png)


