```
项目七: 各部门工资最高的员工（难度：中等）
创建Employee 表，包含所有员工信息，每个员工有其对应的 Id, salary 和 department Id。
+----+-------+--------+--------------+
| Id | Name  | Salary | DepartmentId |
+----+-------+--------+--------------+
| 1  | Joe   | 70000  | 1            |
| 2  | Henry | 80000  | 2            |
| 3  | Sam   | 60000  | 2            |
| 4  | Max   | 90000  | 1            |
+----+-------+--------+--------------+
创建Department 表，包含公司所有部门的信息。
+----+----------+
| Id | Name     |
+----+----------+
| 1  | IT       |
| 2  | Sales    |
+----+----------+
编写一个 SQL 查询，找出每个部门工资最高的员工。例如，根据上述给定的表格，Max 在 IT 部门有最高工资，Henry 在 Sales 部门有最高工资。
+------------+----------+--------+
| Department | Employee | Salary |
+------------+----------+--------+
| IT         | Max      | 90000  |
| Sales      | Henry    | 80000  |
+------------+----------+--------+


项目八: 换座位（难度：中等）
小美是一所中学的信息科技老师，她有一张 seat 座位表，平时用来储存学生名字和与他们相对应的座位 id。
其中纵列的 id 是连续递增的
小美想改变相邻俩学生的座位。
你能不能帮她写一个 SQL query 来输出小美想要的结果呢？
 请创建如下所示seat表：
示例：
+---------+---------+
|    id   | student |
+---------+---------+
|    1    | Abbot   |
|    2    | Doris   |
|    3    | Emerson |
|    4    | Green   |
|    5    | Jeames  |
+---------+---------+
假如数据输入的是上表，则输出结果如下：
+---------+---------+
|    id   | student |
+---------+---------+8
|    1    | Doris   |
|    2    | Abbot  |
|    3    | Green   |
|    4    | Emerson |
|    5    | Jeames  |
+---------+---------+
注意：
如果学生人数是奇数，则不需要改变最后一个同学的座位。


项目九:  分数排名（难度：中等）
编写一个 SQL 查询来实现分数排名。如果两个分数相同，则两个分数排名（Rank）相同。请注意，平分后的下一个名次应该是下一个连续的整数值。换句话说，名次之间不应该有“间隔”。
创建以下score表：
+----+-------+
| Id | Score |
+----+-------+
| 1  | 3.50  |
| 2  | 3.65  |
| 3  | 4.00  |
| 4  | 3.85  |
| 5  | 4.00  |
| 6  | 3.65  |
+----+-------+
例如，根据上述给定的 Scores 表，你的查询应该返回（按分数从高到低排列）：
+-------+------+
| Score | Rank |
+-------+------+
| 4.00  | 1    |
| 4.00  | 1    |
| 3.85  | 2    |
| 3.65  | 3    |
| 3.65  | 3    |
| 3.50  | 4    |
+-------+------+

项目十：行程和用户（难度：困难）
Trips 表中存所有出租车的行程信息。每段行程有唯一键 Id，Client_Id 和 Driver_Id 是 Users 表中 Users_Id 的外键。Status 是枚举类型，枚举成员为 (‘completed’, ‘cancelled_by_driver’, ‘cancelled_by_client’)。
+----+-----------+-----------+---------+--------------------+----------+
| Id | Client_Id | Driver_Id | City_Id |        Status      |Request_at|
+----+-----------+-----------+---------+--------------------+----------+
| 1  |     1     |    10     |    1    |     completed      |2013-10-01|
| 2  |     2     |    11     |    1    | cancelled_by_driver|2013-10-01|
| 3  |     3     |    12     |    6    |     completed      |2013-10-01|
| 4  |     4     |    13     |    6    | cancelled_by_client|2013-10-01|
| 5  |     1     |    10     |    1    |     completed      |2013-10-02|
| 6  |     2     |    11     |    6    |     completed      |2013-10-02|
| 7  |     3     |    12     |    6    |     completed      |2013-10-02|
| 8  |     2     |    12     |    12   |     completed      |2013-10-03|
| 9  |     3     |    10     |    12   |     completed      |2013-10-03| 
| 10 |     4     |    13     |    12   | cancelled_by_driver|2013-10-03|
+----+-----------+-----------+---------+--------------------+----------+
Users 表存所有用户。每个用户有唯一键 Users_Id。Banned 表示这个用户是否被禁止，Role 则是一个表示（‘client’, ‘driver’, ‘partner’）的枚举类型。
+----------+--------+--------+
| Users_Id | Banned |  Role  |
+----------+--------+--------+
|    1     |   No   | client |
|    2     |   Yes  | client |
|    3     |   No   | client |
|    4     |   No   | client |
|    10    |   No   | driver |
|    11    |   No   | driver |
|    12    |   No   | driver |
|    13    |   No   | driver |
+----------+--------+--------+
写一段 SQL 语句查出 2013年10月1日 至 2013年10月3日 期间非禁止用户的取消率。基于上表，你的 SQL 语句应返回如下结果，取消率（Cancellation Rate）保留两位小数。
+------------+-------------------+
|     Day    | Cancellation Rate |
+------------+-------------------+
| 2013-10-01 |       0.33        |
| 2013-10-02 |       0.00        |
| 2013-10-03 |       0.50        |
+------------+-------------------+

项目十一：各部门前3高工资的员工（难度：中等）
将项目7中的employee表清空，重新插入以下数据（其实是多插入5,6两行）：
+----+-------+--------+--------------+
| Id | Name  | Salary | DepartmentId |
+----+-------+--------+--------------+
| 1  | Joe   | 70000  | 1            |
| 2  | Henry | 80000  | 2            |
| 3  | Sam   | 60000  | 2            |
| 4  | Max   | 90000  | 1            |
| 5  | Janet | 69000  | 1            |
| 6  | Randy | 85000  | 1            |
+----+-------+--------+--------------+
编写一个 SQL 查询，找出每个部门工资前三高的员工。例如，根据上述给定的表格，查询结果应返回：
+------------+----------+--------+
| Department | Employee | Salary |
+------------+----------+--------+
| IT         | Max      | 90000  |
| IT         | Randy    | 85000  |
| IT         | Joe      | 70000  |
| Sales      | Henry    | 80000  |
| Sales      | Sam      | 60000  |
+------------+----------+--------+

此外，请考虑实现各部门前N高工资的员工功能。

项目十二  分数排名 - （难度：中等）
依然是昨天的分数表，实现排名功能，但是排名是非连续的，如下：
+-------+------+
| Score | Rank |
+-------+------+
| 4.00  | 1    |
| 4.00  | 1    |
| 3.85  | 3    |
| 3.65  | 4    |
| 3.65  | 4    |
| 3.50  | 6    |
+-------+------
```

