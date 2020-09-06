## 查询

- 1、ORDER BY 根据指定的列对结果集进行排序，默认按照升序，降序 ORDER BY DESC
- LIMIT(m, n) 从第 m + 1 行开始取 n 条记录 ;第一个参数指定第一个返回记录行的偏移量，第二个参数指定返回记录行的最大数目。注意:初始记录行的偏移量是 0(而不是 1)
- INNER JOIN 两边表同时有对应的数据，即任何一边缺失数据就不显示。
LEFT JOIN 会读取左边数据表的全部数据，即便右边表无对应数据。
RIGHT JOIN 会读取右边数据表的全部数据，即便左边表无对应数据。
```sql
# 分组后继续查询
SELECT user_name 
AS 用户, COUNT(id) AS 下单数量 
FROM `Order` 
GROUP BY user_id 
HAVING COUNT(id)>2;
```

## 函数
- MAX 取最大值 eg：SELECT MAX(hire_date) FROM employees
- replace(original-string，search-string，replace-string)
  - original-string： 被搜索的字符串。可为任意长度。 
  - search-string： 要搜索并被 replace-string 替换的字符串。该字符串的长度不应超过 255 个字节。如果 search-string 是空字符串，则按原样返回原始字符串。 
  - replace-string： 该字符串用于替换 search-string。可为任意长度。如果 replacement-string 是空字符串，则删除出现的所有 search-string。
```SQL
UPDATE `titles_test`
SET emp_no = REPLACE(emp_no,'10001','10005') 
WHERE id=5 AND emp_no=10001
```

## 表操作
```sql 
# 重命名：
ALTER TABLE titles_test RENAME TO titles_2017;
```

## 创建视图
视图无非就是存储在数据库中并具有名字的 SQL 语句，或者说是以预定义的 SQL 查询的形式存在的数据表的成分。，一种虚拟的表.
```sql
CREATE VIEW view_name AS
SELECT column1, column2.....
FROM table_name
WHERE [condition];
```