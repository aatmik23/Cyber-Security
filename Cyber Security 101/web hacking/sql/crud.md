
```shell-session
mysql> INSERT INTO books (id, name, published_date, description)
    VALUES (1, "Android Security Internals", "2014-10-14", "An In-Depth Guide to Android's Security Architecture");

Query OK, 1 row affected (0.01 sec)
```


```shell-session
mysql> SELECT * FROM books;
```

```shell-session
mysql> SELECT name, description FROM books;
```


### Update Operation (UPDATE)

```shell-session
mysql> UPDATE books
    SET description = "An In-Depth Guide to Android's Security Architecture."
    WHERE id = 1;
```


### Delete Operation (DELETE)

```shell-session
mysql> DELETE FROM books WHERE id = 1;
```