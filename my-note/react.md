Press F12  to consolelog
-là thư viện 
`npx create-react-app [tên]` : tạo 1 react application
`npx create-react-app .` : tạo react ngay trên file đó

`cd my-react-app,` `npm start` : run react application
  Local:            http://localhost:3000        
  On Your Network:  http://172.27.37.83:3000  

congifure  .gitignore: chỉnh file nào cần đẩy lên git hub

trong file index.js, lệnh createRoot để tạo document ảo

` npm run build` để tối ưu hóa thư mục build
 For environments using [Node](https://nodejs.org/), the easiest way to handle this would be to install [serve](https://github.com/vercel/serve) and let it handle the rest:
`	  npm install -g serve`
`	  serve -s build`

-- _Node_.js _là_ một JavaScript runtime được build dựa trên engine JavaScript V8 của Chrome

--- **NPM là gì?** – NMP là viết tắt của Node package manager là một công cụ tạo và quản lý các thư viện lập trình Javascript cho [Node.js](https://nodejs.org/). Trong cộng đồng Javascript, các lập trình viên chia sẻ hàng trăm nghìn các thư viện với các đoạn code đã thực hiện sẵn một chức năng nào đó. Nó giúp cho các dự án mới tránh phải viết lại các thành phần cơ bản, các thư viện lập trình hay thậm chí cả các [framework](https://topdev.vn/blog/framework-la-gi/).

props : thuộc tính,đặc trong bracket {} để thực thi code JS thay vì HTML

index.css: edit toàn bộ file css
snippet: rfce, ffc
![](https://i.imgur.com/qtZp1Sw.png)


trong thẻ div, có thể text thường, hoặc [{asdwq,asdqwdqw,ádsad}]
phải truyền key=[product.id] để tránh unique trong console


-- file app.js để tạo function, file index.js là để thực thi function đó, app.css để css function riêng của app.js. Nhưng đối với index.js thì css chung cho tất cả

-- width + margin : auto sẽ set container ở center, cố định width kể  cả khi resize browser (nghĩa là có thể bị mất đi 1 vài nội dung => hiển thị scroll)
Trong khi đó maxwidth + margin: auto sẽ flexible container khi resize browser

render: 
```
const root = createRoot(container);
root.render(element);
```
![](https://i.imgur.com/494xu6h.png)

![](https://i.imgur.com/p1gpCj1.png)

<script>
class Car {
  constructor(name, hollow ) {
    this.brand = name;
    this.price = hollow;
    this.shape = 'Rectangle'
  }
  present() {
    return 'I have a ' + this.brand;
  }
}
const mycar = new Car("Ford", 9000);
// document.write(mycar.brand);
console.log(mycar)
</script> 
>> Hàm constructor tự khởi tạo 
>> mycar ={ brand: name, price: hollow, shape: 'Rectangle', present() : null}
>> Khi gọi object
>> mycar ={ brand: "Ford",price: hollow, shape: 'Rectangle', present(): ...}

The **super** keyword is used to access properties on an object literal or class's [[Prototype]], or invoke a superclass's constructor.
The `super` keyword is used to call the constructor of its parent class to access the parent's properties and methods.

`super(arguments)`;  // calls the parent constructor (only inside the constructor)  
`super.parentMethod(arguments)`;  // calls a parent method

```jsx
class Car {
  constructor(name) {
    this.brand = name;
  }

  present() {
    return 'I have a ' + this.brand;
  }
}

class Model extends Car {
  constructor(name, mod) {
    super(name);
    this.model = mod;
  }  
  show() {
      return this.present() + ', it is a ' + this.model
  }
}
const mycar = new Model("Ford", "Mustang");
mycar.show();
```

++ Cách gọi function :
  
regular function
`hello = function() {return "hi"}`
arrow function
`hello = () => "hi" `
````jsx
hello = val => "Hello " + val; (gán biến, nếu 1 biến thì bỏ () )
````

++ map() : để function() trong map
```jsx
const myArray = ['apple', 'banana', 'orange'];

const myList = myArray.map((item) => <p>{item}</p>)
```


++ destructuring array:
```jsx
const vehicles = ['mustang', 'f-150', 'expedition'];

const [car, truck, suv] = vehicles;
```
const [car, ,suv] = vehicles nếu  bỏ truck 

++ destructuring object: (nested)
```jsx
const vehicleOne = {
  brand: 'Ford',
  model: 'Mustang',
  type: 'car',
  year: 2021, 
  color: 'red',
  registration: {
    city: 'Houston',
    state: 'Texas',
    country: 'USA'
  }
}

myVehicle(vehicleOne)

function myVehicle({ model, registration: { state } }) {
  const message = 'My ' + model + ' is registered in ' + state + '.';
}
```

++ spread operator: 
<script>
const numbersOne = [1, 2, 3];
const numbersTwo = [4, 5, 6];
const numbersCombined = [...numbersOne, ...numbersTwo];

document.write(numbersCombined);
</script>
return 1,2,3,4,5,6

```jsx
const numbers = [1, 2, 3, 4, 5, 6];

const [one, two, ...rest] = numbers;
```

```jsx
const myVehicle = {
  brand: 'Ford',
  model: 'Mustang',
  color: 'red'
}

const updateMyVehicle = {
  type: 'car',
  year: 2021, 
  color: 'yellow'
}

const myUpdatedVehicle = {...myVehicle, ...updateMyVehicle}
```
![](https://i.imgur.com/B4uscu3.png)


++ Named Exports: export đc nhiều 
```jsx
export const name = "Jesse"
export const age = 40
```

or
```jsx
const name = "Jesse"
const age = 40

export { name, age }
```

++ Default Exports : chỉ export 1 cái
```jsx
const message = () => {
  const name = "Jesse";
  const age = 40;
  return name + ' is ' + age + 'years old.';
};

export default message;
```

++ import: cả variable or function. import multi: {a,b,c}
++ ternary operator: 
```jsx
authenticated ? renderApp() : renderLogin();
```
|| : cả 2 đều true: true đầu ------ cả 2 đều false: false cuối
&&: cả 2 đều true: true cuối ------cả 2 đều false: false đầu

++ render function:
`ReactDOM.render(cái gì, ở đâu)`
ví dụ: 
`ReactDOM.render(myelement, document.getElementById('root'));`

-> display the specified HTML code inside the specified HTML element.
render trong file index.html, trong folder public


++ Sự khác nhau giữa JS và JSX: JS còn thêm appendChild
JSX:
`const myElement = <h1>I Love JSX!</h1>;`


JS: lệnh creatElement gồm 3 có arg: tag-name, expression in js format, tức là đặt tên class là gì, content1, content2, ...
`const myElement = React.createElement('h1', {}, 'I do not use JSX!');`


Đổi code từ js sang jsx
**https://babeljs.io/repl#?browsers=defaults%2C%20not%20ie%2011%2C%20not%20ie_mob%2011&build=&builtIns=false&corejs=3.21&spec=false&loose=false&code_lz=Q&debug=false&forceAllTransforms=false&shippedProposals=false&circleciRepo=&evaluate=false&fileSize=false&timeTravel=false&sourceType=module&lineWrap=true&presets=env%2Creact%2Cstage-2&prettier=false&targets=&version=7.19.3&externalPlugins=&assumptions=%7B%7D**

++ JSX: 
write expressions inside curly braces `{ }`
multiple lines, put the HTML inside parentheses  `()`
buộc phải có parent element : `<div>`
use a "fragment" to wrap multiple lines. `<></>`. viết gọn từ <React.Fragment></React.Fragment>
Close empty elements with `/>`
put the `if` statements outside of the JSX:
thẻ input phải nằm trong thẻ label
```jsx
const x = 5;
let text = "Goodbye";
if (x < 10) {
  text = "Hello";
}

const myElement = <h1>{text}</h1>;
```
 hoặc dùng ternary"
 ```jsx
const x = 5;

const myElement = <h1>{(x) < 10 ? "Hello" : "Goodbye"}</h1>;
```
++ Tạo component: must include the `extends React.Component` statement, `render()` method, this method returns HTML---------------------- hoặc dùng function
```jsx
class Car extends React.Component {
  render() {
    return <h2>Hi, I am a Car!</h2>;
  }
}
```
hoặc  
```jsx
function Car() {
  return <h2>Hi, I am a Car!</h2>;
}
```
++ render component: 
```jsx
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Car />);
```

++ state: là 1 object, nơi lưu giữ component properties
```jsx
class Car extends React.Component {
  constructor() {
    super();
    this.state = {color: "red"};
  }
  render() {
    return <h2>I am a {this.state.color} Car!</h2>;
  }
}
```

++ props là : là tham số hàm , 1 dạng object
```jsx
function Car(props) {
  return <h2>I am a { props.brand }!</h2>;
}

const myElement = <Car brand="Ford" />;
```
++ `this.state`: khởi tạo object
Ví dụ: 
```jsx
this.state = {
      brand: "Ford",
      model: "Mustang",
      color: "red",
      year: 1964
    };
```
++ `{this.state.propertyname}` : chọc vào thuộc tính 

++ `this.setState()` thay đổi giá trị của state object
```jsx
class Car extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      brand: "Ford",
      model: "Mustang",
      color: "red",
      year: 1964
    };
  }
  changeColor = () => {
    this.setState({color: "blue"});
  }
  render() {
    return (
      <div>
        <h1>My {this.state.brand}</h1>
        <p>
          It is a {this.state.color}
          {this.state.model}
          from {this.state.year}.
        </p>
        <button
          type="button"
          onClick={this.changeColor}
        >Change color</button>
      </div>
    );
  }
}
```
super(props) đóng vai trò initiate parent'constructor method và cho phép các component thừa hưởng method đó từ parent
++ Vòng đời components:

- *mounting : đặt ele vào DOM, theo trình tự sau:*
1.  `constructor()`
2.  `getDerivedStateFromProps()` luôn được gọi trước render
3.  `render() ` bắt buộc phải có
4.  `componentDidMount()` luôn được gọi sau khi render


``getDerivedStateFromProps()`` set the `state` object based on the initial `props`
```jsx
class Header extends React.Component {
  constructor(props) {
    super(props);
    this.state = {favoritecolor: "red"};
  }
  static getDerivedStateFromProps(props, state) {
    return {favoritecolor: props.favcol };
  }
  render() {
    return (
      <h1>My Favorite Color is {this.state.favoritecolor}</h1>
    );
  }
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Header favcol="yellow"/>);
```

``componentDidMount()``
Phương thức componentDidMount được thực thi sau khi render đầu tiên được sinh ra ở phía client. Thông thường những request dạng AJAX, DOM hoặc cập nhật state chúng ta để trong phương thức này
(sau 1s red đổi sang yellow)
```jsx
class Header extends React.Component {
  constructor(props) {
    super(props);
    this.state = {favoritecolor: "red"};
  }
  componentDidMount() {
    setTimeout(() => {
      this.setState({favoritecolor: "yellow"})
    }, 1000)
  }
  render() {
    return (
      <h1>My Favorite Color is {this.state.favoritecolor}</h1>
    );
  }
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Header />);
```

+ update:
1.  `getDerivedStateFromProps()`
2.  `shouldComponentUpdate()` : (có hay ko react tiếp tục render) mặc định true, nếu false thì return false
3.  `render()`
4.  `getSnapshotBeforeUpdate()` phải đi kèm với componentDidUpdate
5.  `componentDidUpdate()`


![](https://i.imgur.com/ex3olLf.png)




































++ useEffect(): để perform side effects : fetching data, update DOM, timers
`useEffect(<function>, <dependency>)`

















vanilla: JS thuần 
`npm create vite@latest` để tạo folder vite-project
`  cd vite-project`
 ` npm install`
`  npm run dev`

`npm run build:` nếu cài react theo cách truyền thống sẽ tạo file build. trong khi đó nếu cài react theo vite thì sẽ tạo file dist

tên 1 hàm luôn viết hoa chữ cái đầu

import {usestate} from react, usestate là 1 hook cơ bản của react
cấu trúc cơ bản của usestate: const [state, setState] = useState(initialStateValue)
Trong đó:

-   **state**: định nghĩa tên của state nó có thể là đơn giá trị hoặc object,.. (là tham số của useState)
-   **setState**: định nghĩa tên function dùng cho việc update state (là tham số của useState)
-   **initialStateValue**: là giá trị ban đầu của state.

setCounter: set lại counter, và render lại Component
check state: vào components trong thanh công cụ chứa console

cài thư viện axios
chú ý cái dependancy của useEfffect()
https://www.devbridge.com/articles/dependency-injection-in-javascript/

https://dummyjson.com/docs/products

**react router:**

hướng dẫn cài đặt: 
https://reactrouter.com/en/main/start/tutorial
````sh
npm install react-router-dom localforage match-sorter sort-by
npm run dev
````
Copy/Paste the tutorial CSS found here into src/index.css
Copy/Paste the tutorial data module found here into src/contacts.js

Delete unused files in src/ so all you have left are these: src 
├── contacts.js ├── index.css └── main.jsx

.
.
.
mặc định thẻ a sẽ gửi đến server và lấy lại file, do đó tránh sự reload nên thay thế <a> bằng  e.preventDefault() hoặc dùng link to = 


cài form: npm install @tailwindcss/forms
cài axios: npm i axios

react hook form