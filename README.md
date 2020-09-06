- 1、ORDER BY 根据指定的列对结果集进行排序，默认按照升序，降序 ORDER BY DESC
- LIMIT(m, n) 从第 m + 1 行开始取 n 条记录 ;第一个参数指定第一个返回记录行的偏移量，第二个参数指定返回记录行的最大数目。注意:初始记录行的偏移量是 0(而不是 1)

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