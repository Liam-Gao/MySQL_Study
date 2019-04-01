### SQL
SQL（Structured Query Language）结构化查询语言，是用于访问数据库的标准化语言  
它包含三部分：
- 数据定义语言，包含定义数据库及其对象的语句，例如表，视图，触发器，储存过程等。
- 数据操作语言，包括允许更新和查询数据的语句。
- 数据控制语言，允许授予用户权限访问数据库中特定数据的权限。
MySQL是一个数据库管理系统，也是一个关系数据库。  

### SELECT语句
select由以下几个子句组成：
- SELECT：之后是逗号分隔的列（或者*），表示要返回的所有列。
- FROM：指定要查询的数据表或者视图。
- JOIN：根据某些连接条件从其他表中获取数据。
- WHERE：过滤结果集中的行
- GROUP BY：将一组行组合成小分组，并对每一个小分组应用聚合函数。
- HAVING：过滤器基于Group By子句定义的小分组。
- ORDER BY：指定用于排序的列的列表。
- LIMIT：限制返回行的数量。
#### SELECT DISTINCT子句
- 从表中查询数据，可能会收到重复的行记录，为了删除重复行，可以：select distinct “your columns” from XXX  
- 如果列具有NULL值，则会保留一个NULL值。
- distinct是group by的特殊形式，区别：group by对结果进行排序，distinct不进行排序。
#### 聚合函数
AVG、COUNT、SUM、MIN、MAX，除了COUNT外，其他聚合函数在 执行计算时会忽略NULL值。
---
## 作业
