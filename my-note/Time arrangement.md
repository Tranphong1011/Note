composer: công cụ quản lý thư viện trong PHP
cd [tên thư muc]: tiến
cd ..: lùi
mở thư mục, bật terminal -> gitbash 
-> composer create-project laravel/laravel example-app 
với example-app là tên app

di chuyển vô thư mục example-app rồi cài ui package cho nó: composer require laravel/ui -> có thể compile sass

npm là công cụ quản lý thư viện JS cho NodeJS: npm install

thiết lập Laravel sử dụng UI ([Bootstrap](https://vinasupport.com/tag/bootstrap/) / [React](https://vinasupport.com/tag/react/) / [Vue](https://vinasupport.com/tag/vue/)) và tạo hệ thống xác thực [Laravel Authentication](https://vinasupport.com/tag/laravel-authentication/) với các trang Login (Đăng nhập), Register (Đăng ký), Logout (Đăng xuất).
++ Chú ý: Bootrap, react và vue đặc trưng cho giao diện của website  ->  php artisan ui bootstrap CÓ NGHĨA LÀ CÀI GIAO DIỆN BOOTSTRAP  CHO WEBSITE -> -php artisan ui bootstrap --auth SẼ GENERATE AUTH BẰNG BOOTSTRAP UI

- cài php artisan ui vue --auth, 
- cài npm install && npm run dev (bắc buộc phải chạy , kết hợp cùng với php artisan serve) [chỉ cần npn run dev là đủ rồi]



![](https://i.imgur.com/XkIZ0or.png)
có thể dùng localhost:5173

admin
email+password: admin@gmail.com

doctor
email+password: doctor@gmail.com
![](https://i.imgur.com/8ijw7wi.png)
![](https://i.imgur.com/UpAOl2G.png)

```
Route::get('/dashboard', function () {

    return view('dashboard');

});
```
nếu return view thì sẽ đọc file dashboard đó, nếu return "hello" thì trả về chữ hello thay vì đọc nội dung trong dashboard. Tuy nhiên chú ý ko đc get file home, vì nó sẽ ko trả về bất kì thứ gì ngoại trừ form login

tải 1 template bất kì của bootrap, đặt folder trong mục  public

`{{asset('')}}`chỉ đơn giản là cho phép bạn liên kết đến một nội dung trong thư mục công cộng của bạn - chẳng hạn `css/main.css`.

tạo folder admin trong resources -> views, tạo folder layout trong admin, tạo 5 cái blade.php, copy từng code của dashboard qua. 

tạo 1 test.blade.php trong layouts của views, include toàn bộ 5 cái blade.php trên vào file test này 

** Cách sử dụng @yield và @extend
- @extends(tên file muốn extend),  @section(tên section muốn extend). @section phải có @endsection
- Khác với @include, nó sẽ include toàn bộ file
- Trích nguồn extend là . thay vì /
![](https://i.imgur.com/OSgdJa3.png)
![](https://i.imgur.com/wI4Y5lE.png)

tạo 1 file model và migration để tương tác với csdl
php arisan make:model Role--migration
*hoặc* php arisan make:model Role -m
--> sẽ thấy có một file Role.php

php artisan migrate: migrate dữ liệu

Những lưu ý khi migrate data: vào file .env chỉnh lại 1 số thông tin: ![](https://i.imgur.com/pI5pfOl.png)
reload serve. Đặt lại mật khẩu cho phpmyadmin, đồng thời vào file config.inc trong WAMP\apps\phpmyadmin5.2.0 và đổi mật khẩu

gặp lỗi :# [Laravel Migration Error: Syntax error or access violation: 1071 Specified key was too long; max key length is 767 bytes]
![](https://i.imgur.com/xDDfeyi.png)


** chú ý : php artisan migrate:rollback  >< php artisan migrate
- php artisan migrate: chạy phương thức up()
- php artisan migrate:rollback chạy phương thức down(). Nghĩa là khi tua ngược lại quá trình làm thì `function down() ` mới được thực thi
--> cần phải viết function `down()` là những gì đảo ngược của `up()`
Ví dụ nếu `up()` là $table->string('gender') thì `down()` phải là ` $table->dropColumn('gender');`
nếu 
`$table->dropColumn('comment_count');`
thì `$table->integer('comment_count');`

Lưu ý, kể từ laravel 8, có thư mục models trong app 
Tạo seeders: php artisan db:seed

