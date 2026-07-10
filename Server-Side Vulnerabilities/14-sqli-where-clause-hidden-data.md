# SQLi in WHERE Clause, Hidden Data

Category filter (`?category=Gifts`) goes straight into a WHERE clause. Tested with a single quote, got a DB error back, so it's injectable.

Payload:
```
?category=Gifts' OR 1=1--
```
Comments out the rest of the query including the "released" check, so hidden/unreleased products show up too. Lab solved.

**Fix:** parameterized queries, always. Never concatenate user input into SQL.
