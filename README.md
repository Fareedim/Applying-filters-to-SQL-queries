# Applying-filters-to-SQL-queries

## Project Description

My organization is working to make their system more secure. It is my job to ensure the system is safe, investigate all potential security issues,  and update employee computers as needed.  
The following steps provide examples of how I used **SQL with filters** to perform security-related tasks.

---

## Retrieve After-Hours Failed Login Attempts

There was a potential security incident that occurred after business hours (after 18:00). All after-hours login attempts that failed need to be investigated.

The following code demonstrates how I created a SQL query to filter for **failed login attempts** that occurred after business hours.

<img width="470" height="102" alt="capture1" src="https://github.com/user-attachments/assets/873934a7-00ea-4f23-a0a6-9923ce286ee7" />


The first part of the screenshot is my query, and the second part is a portion of the output. This query filters for failed login attempts that occurred after 18:00. First, I started by selecting all data from the `log_in_attempts` table. Then, I used a `WHERE` clause with an `AND` operator to filter my results to output only login attempts that occurred after 18:00 and were unsuccessful. The first condition is `login_time > '18:00'`, which filters for the login attempts that occurred after 18:00. The second condition is `success = FALSE`, which filters for the failed login attempts.

---

## Retrieve Login Attempts on Specific Dates

A suspicious event occurred on `2022-05-09`. Any login activity that happened on `2022-05-09` or on the day before needs to be investigated.

The following code demonstrates how I created a SQL query to filter for login attempts that occurred on specific dates.

<img width="939" height="204" alt="image" src="https://github.com/user-attachments/assets/840efde1-3990-44b1-afe4-bf5b7cc002e2" />


The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred on `2022-05-09` or `2022-05-08`. First, I started by selecting all data from the `log_in_attempts` table. Then, I used a `WHERE` clause with an `OR` operator to filter my results to output only login attempts that occurred on either `2022-05-09` or `2022-05-08`. The first condition is `login_date = '2022-05-09'`, which filters for logins on `2022-05-09`. The second condition is `login_date = '2022-05-08'`, which filters for logins on `2022-05-08`.

---

## Retrieve Login Attempts Outside of Mexico

After investigating the organization’s data on login attempts, I believe there is an issue with the login attempts that occurred outside of Mexico. These login attempts should be investigated.

The following code demonstrates how I created a SQL query to filter for login attempts that occurred outside of Mexico.

<img width="467" height="101" alt="Capture3" src="https://github.com/user-attachments/assets/b2724da0-75c3-4984-97a5-65fa5553d84f" />


The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred in countries other than Mexico. First, I started by selecting all data from the `log_in_attempts` table. Then, I used a `WHERE` clause with `NOT` to filter for countries other than Mexico. I used `LIKE` with `MEX%` as the pattern to match because the dataset represents Mexico as `MEX` and `MEXICO`. The percentage sign (`%`) represents any number of unspecified characters when used with `LIKE`.

---

## Retrieve Employees in Marketing

My team wants to update the computers for certain employees in the Marketing department. To do this, I have to get information on which employee machines to update.

The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Marketing department in the East building.

<img width="467" height="138" alt="Capture4" src="https://github.com/user-attachments/assets/0de022b5-baa9-4e17-b01b-6b433dbd98db" />


The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all employees in the Marketing department in the East building. First, I started by selecting all data from the `employees` table. Then, I used a `WHERE` clause with `AND` to filter for employees who work in the Marketing department and in the East building. I used `LIKE` with `'East%'` as the pattern to match because the data in the `office` column represents the East building with the specific office number. The first condition is the `department = 'Marketing'` portion, which filters for employees in the Marketing department. The second condition is the `office LIKE 'East%'` portion, which filters for employees in the East building.

---

## Retrieve Employees in Finance or Sales

The machines for employees in the Finance and Sales departments also need to be updated. Since a different security update is needed, I have to get information on employees only from these two departments.

The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Finance or Sales departments.

<img width="938" height="259" alt="image" src="https://github.com/user-attachments/assets/9689b7dd-4dac-42eb-93da-091961b514e0" />


The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all employees in the Finance and Sales departments. First, I started by selecting all data from the `employees` table. Then, I used a `WHERE` clause with `OR` to filter for employees who are in the Finance and Sales departments. I used the `OR` operator instead of `AND` because I want all employees who are in either department. The first condition is `department = 'Finance'`, which filters for employees from the Finance department. The second condition is `department = 'Sales'`, which filters for employees from the Sales department.

---

## Retrieve All Employees Not in IT

My team needs to make one more security update on employees who are not in the Information Technology department. To make the update, I first have to get information on these employees.

The following demonstrates how I created a SQL query to filter for employee machines from employees not in the Information Technology department.

<img width="468" height="123" alt="Capture6" src="https://github.com/user-attachments/assets/880bddf8-bfba-49a1-b430-d4fb745db683" />


The first part of the screenshot is my query, and the second part is a portion of the output. The query returns all employees not in the Information Technology department. First, I started by selecting all data from the `employees` table. Then, I used a `WHERE` clause with `NOT` to filter for employees not in this department.

---

## Summary

I applied filters to SQL queries to get specific information on login attempts and employee machines. I used two different tables, `log_in_attempts` and `employees`. I used the `AND`, `OR`, and `NOT` operators to filter for the specific information needed for each task. I also used `LIKE` and the percentage sign (`%`) wildcard to filter for patterns.






