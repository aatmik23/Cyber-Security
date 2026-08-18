

CONCAT() Function

```shell-session
mysql> SELECT CONCAT(name, " is a type of ", category, " book.") AS book_info FROM books;
```


GROUP_CONCAT() Function

```shell-session
mysql> SELECT category, GROUP_CONCAT(name SEPARATOR ", ") AS books
    FROM books
    GROUP BY category;
+--------------------+-------------------------------------------------------------+
| category           | books                                                       |
+--------------------+-------------------------------------------------------------+
| Defensive Security | Android Security Internals, Designing Secure Software       |
| Offensive Security | Bug Bounty Bootcamp, Car Hacker's Handbook, Ethical Hacking |
+--------------------+-------------------------------------------------------------+
```


SUBSTRING() Function

```shell-session
mysql> SELECT SUBSTRING(published_date, 1, 4) AS published_year FROM books;
+----------------+
| published_year |
+----------------+
| 2014           |
| 2021           |
| 2016           |
| 2021           |
| 2021           |
+----------------+
```


LENGTH() Function

```shell-session
> SELECT LENGTH(name) AS name_length FROM books;
```

Aggregate Functions

```shell-session
mysql> SELECT COUNT(*) AS total_books FROM books;
+-------------+
| total_books |
+-------------+
|           5 |
+-------------+
```

SUM() Function

```shell-session
SELECT SUM(price) AS total_price FROM books;
+-------------+
| total_price |
+-------------+
|      249.95 |
```


MAX() Function

```shell-session
mysql> SELECT MAX(published_date) AS latest_book FROM books;
+-------------+
| latest_book |
+-------------+
| 2021-12-21  |
+-------------+
```

```shell-session
SELECT MIN(published_date) AS earliest_book FROM books;
```




![](../../assets/Pasted%20image%2020260818234957.png)


![](../../assets/Pasted%20image%2020260818235104.png)

![](../../assets/Pasted%20image%2020260818235921.png)