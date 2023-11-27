## SQL 👩‍💻

1. Zwróć wszystkich klientów, którzy NIE pochodzą z „Niemiec”, „Francji” ani „Wielkiej Brytanii”:

```sql
SELECT * FROM Customers
WHERE Country NOT IN ('Germany', 'France', 'UK');
```

![SQL 1](https://github.com/ios1111-creator/PORTFOLIO/assets/65659662/51a761f7-33af-434d-b09d-c239ab8505f4)

2. Zwróć wszystkich klientów, którzy pochodzą z „Niemiec”, „Francji” ani „Wielkiej Brytanii”:

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
UPDATE Customers SET first_name ='Jan', last_name = 'Nowak'
WHERE customer_id = 1
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

9. Zwróć wszystkie rekordy z tabeli o nazwie 'Products', gdzie 'Price' znajduje się w kolejności od najmniejszej do najwiekszej pomiędzy 50 i 100?

```sql
SELECT * FROM Products
WHERE Price >= 50 AND Price <=100
ORDER BY Price;
lub
SELECT * FROM Products
WHERE Price BETWEEN 50 AND 100
ORDER BY Price;
```

![SQL 9](https://github.com/ios1111-creator/PORTFOLIO/assets/65659662/b98dd01f-a560-4463-a980-0b458ea8f8a0)

10. Zwróć wszystkich klientów zaczynających się od „a”, „b”, „c”, „d”, „e”, „f”:

```sql
SELECT * FROM Customers
WHERE CustomerName LIKE '[a-f]%';
```

![SQL 10](https://github.com/ios1111-creator/PORTFOLIO/assets/65659662/24800ecc-f972-44c6-92b2-bddc932d5ce8)

11. Zwróć wszystkich klientów, którzy NIE złożyli żadnych zamówień w tabeli Zamówienia:

```sql
SELECT * FROM Customers
WHERE CustomerID NOT IN (SELECT CustomerID FROM Orders);
```

![SQL 11](https://github.com/ios1111-creator/PORTFOLIO/assets/65659662/d082c859-1ec7-4258-8516-36c7f9b65271)

12. Wstaw do tabeli Orders, nowy rekord item headphones i amount 150, dla klienta o id 1:

```sql
INSERT INTO Orders(item,amount,customer_id)
VALUES('Headphones','150',1)
```

![SQL 12](https://github.com/ios1111-creator/PORTFOLIO/assets/65659662/7f6d82f5-702a-40f8-8ac2-8c500cea8caa)

13. Połącz kolumnę OrderID, OrderDate z tabeli Orders i kolumnę LastName, FirstName z tabeli Employees, łącząc relacje tak, żeby EmployeeID pasowało do danego rekordu z tabeli Orders i Employees, do tego dodaj z tabeli Shippers kolumny ShipperName, Phone:

```sql
SELECT Orders.OrderID, Orders.EmployeeID ,Employees.FirstName, Employees.LastName, Orders.OrderDate, Shippers.ShipperName, Shippers.Phone FROM ((Orders
INNER JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID)
INNER JOIN Shippers ON Orders.ShipperID = Shippers.ShipperID)
```

![SQL 13](https://github.com/ios1111-creator/PORTFOLIO/assets/65659662/3c80034b-bba1-4f8e-bffc-c3f33af10755)
