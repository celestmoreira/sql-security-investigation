# Project Description 
In this lab activity, I worked as a security analyst investigating potentional security issues using SQL. The goal was to analyze login attempts and employee data to identify suspicious acitivity and determine which systems might require further security review or updates. 

Using SQL queries, I filtered login records based on time, date, and location, and queries employee information based on department and office location. This project helped me practice how SQL is used in real world security investigations and reinforced how filtering data can support incident response and access managment. 

# Task 1: Retrieve After Hours Failed Login Attempts 
In this task, I investigated failed login attempts that occurred after normal business hours. Since office hours end at 18:00, login attempts made after that time may indicate suspicious activity.

To identify these events, I queried the `log_in_attempts` table and filtered the data based on the time of the login attempt and whether the login was successful.

![After hours failed login attempts](screenshots/after_hours_failed_login_attempts.png)

## Explnation 
The condition `login_time > '18:00'` filters the results to only include login attempts that occurred after business hours.

The condition `success = FALSE` filters for failed login attempts. In MySQL and MariaDB, Boolean values are stored as `TRUE` or `FALSE`, which are represented internally as `1` and `0`. Using `FALSE` allows me to specifically retrieve unsuccessful login attempts. 

The `AND` operator ensures that both conditions must be true for a record to be returned. As a result, the query only shows failed login atempts that occurred after 18:00. 

# Task 2: Retrieve Login Attempts on Specififc Dates
In this task, I invesitgated login attempts related to a suspicoius event that occurred on `2022-05-09`. To get more context around this activity, I retrieved all login attempts that occurred on that day and the day before, `2022-05-08`.

To complete this task, I queried the `log_in_attempts` table and filtered the results based on the `login_date` column.

![Login Attempts ]