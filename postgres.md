
psql - terminal
![[Pasted image 20221130111217.png]]
password for superuser: phong

-- lệnh tạo database mới: create database + [tên db muốn tạo]
list db: `\l`

-- lệnh tạo user mới: create user [tên user muốn tạo] with encrypted password '[mật khẩu]'
(Lưu ý là mật khẩu có dấu '   ')
list user:  `\du`
User mới tạo: phong
Mật khẩu mới tạo: 093528


give priviledges: từ superuser(phong) sang user(phong)
grant all privileges on database [tên database trong superuser - postgres] to [tên user cần được grant]
![[Pasted image 20221214152312.png]]

![[Pasted image 20221214152242.png]]
đổi vị trí bd đang đứng là postgres sang mydtb

Lệnh tạo table mới trong database
![[Pasted image 20221214152505.png]]


Khi tạo mới database, cả 2 user đều cùng có database, đồng nghĩa với việc cả 2 user này có cùng container chứ các db.
Trong mỗi db có nhiều schema, trong mõi schema có nhiều table
https://tableplus.com/blog/2018/04/postgresql-how-to-grant-access-to-users.html