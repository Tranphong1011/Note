khởi tạo:
`npm init`
hoặc `npm init -y ` nghĩ là yes all
- framework expressjs cho nodejs
- `node [tên file]` để chạy nodejs runtime
- cài đặt thư viện `npm i nodemon -D` để tự động reset server
vào package.json, mục script add: "start": nodemon index.js
-> npm start 

+ Cài  "prod": "node index.js" trong scripts

để chạy consolelog, chỉ cần send trong postman

key cuối trung trong json của postman ko có dấu ,

lúc gửi dữ liệu lên, server ko hiểu format dữ liệu là gì, cần cài middleware `app.use(express.json())` để chuyển thành json



-->  khi chạy lại server `npm start` thì cho dù xóa sửa gì cũng trở lại ban đầu

- string minify sau khi add 

- cài đặt thư viện mongoose
- trong es6: import, trong es5: require
[dotenv - npm (npmjs.com)](https://www.npmjs.com/package/dotenv)

npm install cors , chú ý nếu front và back ko tương thích local nên phải cài cors


sign in/ log out: server sử dụng thư viện jwt để tạo ra token trả ngược về clients, token này được lưu trong local/sectionstorage hay cookies

encode và decode thì 2 chiều, trong khi đó hash thì 1 chiều



server ------------> ORM -------------------> Database
ORM : mongoose,... cho những sql
sequel: cho những mysql

morgan là 1 middleware để ghi lại những request