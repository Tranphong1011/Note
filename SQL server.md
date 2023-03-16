
stv.phong
phong@123
192.168.1.4

@ là biến do mình đặt ra, @@ là biến của hệ thống

Cách sử dụng WITH ... AS![[Pasted image 20230203094211.png]]
![[Pasted image 20230203094242.png]]
tạo bảng riêng cte_quantity, so đó thực thi cái select dưới
Tương đương: ![[Pasted image 20230203094342.png]]
Cấu trúc: 
![[Pasted image 20230203094618.png]]

Kí tự N'': i used prefix N , It got inserted as it is ( **Wāhi** ) , when i tried without prefix N , the inserted value is ( **Wahi** )

![[Pasted image 20230203095907.png]]

Cách sử dụng substring
![[Pasted image 20230203103443.png]]
![[Pasted image 20230203103508.png]]

Ascii:
![[Pasted image 20230203104425.png]]

Hàm ngược của Ascii:
![[Pasted image 20230203104656.png]]

https://www.w3schools.com/sql/func_sqlserver_char.asp

**DML là** viết tắt của Ngôn ngữ Thao tác Dữ liệu ( Data Manipulation Language): INSERT, UPDATE và DELETE **là** các câu lệnh **DML**. 
**DDL là** viết tắt của Ngôn ngữ Định nghĩa Dữ liệu (Data Definition Language): CREATE, ALTER, DROP, RENAME **là** các câu lệnh **DDL**.

**DML triggers là các triggers sẽ được tự động thực thi khi các có sự kiện thao tác dữ liệu xảy tương ứng liên quan thao tác dữ liệu trên table hoặc view mà nó gắn kết**.
DDL trigger sẽ kích hoạt khi những sự kiện bị thay đổi cấu trúc như việc tạo, sửa đổi, bỏ bảng. Cũng có thể xuất hiện trong những sự kiện liên quan tới server (sửa đổi bảo mật, cập nhật thống kê).

Cách sử dụng With execution as:
![[Pasted image 20230203110243.png]]
https://www.mssqltips.com/sqlservertip/1227/sql-server-execute-as/

Sử dụng thêm lệnh SET NOCOUNT ON trong các stored procedures

Thông thường T-SQL sẽ thông báo tổng số các bản ghi bị tác động khi thực thi một lệnh SQL. Tuy nhiên, nếu chúng ta sử dụng lệnh SET NOCOUNT ON ở đầu các stored procedures thì hệ thống không trả về thông báo nữa. Việc này tiết kiệm lưu lượng mạng chút xíu.

** Cách cách để tối ưu query:
https://technotransfer.wordpress.com/2013/06/28/toi-uu-hoa-cau-lenh-sql/

database_principal_id
![[Pasted image 20230203112950.png]]

is_member : Indicates whether the current user is a member of the specified Microsoft Windows group or SQL Server database role.
```
IS_MEMBER ( { 'group' | 'role' } )
```
Ex: `select @IsDbo = IS_MEMBER(N'db_owner');`
giá trị trả về dưới dạng 0,1 và null\

revert: Switches the execution context back to the caller of the last EXECUTE AS statement.
Tức là chỉ khi `execute as caller`:
```
CREATE PROCEDURE dbo.usp_myproc   
  WITH EXECUTE AS CALLER  
AS   
    SELECT SUSER_NAME(), USER_NAME();  
    EXECUTE AS USER = 'guest';  
    SELECT SUSER_NAME(), USER_NAME();  
    REVERT;  
    SELECT SUSER_NAME(), USER_NAME();  
GO
```

sp_OACreate: tạo đối tượng OLE
`sp_OACreate { progid | clsid }`
Kiểu progid có dạng:  **'**_OLEComponent_**.**_Object_**'**
Ví dụ:
`EXECUTE @OLEResult = sp_OACreate 'Scripting.FileSystemObject',`
->
OLEComponent is the component name of the OLE Automation server, and Object is the name of the OLE object. The specified OLE object must be valid and must support the IDispatch interface.

**Return là int:**

Specifies the execution context in which the newly created OLE object runs. If specified, this value must be one of the following:

1 = In-process (.dll) OLE server only.
4 = Local (.exe) OLE server only.
5 = Both in-process and local OLE server allowed

IN/OUT trong SQL server: 
IN Parameters - parameters that pass data TO a stored Procedure
OUT Parameters - parameters that are used to RETURN data FROM a stored procedure
Ví dụ:
![[Pasted image 20230203133400.png]]

hàm convert:
`CONVERT(data_type(length), expression, style)`
Ví dụ: 
`SELECT CONVERT(varchar, '2017-08-25', 101);`
style : là format để chuyển đổi giữa 2 data. Tham khảo bảng style:  https://www.w3schools.com/sql/func_sqlserver_convert.asp

hàm getdate(): trả về ngày tháng hiện tại dưới dạng: 
`'YYYY-MM-DD hh:mm:ss.mmm' format.`
Ví dụ: 2023-02-03 07:02:46.557

