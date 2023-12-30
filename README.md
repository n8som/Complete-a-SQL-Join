# Complete-a-SQL-Join

<h2>Activity overview</h2>

As a security analyst, I’ll often find that I need data from more than one table.

Previously, I learned that a relational database is a structured database containing tables that are related to each other.

SQL joins enable me to combine tables that contain a shared column. This is helpful when I need to connect information that appears in different tables.

In this lab activity, I’ll use SQL joins to connect separate tables and retrieve needed information.

Note: The terms row and record are used interchangeably.

<h2>Scenario</h2>

In this scenario, I’ll investigate a recent security incident that compromised some machines.

I am responsible for getting the required information from the database for the investigation.

Here’s how I’ll do this task: First, I’ll use an inner join to identify which employees are using which machines. Second, I’ll use left and right joins to find machines that do not belong to any specific user and users who do not have any specific machine assigned to them. Finally, I’ll use an inner join to list all login attempts made by all employees.

<h2>Task 1. Match employees to their machines</h2>

First, I must identify which employees are using which machines. The data is located in the machines and employees tables.

I must use a SQL inner join to return the records I need based on a connecting column. In the scenario, both tables include the device_id column, which I’ll use to perform the join.

1. Run the following query to retrieve all records from the machines table:

```SELECT *```
 
```FROM machines;```

![image](https://github.com/n8som/Complete-a-SQL-Join/assets/110139109/5d68ac15-7a84-4cf0-a2d5-0e5b6e6f9317)

I’ll note that this query is not sufficient to perform the join and retrieve the information I need.

2. Complete the query to perform an inner join between the machines and employees tables on the device_id column. Replace X and Y with this column name:

```SELECT *```

```FROM machines```

```INNER JOIN employees ON machines.device_id = employees.device_id;```

Note: Placing the employees table after INNER JOIN makes it the right table.

INNER JOIN returned 185 rows:

![image](https://github.com/n8som/Complete-a-SQL-Join/assets/110139109/c61479bd-766f-483a-9f86-64ed15f864d1)

![image](https://github.com/n8som/Complete-a-SQL-Join/assets/110139109/6d795fc6-4990-4330-9670-f2398855d4ba)

<h2>Task 2. Return more data</h2>

Now I must return the information on all machines and the employees who have machines. Next, I must do the reverse and retrieve the information of all employees and any machines that are assigned to them.

To achieve this, I’ll complete a left join and a right join on the employees and machines tables. The results will include all records from one or the other table. I must link these tables using the common device_id column.

1. Run the following SQL query to connect the machines and employees tables through a left join. I must replace the keyword X in the query:

```SELECT *```
 
```FROM machines```

```LEFT JOIN employees ON machines.device_id = employees.device_id;```

Note: In a left join, all records from the table referenced after FROM and before LEFT JOIN are included in the result. In this case, all records from the machines table are included, regardless of whether they are assigned to an employee or not.

NULL is the username for the last record returned:

![image](https://github.com/n8som/Complete-a-SQL-Join/assets/110139109/5188abe5-04df-4ac5-8ae3-f107bdf91954)

2. Run the following SQL query to connect the machines and employees tables through a right join. I must replace the keyword X in the query to solve the problem:

```SELECT *```
 
```FROM machines```

```RIGHT JOIN employees ON machines.device_id = employees.device_id;```

Note: In a right join, all records from the table referenced after RIGHT JOIN are included in the result. In this case, all records from the employees table are included, regardless of whether they have a machine or not.

areyes is the username for the last record returned;

![image](https://github.com/n8som/Complete-a-SQL-Join/assets/110139109/d5c390cd-ce00-4659-ad91-0a5988052984)

<h2>Task 3. Retrieve login attempt data</h2>

To continue investigating the security incident, I must retrieve the information on all employees who have made login attempts. To achieve this, I’ll perform an inner join on the employees and log_in_attempts tables, linking them on the common username column.

- Run the following SQL query to perform an inner join on the employees and log_in_attempts tables. Replace X with the name of the right table. Then replace Y and Z with the name of the column that connects the two tables:

```SELECT *```
 
```FROM employees```

```INNER JOIN log_in_attempts ON employees.username = log_in_attempts.username;```

Note: I must specify the table name with the column name (table.column) when joining the tables.

This query returns 200 records:

![image](https://github.com/n8som/Complete-a-SQL-Join/assets/110139109/e0f7b00d-c5b3-4b38-a646-7706dfe69e90)

<h2>Conclusion</h2>

I have completed this activity and should be able to use joins to combine data from multiple tables in a database.

I now have practical experience in using

- ```INNER JOIN```,
- ```LEFT JOIN```, and
- ```RIGHT JOIN```.

Great work using SQL joins to obtain the precise data I need.

