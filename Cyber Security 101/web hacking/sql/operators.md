
boolean value of `TRUE` or `FALSE`.

### LIKE Operator

```shell-session
SELECT *
    FROM books
    WHERE description LIKE "%guide%";
```

### AND Operator

```shell-session
SELECT *
    FROM books
    WHERE category = "Offensive Security" AND name = "Bug Bounty Bootcamp"; 
```

### OR Operator

```shell-session
SELECT *
    FROM books
    WHERE name LIKE "%Android%" OR name LIKE "%iOS%"; 
```

### NOT Operator


```shell-session
ELECT *
    FROM books
    WHERE NOT description LIKE "%guide%";
```

### BETWEEN Operator

```shell-session
SELECT *
    FROM books
    WHERE id BETWEEN 2 AND 4;
```

## Comparison Operators

`=`

```shell-session
SELECT *
    FROM books
    WHERE name = "Designing Secure Software";
```

not equal
`!=`

Less Than Operator

The `<` (less tha

### Greater Than Operator

The `>` (greater than)

`<=` (Less than or equal) o


![](../../assets/Pasted%20image%2020260818233524.png)

![](../../assets/Pasted%20image%2020260818233637.png)