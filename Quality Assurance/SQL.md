## SQL 👩‍💻

1. Zwróć wszystkich klientów, którzy NIE pochodzą z „Niemiec”, „Francji” ani „Wielkiej Brytanii”:

```sql
SELECT * FROM Customers
WHERE Country NOT IN ('Germany', 'France', 'UK');
```

![SQL 1](https://github.com/ios1111-creator/PORTFOLIO/assets/65659662/51a761f7-33af-434d-b09d-c239ab8505f4)

2. Zwróć wszystkich klientów, którzy NIE pochodzą z „Niemiec”, „Francji” ani „Wielkiej Brytanii”:

```sql
SELECT * FROM Customers
WHERE Country IN ('Germany', 'France', 'UK');
```

![SQL 2](https://github.com/ios1111-creator/PORTFOLIO/assets/65659662/00a9241f-eb58-4e86-ab13-b9dc1a4eb82c)

3. Dodaj kolumne Email do tabeli Customers:

```sql
ALTER TABLE Customers
ADD Email varchar(255);
```

![SQL 3](https://github.com/ios1111-creator/PORTFOLIO/assets/65659662/7e26a056-3b86-4202-8e61-31f73c88f850)

4. Zaktualizuj tabele Customers, na first_name 'Jan' i last_name na 'Nowak', wtedy gdy CustomerID jest równy 1

```sql
UPDATE Customers SET first_name ='Jan', last_name = 'Nowak' WHERE customer_id = 1
```

![SQL 4](https://github.com/ios1111-creator/PORTFOLIO/assets/65659662/62abc2ae-043a-4fd8-a404-677d7b153071)

5. Zwróć wszystkich klientów z miastem rozpoczynającym się od „L”, po którym następują dowolne 3 znaki i kończącym się na „on”:

```sql
SELECT * FROM Customers
WHERE City LIKE 'L___on';
```

![SQL 5](https://github.com/ios1111-creator/PORTFOLIO/assets/65659662/8f87932d-0a39-4230-ab83-7a75beb669ec)

6. Zwróć wszystkich klientów, którzy mają „r” na drugiej pozycji:

```sql
SELECT * FROM Customers
WHERE CustomerName LIKE '_r%';
```

![SQL 6](https://github.com/ios1111-creator/PORTFOLIO/assets/65659662/447ffe5a-33ff-4d84-9746-db0121ad4d55)

7. Zwróć wszystkich klientów (Customers), którzy mają zamówienie w tabeli Zamówienia (Orders ) od największej od najmniejszej po CustomerID:

```sql
SELECT DISTINCT Customers.*
FROM Customers
INNER JOIN Orders ON Customers.CustomerID = Orders.CustomerID
ORDER BY Customers.CustomerID DESC;
```

![image](https://github.com/ios1111-creator/PORTFOLIO/assets/65659662/676b1aa8-4e2c-43de-a208-69b63938a988)

8. Stwórz nową tabelę o nazwie „TestTable” która jest kopią tabeli „Klienci” (Customers):

```sql
CREATE TABLE TestTable AS
SELECT first_name, last_name
FROM Customers;
```

# ![SQL 8](https://github.com/ios1111-creator/PORTFOLIO/assets/65659662/6d227db3-afdf-4057-8bf6-46155bb8c433)
