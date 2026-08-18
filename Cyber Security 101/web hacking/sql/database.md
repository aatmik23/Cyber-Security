
![](../../assets/Pasted%20image%2020260818211200.png)


```shell-session
mysql> CREATE DATABASE database_name;
```


```shell-session
mysql> SHOW DATABASES;
```

```shell-session
mysql> USE thm_bookmarket_db;
```

### removed using the `DROP` statement.

   mysql> DROP database database_name;


```shell-session
mysql> CREATE TABLE example_table_name (
    example_column1 data_type,
    example_column2 data_type,
    example_column3 data_type
```

```shell-session
mysql> CREATE TABLE book_inventory (
    book_id INT AUTO_INCREMENT PRIMARY KEY,
    book_name VARCHAR(255) NOT NULL,
    publication_date DATE
);
```


descibe

           mysql> DESCRIBE book_inventory;

           mysql> ALTER TABLE book_inventory
ADD page_count INT;


```shell-session
mysql> DROP TABLE table_name;
```