```
数据导入导出
-- 查看secure-file-priv 
SHOW VARIABLES LIKE '%secure%';

-- 二维表导出到csv
SELECT * FROM Person
    INTO OUTFILE '/var/lib/mysql-files/output.csv'
    FIELDS TERMINATED BY ','           --字段以','分隔
    OPTIONALLY ENCLOSED BY ""          --字段用""括起
    ESCAPED BY ""                      --字段中使用的转义符为"
    LINES TERMINATED BY '\r\n';        --行以\r\n结束


-- 导入csv
-- 需要对应字段的二维表存在
LOAD DATA INFILE '/var/lib/mysql-files/output.csv'
    INTO TABLE Person
    FIELDS TERMINATED BY ','
    OPTIONALLY ENCLOSED BY ""
    ESCAPED BY ""
    LINES TERMINATED BY '\r\n';
作业
7
建表

CREATE TABLE Employee(
    Id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    Name VARCHAR(10) NOT NULL,
    Salary INT NOT NULL,
    DepartmentId INT NOT NULL);

CREATE TABLE Department(
    Id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    Name VARCHAR(30) NOT NULL);
插入数据

INSERT INTO Employee
    VALUES (1, 'Joe', 70000, 1),
            (2, 'Henry', 80000, 2),
            (3, 'Sam', 60000, 2),
            (4, 'Max', 90000, 1);

INSERT INTO Department
    VALUES (1, 'IT'),
            (2, 'Sales');
答案

-- 去掉 sql_mode 的 ONLY_FULL_GROUP_BY 
set global sql_mode='STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION';
set session sql_mode='STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION';


SELECT  d.Name Department, e.Name Employee, MAX(Salary) Salary
    FROM Employee e
    LEFT JOIN Department d
    ON e.DepartmentId = d.Id
    GROUP BY Department;


SELECT d.Name Department, e.Name Employee ,salary
FROM Employee e 
JOIN Department d
ON e.DepartmentId = d.id
WHERE salary IN
    (SELECT MAX(salary)
    FROM Employee
    GROUP BY DepartmentId);
8
建表

CREATE TABLE seat(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    student VARCHAR(40) NOT NULL);
插入数据

INSERT INTO seat
    VALUES (1, 'Abbot'),
            (2, 'Doris'),
            (3, 'Emerson'),
            (4, 'Green'),
            (5, 'Jeams');
答案

SELECT
(CASE
WHEN MOD(id, 2) = 1 AND id != (SELECT MAX(id) FROM seat) THEN id + 1
WHEN MOD(id, 2) = 0 THEN id -1
ELSE id
END)  id, student
FROM seat    -- order 21435
ORDER BY id; -- reset order 12345
9
建表

CREATE TABLE score(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    Score FLOAT NOT NULL);
插入数据

INSERT INTO score
    VALUES (1, 3.50),
            (2, 3.65),
            (3, 4.00),
            (4, 3.85),
            (5, 4.00),
            (6, 3.65);
答案

-- 自定义rank函数, 降序后, 将Score与上一个Score对比, 若不同则Rank+1, 不降序Rank就失效了
SELECT
  Score,
  @rank := @rank + (@prev <> (@prev := Score))  Rank
FROM
  score,
  (SELECT @rank := 0, @prev := -1) init
ORDER BY Score DESC;

-- 提前计算出了每个无重复Score的Rank, 即使不降序每个Score的Rank依然准确, 比方法一要耗时
SELECT
  Score,
  (SELECT COUNT(DISTINCT Score) FROM score WHERE Score >= s.Score) Rank
FROM score s
ORDER BY Score desc;
10
建表

CREATE TABLE trips(
    Id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    Client_Id INT NOT NULL,
    Driver_Id INT NOT NULL,
    City_Id INT NOT NULL,
    Status ENUM('completed', 'cancelled_by_driver', 'cancelled_by_client') NOT NULL,
    Request_at DATE DEFAULT NULL);

CREATE TABLE Users(
    Users_Id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    Banned VARCHAR(10) NOT NULL,
    Role ENUM('client', 'driver', 'partnet') NOT NULL);
插入数据

INSERT INTO trips
     VALUES (1,1,10,1,'completed','2013-10-01'),
             (2,2,11,1, 'cancelled_by_driver','2013-10-01'),
             (3,3,12,6,'completed','2013-10-01'),
             (4,4,13,6,'cancelled_by_client','2013-10-01'),
             (5,1,10,1,'completed','2013-10-02'),
             (6,2,11,6,'completed','2013-10-02'),
             (7,3,12,6,'completed','2013-10-02'),
             (8,2,12,12,'completed','2013-10-03'),
             (9,3,10,12,'completed','2013-10-03'),
             (10,4,13,12, 'cancelled_by_driver','2013-10-03');

INSERT INTO Users
    VALUES (1, 'No', 'client'),
            (2, 'Yes', 'client'),
            (3, 'No', 'client'),
            (4, 'No', 'client'),
            (10, 'No', 'driver'),
            (11, 'No', 'driver'),
            (12, 'No', 'driver'),
            (13, 'No', 'driver');
答案

SELECT t.Request_at Day,
ROUND(SUM((CASE WHEN t.Status LIKE 'cancelled%' THEN 1 ELSE 0 END))/COUNT(*),2) 'Cancellation Rate'  
FROM trips t  
INNER JOIN Users u 
ON u.Users_Id = t.Client_Id AND u.Banned = 'No'  
WHERE t.Request_at BETWEEN '2013-10-01'and'2013-10-03' 
GROUP BY t.Request_at;
11
建表

CREATE TABLE Employee(
    Id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    Name VARCHAR(10) NOT NULL,
    Salary INT NOT NULL,
    DepartmentId INT NOT NULL);
插入数据

INSERT INTO Employee
    VALUES (1, 'Joe', 70000, 1),
            (2, 'Henry', 80000, 2),
            (3, 'Sam', 60000, 2),
            (4, 'Max', 90000, 1),
            (5, 'Janet', 69000, 1),
            (6, 'Randy', 85000, 1);
答案

SELECT d.Name Department, e1.Name Employee, e1.Salary Salary
FROM Employee e1
JOIN Department d
ON e1.DepartmentId = d.Id
WHERE 3 >   (
            SELECT COUNT(DISTINCT e2.Salary) 
            FROM Employee e2
            WHERE e2.Salary > e1.Salary AND e1.DepartmentId = e2.DepartmentId
            )
ORDER BY d.Name, e1.Salary DESC;
12
建表

CREATE TABLE score(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    Score FLOAT NOT NULL);
插入数据

INSERT INTO score
    VALUES (1, 3.50),
            (2, 3.65),
            (3, 4.00),
            (4, 3.85),
            (5, 4.00),
            (6, 3.65);
答案

-- 自定义rank函数, 降序后, 将Score与上一个Score对比, 若不同则Rank+count, count置1, 相同count+=1, 不降序Rank就失效了
SELECT
  Score,
  @rank := @rank + (@prev <> (s.Score)) * @count  Rank,
(CASE 
WHEN (@prev <> (@prev := Score)) THEN @count := 1
ELSE @count := @count + 1  END) Count
FROM
  score s,
  (SELECT @rank := 0, @prev := -1, @count := 1) init
ORDER BY Score DESC;
:=和=的区别
=

只有在set和update时才是和:=一样，赋值的作用，其它都是等于的作用。鉴于此，用变量实现行号时，必须用:=

:=

select时也是赋值的作用
```
