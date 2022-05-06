# Question 2

## Using the `tutorial.sf_crime_incidents_cleandate` Table

### Columns:
-- incident_num | category | description | day_of_week | date | time | pd_district | resolution | address | lon | lat | location | cleaned_date | id

### Test query

```SQL
SELECT *
FROM tutorial.sf_crime_incidents_cleandate
LIMIT 25;
```

### a) Query all the different categories of crimes. Display each only once.
<details>
  <summary>Solution</summary>

  ```SQL
  SELECT DISTINCT category
  FROM tutorial.sf_crime_incidents_cleandate
  ```

</details>

### b) Find all of the crimes that had happened in the 'PARK' district on a Sunday.
<details>
  <summary>Solution</summary>

  ```SQL
  SELECT category, descript, day_of_week, time, pd_district
  FROM tutorial.sf_crime_incidents_cleandate
  WHERE day_of_week = 'Sunday' AND pd_district = 'PARK';
  ```

</details>

### c) Use GROUP BY to count how many of each crime there is in the database.
<details>
  <summary>Solution</summary>

  ```SQL
  SELECT category, COUNT(category)
  FROM tutorial.sf_crime_incidents_cleandate
  GROUP BY category
  ORDER BY COUNT(category) DESC;
  ```

</details>
