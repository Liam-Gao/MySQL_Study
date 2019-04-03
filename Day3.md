## 内容
1. MySQL表数据类型
2. 用SQL语句创建表
    - 语句解释
    - 设定列类型 、大小、约束
    - 设定主键
3. 用SQL语句向表中添加数据
    - 语句解释
    - 多种添加方式（指定列名；不指定列名）
4. 用SQL语句删除表
    - 语句解释
    - DELETE
    - DROP
    - TRUNCATE
    - 不同方式的区别
5. 用SQL语句修改表
    - 修改列名
    - 修改表中数据
    - 删除行
    - 删除列
    - 新建列
    - 新建行
6. 表联结
    - MySQL别名
    - INNER JOIN
    - LEFT JOIN
    - CROSS JOIN
    - 自连接
    - UNION
    - 以上几种方式的区别和联系
7. Notice：
    - Where 和 Having 的使用场景
项目三：超过5名学生的课（难度：简单）  
创建如下所示的courses 表 ，有: student (学生) 和 class (课程)。  
'''例如,表:  
| student | class      |  
| A       | Math       |  
| B       | English    |  
| C       | Math       |  
| D       | Biology    |  
| E       | Math       |  
| F       | Computer   |  
| G       | Math       |  
| H       | Math       |  
| I       | Math       |   
| A      | Math       |  
'''
编写一个 SQL 查询，列出所有超过或等于5名学生的课。  
应该输出:  
+---------+  
| class   |  
+---------+  
| Math    |  
+---------+。。  
Note:  
学生在每个课中不应被重复计算。  
**select class FROM (SELECT DISTINCT * from courses) as c GROUP BY c.class HAVING COUNT(class) >5;**  
---
项目四：交换工资（难度：简单）  
创建一个 salary表，如下所示，有m=男性 和 f=女性的值 。  
例如:  
| id | name | sex | salary |  
|----|------|-----|--------|  
| 1  | A    | m   | 2500   |  
| 2  | B    | f   | 1500   |  
| 3  | C    | m   | 5500   |  
| 4  | D    | f   | 500    |  

交换所有的 f 和 m 值(例如，将所有 f 值更改为 m，反之亦然)。要求使用一个更新查询，并且没有中间临时表。  
运行你所编写的查询语句之后，将会得到以下表:  
| id | name | sex | salary |  
|----|------|-----|--------|  
| 1  | A    | f  | 2500   |  
| 2  | B    | m   | 1500   |  
| 3  | C    | f   | 5500   |  
| 4  | D    | m   | 500    |  

**update salary set sex=case when sex='f' then 'm' else 'f' end;**  
---
项目五：组合两张表 （难度：简单）  
在数据库中创建表1和表2，并各插入三行数据（自己造）  
表1: Person  
+-------------+---------+  
| 列名         | 类型     |  

| PersonId    | int     |  
| FirstName   | varchar |  
| LastName    | varchar |  

PersonId 是上表主键  
'''表2: Address  
| 列名         | 类型    |  

| AddressId   | int     |  
| PersonId    | int     |  
| City        | varchar |  
| State       | varchar |'''
AddressId 是上表主键  
编写一个 SQL 查询，满足条件：无论 person 是否有地址信息，都需要基于上述两表提供 person 的以下信息：FirstName, LastName, City, State  
**select p.firstname, p.lastname, a.city, a.state from Person p left join address a on p.personid=a.personid;**
---
项目六：删除重复的邮箱（难度：简单）  
编写一个 SQL 查询，来删除 email 表中所有重复的电子邮箱，重复的邮箱里只保留 Id 最小 的那个。  
+----+---------+  
| Id | Email   |  
+----+---------+  
| 1  | a@b.com |  
| 2  | c@d.com |  
| 3  | a@b.com |  
+----+---------+  
Id 是这个表的主键。  
例如，在运行你的查询语句之后，上面的 Person表应返回以下几行:  
+----+------------------+  
| Id | Email            |  
+----+------------------+  
| 1  | a@b.com |  
| 2  | c@d.com  |  
+----+------------------+  
**delete e1 from email e1, email e2 where e1.email=e2.email and e1.id>e2.id;**

