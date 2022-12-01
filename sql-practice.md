+ [1](#1)
+ [2](#2)
+ [3](#3)
+ [4](#4)
+ [5](#5)
+ [6](#6)
+ [7](#7)
+ [8](#8)
+ [9](#9)
+ [10](#10)
+ [11](#11)
+ [12](#12)
+ [13](#13)
+ [14](#14)
+ [15](#15)
+ [16](#16)
+ [17](#17)
+ [18](#18)
+ [19](#19)
+ [20](#20)

## 1

https://sql-ex.ru/learn_exercises.php?LN=1

```sql
SELECT model, speed, hd
FROM PC
WHERE price < 500
```

## 2

https://sql-ex.ru/learn_exercises.php?LN=2

```sql
SELECT distinct maker
FROM product
WHERE type='Printer'
```

## 3

https://sql-ex.ru/learn_exercises.php?LN=3

```sql
SELECT model, ram, screen
FROM laptop
WHERE price > 1000
```

## 4

https://sql-ex.ru/learn_exercises.php?LN=4

```sql
SELECT *
FROM printer
WHERE color = 'y'
```

## 5

https://sql-ex.ru/learn_exercises.php?LN=5

```sql
SELECT model, speed, hd
FROM PC
WHERE (cd = '12x' or cd ='24x') and price < 600
```

## 6

https://sql-ex.ru/learn_exercises.php?LN=6

```sql
SELECT DISTINCT Product.maker, Laptop.speed
FROM Product
JOIN Laptop
ON Product.model = Laptop.model
WHERE hd >= 10
```

## 7

https://sql-ex.ru/learn_exercises.php?LN=7

```sql
SELECT Laptop.model, Laptop.price
FROM Laptop
JOIN Product
ON Laptop.model=Product.model
WHERE maker='B'
UNION
SELECT PC.model, PC.price
FROM PC
JOIN Product
ON PC.model=Product.model
WHERE maker='B'
UNION
SELECT Printer.model, Printer.price
FROM Printer
JOIN Product
ON Printer.model=Product.model
WHERE maker='B'
```

## 8

https://sql-ex.ru/learn_exercises.php?LN=8

```sql
SELECT maker
FROM Product
WHERE type='PC'
EXCEPT
SELECT maker
FROM Product
WHERE type='Laptop'
```

## 9

https://sql-ex.ru/learn_exercises.php?LN=9

```sql
SELECT DISTINCT Product.maker
FROM PC
JOIN Product
ON PC.model=Product.model
WHERE speed >= 450
```

## 10

https://sql-ex.ru/learn_exercises.php?LN=10

```sql
SELECT model, price
FROM Printer
WHERE price = (SELECT MAX(price)
FROM Printer
)
```

## 11

https://sql-ex.ru/learn_exercises.php?LN=11

```sql
SELECT AVG(speed)
FROM PC
```

## 12

https://sql-ex.ru/learn_exercises.php?LN=12

```sql
SELECT AVG(speed)
FROM Laptop
WHERE price > 1000
```

## 13

https://sql-ex.ru/learn_exercises.php?LN=13

```sql
SELECT AVG(speed)
FROM PC
JOIN Product
ON PC.model=Product.model
WHERE maker='A'
```

## 14

https://sql-ex.ru/learn_exercises.php?LN=14

```sql
SELECT Ships.class, Ships.name, Classes.country
FROM Ships
JOIN Classes
ON Classes.class=Ships.class
WHERE numGuns >= 10
```

## 15

https://sql-ex.ru/learn_exercises.php?LN=15

```sql
SELECT hd
FROM PC
GROUP BY hd
HAVING COUNT(hd) >= 2
```

## 16

https://sql-ex.ru/learn_exercises.php?LN=16

```sql
SELECT DISTINCT pc1.model, pc2.model, pc1.speed, pc1.RAM
FROM PC as pc1, PC as pc2
WHERE pc1.model>pc2.model AND pc1.RAM=pc2.RAM AND pc1.speed=pc2.speed
```

## 17

https://sql-ex.ru/learn_exercises.php?LN=17

```sql
SELECT DISTINCT Product.type, Laptop.model, Laptop.speed
FROM Laptop
JOIN Product
On Product.model=Laptop.model
WHERE Laptop.speed<(SELECT MIN(speed) AS min_PC_speed FROM PC)
```

## 18

https://sql-ex.ru/learn_exercises.php?LN=18

```sql
SELECT DISTINCT Product.maker, Printer.price
FROM Printer
JOIN Product
ON Printer.model=Product.model
WHERE Printer.color='y' AND Printer.price=(SELECT MIN(price)
FROM Printer
WHERE color='y'
)
```

## 19

https://sql-ex.ru/learn_exercises.php?LN=19

```sql
SELECT Product.maker, AVG(Laptop.screen)
FROM Laptop
JOIN Product
ON Product.model=Laptop.model
GROUP BY Product.maker
```

## 20

https://sql-ex.ru/learn_exercises.php?LN=20

```sql
SELECT maker, COUNT(type)
FROM Product
WHERE type='PC'
GROUP BY Product.maker
HAVING COUNT(type)>=3
```
