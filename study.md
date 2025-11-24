# SQL 基础知识

## SQL 简介

SQL（Structured Query Language）是用于管理关系数据库的标准编程语言。

## 基本分类

### DDL - 数据定义语言
用于定义数据库结构

```sql
CREATE DATABASE database_name;
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    ...
);
ALTER TABLE table_name ADD column_name datatype;
DROP TABLE table_name;
```

### DML - 数据操作语言
用于操作数据库中的数据

```sql
INSERT INTO table_name (column1, column2) VALUES (value1, value2);
UPDATE table_name SET column1 = value1 WHERE condition;
DELETE FROM table_name WHERE condition;
```

### DQL - 数据查询语言
用于查询数据库中的数据

```sql
SELECT column1, column2 FROM table_name WHERE condition;
SELECT * FROM table_name ORDER BY column1 DESC;
SELECT COUNT(*) FROM table_name;
```

### DCL - 数据控制语言
用于控制数据库访问权限

```sql
GRANT privilege ON table_name TO user;
REVOKE privilege ON table_name FROM user;
```

## 常用数据类型

- **INT** - 整数
- **VARCHAR(n)** - 可变长度字符串
- **CHAR(n)** - 固定长度字符串  
- **DATE** - 日期
- **DECIMAL(p,s)** - 精确小数
- **BOOLEAN** - 布尔值

## 约束条件

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    PRIMARY KEY (ID),
    UNIQUE (LastName),
    CHECK (Age >= 18)
);
```

## 查询进阶

### 连接查询
```sql
SELECT Orders.OrderID, Customers.CustomerName
FROM Orders
INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID;
```

### 聚合函数
```sql
SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country
HAVING COUNT(CustomerID) > 5;
```

### 子查询
```sql
SELECT ProductName
FROM Products
WHERE ProductID IN (SELECT ProductID FROM OrderDetails WHERE Quantity > 100);
```

## 常用函数

### 字符串函数
```sql
SELECT UPPER(column_name), LOWER(column_name), LENGTH(column_name)
FROM table_name;
```

### 数值函数
```sql
SELECT ROUND(column_name, 2), ABS(column_name), AVG(column_name)
FROM table_name;
```

### 日期函数
```sql
SELECT NOW(), CURDATE(), DATE_FORMAT(date_column, '%Y-%m-%d')
FROM table_name;
```

## 事务控制

```sql
START TRANSACTION;
UPDATE Accounts SET balance = balance - 100 WHERE account_id = 1;
UPDATE Accounts SET balance = balance + 100 WHERE account_id = 2;
COMMIT;
-- 或 ROLLBACK;
```

## 最佳实践

1. **使用明确的列名**代替 `SELECT *`
2. **合理使用索引**提高查询性能
3. **避免在 WHERE 子句**中使用函数
4. **使用参数化查询**防止 SQL 注入
5. **定期备份**重要数据

---

**注意：** 不同数据库系统（MySQL、PostgreSQL、SQL Server等）在语法上可能有细微差异。