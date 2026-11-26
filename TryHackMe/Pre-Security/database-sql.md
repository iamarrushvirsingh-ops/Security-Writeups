# Database SQL

- SQL (Structured Query Language) is used to ask a database for data.
- `SELECT *`: the `*` symbol means **all columns**.
- The word `FROM` tells the database which table to use.

```sql
SELECT * FROM Orders;
SELECT drink, price FROM Orders;
```

- The `WHERE` keyword filters rows. It keeps only the rows that match a condition.

```sql
SELECT * FROM Orders WHERE drink = 'Coffee';
```

- The `ORDER BY` keyword sorts results by a column. By default, results are sorted in ascending order (lowest to highest). Add `DESC` to sort from highest to lowest.

```sql
SELECT * FROM Orders ORDER BY price;
SELECT * FROM Orders ORDER BY price DESC;
```

## SQL Keywords Learned in This Room

- `SELECT`: choose what data to display
- `FROM`: choose where the data comes from
- `WHERE`: filter records based on a condition
- `ORDER BY`: sort the results
