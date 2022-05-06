# Question 3

## Using the `tutorial.oscar_nominees` Table

### Columns
-- year | category | nominee | movie | winner | id

### Test query

```SQL
SELECT *
FROM tutorial.oscar_nominees
LIMIT 25;
```

### a) Find how many different nominees are in the table.
<details>
  <summary>Solution</summary>

  ```SQL
  SELECT count(DISTINCT nominee)
  FROM tutorial.oscar_nominees
  ```

</details>

### b) Find the first/oldest 25 actress oscar winners by year.
<details>
  <summary>Solution</summary>

  ```SQL
  SELECT year, category, nominee, movie, winner
  FROM tutorial.oscar_nominees
  WHERE category = 'actress' AND winner = 'true'
  ORDER BY year ASC
  LIMIT 25;
  ```

</details>


### c) Use GROUP BY to see which movies have the most oscar winners.
<details>
  <summary>Solution</summary>

  ```SQL
  SELECT movie, year, COUNT(DISTINCT nominee), count(nominee)
  FROM tutorial.oscar_nominees
  WHERE winner = 'true'
  GROUP BY movie, year
  ORDER BY COUNT(DISTINCT nominee) DESC, year DESC
  LIMIT 25;
  ```

</details>