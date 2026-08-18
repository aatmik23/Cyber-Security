
avoid duplication
```shell-session
 SELECT DISTINCT name FROM books;
```  


```shell-session
 SELECT name, COUNT(*)
    FROM books
    GROUP BY name;
```


```shell-session
SELECT *
    FROM books
    ORDER BY published_date ASC;
```


```shell-session
SELECT name, COUNT(*)
    FROM books
    GROUP BY name
    HAVING name LIKE '%Hack%';
```

