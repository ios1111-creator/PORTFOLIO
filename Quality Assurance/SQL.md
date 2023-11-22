## SQL 👩‍💻

1. Zwróć wszystkich klientów, którzy NIE pochodzą z „Niemiec”, „Francji” ani „Wielkiej Brytanii”:

```sql
SELECT * FROM Customers
WHERE Country NOT IN ('Germany', 'France', 'UK');
```

![zadanie 1](E:\Testowanie\PORTFOLIO\Quality Assurance\images\1.png)
