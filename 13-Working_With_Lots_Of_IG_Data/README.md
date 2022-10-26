# Challenges

1. Que: Find 4 oldest users.

```
SELECT * FROM users
ORDER BY created_at
LIMIT 4;
```

2. Que: What day of week most users registered on

```
SELECT DAYNAME(users.created_at) as day_name
FROM users
GROUP BY day_name
ORDER BY COUNT(day_name) DESC
LIMIT 1;
```