![[Pasted image 20230203141012.png]]
carriage return: về đầu dòng
char(13) + char(10) : xuống hàng 
![[Pasted image 20230203142458.png]]

Tạo procedure: ![[Pasted image 20230206093228.png]]
Cách thức chạy:
![[Pasted image 20230206093719.png]]

Cách sử dụng WITH (NOLOCK)
```
-- run in query window 1
BEGIN TRAN
UPDATE Person.Contact SET Suffix = 'B' WHERE ContactID < 20
-- ROLLBACK or COMMIT
```

```
-- run in query window 2 (ko có nolock)
SELECT * FROM Person.Contact WHERE ContactID < 20
```

```
-- run in query window 2 (có nolock)
SELECT * FROM Person.Contact WITH (NOLOCK) WHERE ContactID < 20
```
Khi transaction đang chạy nhưng chưa commit hoặc rollback, thì select sẽ suspending (đang đợi transaction thực thi xong). 
Tuy nhiên, với nolock thì lệnh select thực thi "bất chấp" -> dẫn đến kết quả ko đồng nhất

Kiểu dữ liệu Varchar trong SQL server lưu trữ dữ liệu chuỗi có độ dài thay đổi

RTRIM(String), LTRIM(String) : strim bên phải, trái

ISNULL(_expression_, _value_), nếu expression trả về NULL thì hàm ISNULL trả về value, nếu expression ko trả về NULL thì hàm ISNULL trả về kết của của expression

The COALESCE() function returns the first non-null value in a list.
```
SELECT COALESCE(NULL, NULL, NULL, 'W3Schools.com', NULL, 'Example.com');
```
-> Trả về: `W3Schools.com`

Cấu trúc Exist và Not exist:
```
SELECT SupplierName
FROM Suppliers
WHERE not EXISTS (SELECT ProductName FROM Products WHERE Products.SupplierID = Suppliers.supplierID AND Price < 20);
```
sẽ tương đương với
```
SELECT Suppliers.SupplierName
FROM Suppliers,Products 
WHERE Products.SupplierID = Suppliers.supplierID AND Price < 20;
```

Not exist sẽ tương ứng với việc Price >=20

Lưu ý: kiểu dữ liệu datetime có thể cộng int:
```
CONVERT( DATETIME, CONVERT( VARCHAR, GETDATE() - 1, 112 ), 112 ) + 0.99999999
```
tức là `2023-02-05 00:00:00.000 + 0.99999999 =  2023-02-06 00:00:00.000`

Tạo bảng mới và đặt tên bảng mới:
`SELECT` `Employee_id, First_name, Salary, Department_id`
`INTO` `EMP`
`FROM` `EMPLOYEES`
`WHERE` `Department_id` `IN``(70, 90)`
-> bảng mới lúc này có tên là EMP

**MERGE** là lệnh dùng để sửa đổi (update/insert/delete) dữ liệu của 1 bảng dựa vào kết quà so sánh với 1 bảng nào đó
Merge trong MySQL có tổ hợp update và insert:
cú pháp:
![[Pasted image 20230206145601.png]]

->
![[Pasted image 20230206145529.png]]

Merge trong SQL Server:
![[Pasted image 20230206150212.png]]
![[Pasted image 20230206150153.png]]

So với UNION thì đối với UNION ALL dữ liệu ko cho phép duplicate
```
SELECT _column_name(s)_ FROM _table1_  
UNION  / UNION ALL
SELECT _column_name(s)_ FROM _table2_;
```
Điều kiện Union:
```
-   Every `SELECT` statement within `UNION` must have the same number of columns
-   The columns must also have similar data types
-   The columns in every `SELECT` statement must also be in the same order
```

Cách sử dụng Pivot và Unpivot
![[Pasted image 20230206153120.png]]
![[Pasted image 20230206153144.png]]

Cách sử dụng cast:
`SELECT CAST(25.65 AS int);`

Cách lấy năm:
```
SELECT YEAR('2017/08/25') AS Year;
```

Xem duration của lệnh query
![[Pasted image 20230207120522.png]]

cách phân chia partition:
![[Pasted image 20230207153248.png]]
![[Pasted image 20230207153322.png]]
Phân vùng không gian lưu trữ
![[Pasted image 20230207153619.png]]

![[Pasted image 20230207153714.png]]
![[Pasted image 20230207154013.png]]
Các bước tạo partition table:
https://www.sqlservertutorial.net/sql-server-administration/sql-server-table-partitioning/

case when:
![[Pasted image 20230208101730.png]]
![[Pasted image 20230208101750.png]]

nested case when:
![[Pasted image 20230208101913.png]]
https://help.hcltechsw.com/commerce/7.0.0/com.ibm.commerce.developer.soa.doc/refs/rsdperformanceworkspaces.html

Cách sử dụng Cursor:
https://xuanthulab.net/su-dung-cursor-trong-sql-server.html
In practice, you will rarely use the cursor to process a result set in a row-by-row manner.

