# Question 1

## Using the `tutorial.us_flights` Table

### Test query

```SQL
SELECT *
FROM tutorial.us_flights
LIMIT 25;
```

### a) Find all the flights that landed at SFO.
<details>
  <summary>Solution</summary>

  ```SQL
  SELECT *
  FROM tutorial.us_flights
  WHERE dest = 'SFO';
  ```

</details>

### b) How many flights landed at SFO?

<details>
  <summary>Solution</summary>

  ```SQL
  SELECT COUNT(*)
  FROM tutorial.us_flights
  WHERE dest = 'SFO';
  ```

</details>

### c) What is the average flight distance traveled? Duration(actual_elapsed_time)?

<details>
  <summary>Solution</summary>

  ```SQL
  SELECT AVG(distance)
  FROM tutorial.us_flights
  WHERE dest = 'SFO';
  ```

</details>

### d) Which `origin` has the most flights to SFO?

<details>
  <summary>Solution</summary>

  ```SQL
  SELECT COUNT(*)
  FROM tutorial.us_flights
  WHERE dest = 'SFO'
  GROUP BY origin
  ORDER BY DESC;
  ```

</details>