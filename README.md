# Домашнє завдання до Теми 7. Додаткові вбудовані SQL функції. Робота з часом

1. Напишіть SQL-запит, який для таблиці orders з атрибута date витягує рік, місяць і число. Виведіть на екран їх у три окремі атрибути поряд з атрибутом id та оригінальним атрибутом date (всього вийде 5 атрибутів).
```SQL 
SELECT
    id,
    date,
    YEAR(date) AS year,
    MONTH(date) AS month,
    DAY(date) AS day
FROM orders;
```
![1.png](1.png)

2. Напишіть SQL-запит, який для таблиці orders до атрибута date додає один день. На екран виведіть атрибут id, оригінальний атрибут date та результат додавання.
```SQL 
SELECT
    id,
    date,
    DATE_ADD(date, INTERVAL 1 DAY) AS date_plus_one
FROM orders;
```
![2.png](2.png)

3. Напишіть SQL-запит, який для таблиці orders для атрибута date відображає кількість секунд з початку відліку (показує його значення timestamp). Для цього потрібно знайти та застосувати необхідну функцію. На екран виведіть атрибут id, оригінальний атрибут date та результат роботи функції.
```SQL 
SELECT
    id,
    date,
    UNIX_TIMESTAMP(date) AS date_timestamp
FROM orders;
```
![3.png](3.png)



4. Напишіть SQL-запит, який рахує, скільки таблиця orders містить рядків з атрибутом date у межах між 1996-07-10 00:00:00 та 1996-10-08 00:00:00.
```SQL 
SELECT
    COUNT(*) AS count_in_range
FROM orders
WHERE date BETWEEN '1996-07-10 00:00:00' AND '1996-10-08 00:00:00';
```
![4.png](4.png)



5. Напишіть SQL-запит, який для таблиці orders виводить на екран атрибут id, атрибут date та JSON-об’єкт {"id": <атрибут id рядка>, "date": <атрибут date рядка>}. Для створення JSON-об’єкта використайте функцію.
```SQL 
SELECT
    id,
    date,
    JSON_OBJECT('id', id, 'date', date) AS json_data
FROM orders;
```
![5.png](5.png)