Group by theo 2 cột subject và year :
![[Pasted image 20230209113851.png]]
kết quả: ![[Pasted image 20230209113922.png]]

Cách tạo clustered / noncluster index:
![[Pasted image 20230209115925.png]]

![[Pasted image 20230209135747.png]]
Ví dụ
`CREATE NONCLUSTERED INDEX IX_GRPBY ON dbo.Votes ( BountyAmount, UserId );`

index loại bỏ những giá trị null của cột BountyAmount(nên dùng theo cách này để tối ưu hóa):
```
CREATE NONCLUSTERED INDEX IX_GRPBY
ON dbo.Votes ( BountyAmount, UserId )
WHERE BountyAmount IS NOT NULL
WITH ( DROP_EXISTING = ON );
```

![[Pasted image 20230209131627.png]]

Xóa index:
![[Pasted image 20230209120202.png]]
Lưu ý: Mỗi lần có chỉnh sửa trong database, thì các index phải được update . This is why indexes are typically applied to databases in data warehouses that get new data updated on a scheduled basis(off-peak hours) and not production databases which might be receiving new writes all the time.
--Adding an index will always mean storing more data ---Adding an index will increase how long it takes your database to fully update after a write operation.
https://dataschool.com/sql-optimization/how-indexing-works/
https://comdy.vn/sql-server/index-trong-sql-server/

Optimize:
There are many ways to optimize your query. check the BELOW mentioned things which are very common and easy to impliment.

Do’s

1.  Use WITH clauses.
2.  Create VIEWS for huge volume tables.
3.  Use HINTS.
4.  Use the JOIN CONDITIONS properly.

Don'ts

1.  Define SELECT FIELDS instead of select *.
2.  Use WILDCARDS only when they are necessary.
3.  Try to avoid using DISTINCT.

https://noted.lol/5-sources-for-developers-to-look-for-jobs/
[phuongvd@dnkinno.com](mailto:phuongvd@dnkinno.com) / phuong123
https://dnkinno.udemy.com/organization/home/

**The DELETE command is used to delete particular records from a table.** **The TRUNCATE command is used to delete the complete data from the table**

Mỗi procedure là 1 transaction

Cách tạo trigger: 
tạo bảng LotteProduct.dbo.Test, thêm các element vào
tạo bảng tạm LotteProduct.dbo.Test_BU để lưu các log

chuột phải lên database LotteProduct, chọn new sql, sau đó:
```sql
	create trigger Test_trigger on LotteProduct.dbo.Test
	after INSERT , DELETE 
	as
	begin
	set nocount on;
	INSERT into LotteProduct.dbo.Test_BU (
	
	EmployeeID,
	LastName,
	FirstName,
	updated_at,
	operation)
	select EmployeeID, LastName, FirstName, GETDATE(), 'INS' from inserted I
	union all
	select EmployeeID,LastName, FirstName, GETDATE(), 'DEL' from deleted D
	end
	
```
![[Pasted image 20230214145037.png]]
![[Pasted image 20230214150126.png]]
![[Pasted image 20230214150301.png]]
cách sử dụng cả 3 lệnh after update, insert , delete:
```sql
-- Alter the table to capture updates and add operation
ALTER TABLE ChangeTrackingHistory
ADD Operation VARCHAR(10);
GO
-- Install the trigger to capture updates
ALTER TRIGGER dbo.TRG_Users_ChangeTracking
ON dbo.Users
AFTER INSERT, UPDATE, DELETE
AS
BEGIN
    SET NOCOUNT ON;
    WITH cte1 AS(
                SELECT
                    d.UserID AS DeletedID
                    ,i.UserID AS InsertedID
                FROM Deleted d
                FULL OUTER HASH JOIN Inserted i ON i.UserID = d.UserID
            ),
            cte2 AS(
                SELECT
                    COALESCE(InsertedID,DeletedID) AS UserID
                    ,CASE
      WHEN InsertedID IS NOT NULL AND DeletedID IS NOT NULL THEN 'Update'
      WHEN InsertedID IS NOT NULL AND DeletedID IS NULL THEN 'Insert'
      WHEN InsertedID IS NULL AND DeletedID IS NOT NULL THEN 'Delete'
                        ELSE ''
                    END AS Operation
                FROM cte1
            )
    INSERT INTO ChangeTrackingHistory(UserID,Operation)
    SELECT UserID,Operation
    FROM cte2;
END
GO
```

```sql
USE AdventureWorks2012;  
GO  
IF EXISTS (SELECT name FROM sys.objects  
      WHERE name = 'reminder' AND type = 'TR')  
   DROP TRIGGER Person.reminder;  
GO  
CREATE TRIGGER reminder  
ON Person.Address  
AFTER UPDATE   
AS   
IF ( UPDATE (StateProvinceID) OR UPDATE (PostalCode) )  
BEGIN  
RAISERROR (50009, 16, 10)  
END;  
GO  
-- Test the trigger.  
UPDATE Person.Address  
SET PostalCode = 99999  
WHERE PostalCode = '12345';  
GO
```