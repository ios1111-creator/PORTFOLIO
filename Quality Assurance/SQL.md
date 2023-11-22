## SQL 👩‍💻

1. Zwróć wszystkich klientów, którzy NIE pochodzą z „Niemiec”, „Francji” ani „Wielkiej Brytanii”:

```sql
SELECT * FROM Customers
WHERE Country NOT IN ('Germany', 'France', 'UK');
```

![zadanie 1](//images/SQL 1.png)
