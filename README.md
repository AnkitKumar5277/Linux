Notes : https://docs.google.com/document/d/1y5Tx_IIqDDl_hSvaH25CX6J8Qh_xqfCBH59A2toEBWk/edit?usp=sharing

SQL Notes by Ankit Kumar

Mysql - Me full outerjoin, intersect, except nhi hote hai
Sql - Structured query language used for access and manipulate data in relational database 
database - collection of data, it store and organise data
db diagram - table ka name aur column k name hote h jo dusre table se connected hote h
Sequence of all clause : Select From Where Group by Having Order by
sql application : CRUD create, read, update, delete
Relational db’s: mysql, ms sql server, oracle, postresql
Non relational db’s: mongoDB, cassandra
Structure of sql (RDBMS) : database-> table-> data-> row & coloumn 
user defined function - jo khud se function banate h aur call karte h
Mod - return modulus ot two number - Select mod(11, 4)
Power - nth power - Select power(11, 4)
Sqrt - Select sqrt(144);
Exist - Record h ya nhi wo return karta h Record h to true nhi to false
Intersect - Dono table me common data ko nikalte h
dql / drl - data query language / data retrieval language
Char Variable length fixed hoti h 
Varchar Variable length fixed nhi hoti h
storing data in the database is: Modified, Accessed, Analyzed, Protected, Easily (MAPE
create index - database table me data ko index deta h

Why we use SQL?
It Simplifies work with large datasets, Easy and efficient data management.
SQL is universal and works with most database systems (like PostgreSQL, MySQL,

msexcel - store limited data 
Not automated task like manual graph, chart banana 
No data integrity, Low search filter 

database - store large data 
automated tasks like graph, chart, data integrity, high search filters

Sql commands : 
DDL- create, alter, drop, truncate 
DML- insert, update, delete, select 
DCL- grant, revoke - persmission (dete h aur wapis lete h)
TCL- commit, rollback, save point 
Constraints- primary key, foreign key, unique, not null, check, default
DQL - select

Sql database 
Store data in the form of table, Not change schema (design) of sql
Fixed, static, Slow for low database, Low performance
No sql database
data key value pairs, document me, graph me, wide column me store hota h ye dynamic hota h matlab isme sql ka schema change kar sakte h sabhi db k liye aasan kam karta 

Datatype - define in column, konsi value daalni h column me kis type ka value aana chaiye 
string: char, varchar, etc 
numeric: int, float, bool, etc 
data and time: date, datetime, etc
Ex int, float, double, decimal, char, varchar, text

CREATE TABLE
CREATE TABLE Books (
  id INT PRIMARY KEY,
  name VARCHAR(50),
  age INT,
  city VARCHAR(50)
);

Constraints:
Primary key - unique & not null
Foreign key - links one table to another
Unique - different rows, may be null
Not Null - empty row
Check - apply condition

Constraints
CREATE TABLE table_name ( 
column1 datatype constraint, 
column2 datatype constraint, 
column3 datatype constraint, ... 
);

Comments	/* */ multiline	–, # single line

Find nth record in table: n = jo record nikalna h
Select salary from employee
Order by salary 
desc limit (n-1,1) 

Literal		17 - numeric literal	“Harry” - text literal	12.5 - real literal

QUERYING TABLES : -
Select - database table me data ko retrieve or select karte h
select all - db table me all data ko retrieve or select karte h
Where - Individual data records par condition lagata h where select aur from k baad where me condition lagate h
AS - sql me alias hota h jo column ko temprory naam deta h
order by - data ko ascending, decending order me sort karta h
SELECT * FROM users ORDER BY age ASC;
SELECT * FROM users ORDER BY age DESC;
Limit - limited no. of rows return karta h
SELECT * FROM users LIMIT 5;
Distinct - db table me unique column ko retrieve or select karte h
select distinct country FROM customers;

Filtering Data : -
WHERE col >= n
WHERE col <>	 -> not equal to 
WHERE col != n	 -> not equal to 
WHERE col BETWEEN	-> between

Operator - reserved words hote h jise where clause me use kiya jaata h
arithmetic operator, comparison operator, logical operator-> all, in, between, like, or, not, any, bitwise operator-> &, |

AGGREGATING DATA : -
SELECT COUNT(*) FROM users;
SELECT SUM(salary) FROM employees;
SELECT AVG(age) FROM users;
SELECT MAX(age), MIN(age) FROM users;

Group by - Ye do ya do se jyada column ko group kar deta h aur aggregate function perform karta h 2. Identical data ko arrange karta h 

Having - Ye group par condition lagata h aur condition ka kaam karta h
Group of records par condition lagata h 

Create copy of table 
Data with schema - Create table new_table 
Only schema - Create table new_table like old

Alter table - Table ke structure ko change karta hai jese add new colum, modify old column, Rename column
Add new column - Alter table tablename Newcolumnname; 
Modify old column - Alter Table tablename Modify oldcolumnname  [<newdatatype><size>] 
Rename column - Alter table change oldcolumnname newcolumnname newdatatype;

Drop - delete complete table, can’t rollback		DROP TABLE users;
Truncate - delete Multiple rows, can’t rollback	TRUNCATE TABLE users;
Delete - delete Particular row cant rollback	Delete from table_name where condition;

IN / BETWEEN
SELECT * FROM users WHERE role IN ('admin','tester');
SELECT * FROM users WHERE age BETWEEN 18 AND 30;

Insert
INSERT INTO table_name (coloumn1, column2, column3, columnN) 
VALUES (value1, value2, value4,...valueN);

update 
UPDATE users
SET age = 26
WHERE name = 'Ankit';

function in sql - sql k keyword ya objects hote h jo sql k andar phele se hote h kuch specific task ko complete karne k liye

system defined function / character manipulation function
jo built in function hote h jese rand(), round(), lower(), count(), sum(), max(), etc

string functions - functions ko string k upar perform karte h
upper(), lower() - select upper(first_name) from customers 
length() - select length(first_name) from customers
initcap() - Phele letter capital baad me sab small 
substring() - select substring(first_name,1,3) from customers-> ank return
concat() - select CONCAT(first_name, last_name), first_name, last_name from customers; 
replace() - select replace(first_name,'John','Ankit'),first_name from customers;
trim() - extra spaces ko remove karta h AND, now(), format(), etc.

Join - Me 2 or 2 se jyaada tables ko jodte h row wise agar ek dusre se related column h
types join - inner join, left join, right join, full join
self join - regular join hota h jo khud se join hota h row k column k value ko compare karta h same table me

INNER JOIN - dono tables ka matched record return karta h
SELECT u.name, o.order_id
FROM users u
INNER JOIN orders o 
ON u.id = o.user_id;

LEFT JOIN - return all data from left table and matched data right
SELECT u.name, o.order_id
FROM users u
LEFT JOIN orders o 
ON u.id = o.user_id;

RIGHT JOIN - return all data from right and matched data from left
SELECT u.name, o.order_id
FROM users u
RIGHT JOIN orders o 
ON u.id = o.user_id;

FULL JOIN - return all data from left and right table

Union
2 aur 2 se jyaada tables ko jodte h row wise excluding duplicate value 
Dono SELECT me same number of columns aur rows honi chahiye
Same datatype, Same order
SELECT name FROM users
UNION
SELECT name FROM customers;

union all
do aur do se jyaada row ko combine karte h isme saara data concatenate hota h including duplicate data
SELECT name FROM users
UNION ALL
SELECT name FROM customers;

sub query - inner query or nested query - query k andar query chalate h
SELECT name 
FROM users 
WHERE age > (SELECT AVG(age) FROM users);

In / NOT IN -  select rows if the country is either USA or UK
Multiple or ka kaam karta h ya to ye condition Karo nhi dusri condition Karo

View - View is virtual table hoti, it exist logically not physically 
view always show up to date data, Isme insert, delete, or modify operation ka use nhi hota kyuki ye group function contain nhi karta
Advantages 
1. Insert, primary key, not null phele se included hote h
2. Ye aggregate function, group by, having, distinct clauses define nhi karta 
3. Virtual column cannot be generate

Pattern matching
SELECT * FROM users WHERE name LIKE 'A%';   -- starts with A
SELECT * FROM users WHERE name LIKE '%a';   -- ends with a
SELECT * FROM users WHERE name LIKE '%an%'; -- contains an

ADVANCE :
*Per jis question me aaye - wha Group by ka use karo
Per k baad jo h vahi select aur group by me likha jata h
#8. Find the average customer rating per vehicle type:
SELECT Vehicle_Type, AVG(Customer_Rating) as avg_customer_rating
FROM bookings
GROUP BY Vehicle_Type;

copy customer(cusomer_id, firstname, email, address_id) from 'F:\customer.csv' 
Delimiter ','-> becoz this is csv file 
csv header;-> file ka header

Timestamp - ek datatype h jisme date aur time hota h 
TIME HH:MM:SS 
DATE YYYY-MM-DD 
YEAR YYYY OR YY 
TIMESTAMPTZ contain date, time, and timezone 
timestamp functions / operators: 
SELECT NOW() 
SELECT NOW()
CURDATE()
CURTIME()
SELECT TIMEOFDAY() 

extract function
kisi bhi data ya time k part ko extract karne k liye use hota h
YEAR, QUARTER, MONTH, WEEK, DAY, HOUR, MINUTE, DOW, DO

Minus - Do table h a aur b A-B B ka Sara data a me se hatate h

CASE Statement
SELECT name,
CASE 
  WHEN age >= 18 THEN 'Adult'
  ELSE 'Minor'
END AS status
FROM users;
