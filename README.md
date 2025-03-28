# Apply Filters to SQL Queries

### Project description

My organization is working to make its system more secure.  It is my responsibility to keep the system safe, investigate any potential security vulnerabilities, and upgrade employee computers as needed.  The steps below demonstrate how I used SQL with filters to complete security-related activities.

### Retrieve after hours failed login attempts

A potential security incident occurred after business hours (18:00).  All after-hours login attempts that fail must be scrutinized.

The code below shows how I developed a SQL query to filter for failed login attempts during business hours.

![image alt](https://github.com/mruiz4241/mruiz4241/blob/8598d47a2b3c547692da8a5b30cf7322d0f49b0b/Screenshot1SQL.jpg)

The first section of the screenshot depicts my query, while the second part shows a subset of the results.  This query looks for failed login attempts that happened after 18:00.  First, I selected all data from the `log_in_attempts` table.  Then, I used a `WHERE` clause with an `AND` operator to limit my results to login attempts that happened after 18:00 and were failed.  The first criteria is `login_time > '18:00'`, which screens for login attempts made after 18:00.  The second condition, `success = FALSE`, screens out failed login attempts.

### Retrieve login attempts on specific dates

On `2022-05-09`, a mysterious event occurred.  Any login activity that occurred on `2022-05-09` or the day prior should be investigated.

The code below shows how I developed a SQL query to filter for login attempts on specified dates.

The following code demonstrates how I created a SQL query to filter for login attempts that occurred on specific dates.

![image alt](https://github.com/mruiz4241/mruiz4241/blob/f9dc4a9d421292170616399fac43cdaa5e782be5/ScreenshotSQL2.jpg)

The first section of the screenshot depicts my query, while the second part shows a subset of the results.  This query returns all login attempts made on 2022-05-09 or 2022-05-08.  First, I selected all data from the `log_in_attempts` table.  Then, using a `WHERE` clause and an `OR` operator, I filtered my findings to show only login attempts made on either 2022-05-09 or 2022-05-08.  The first criteria is `login_date = '2022-05-09'`, which selects logins made on that date.  The second criteria is `login_date = '2022-05-08'`, which selects logins made on May 8, 2022.

### Retrieve login attempts outside of Mexico

After reviewing the organization's data on login attempts, I feel there is a problem with the login attempts made outside of Mexico.  These login attempts need to be investigated.

The following code explains how I wrote a SQL query to filter for login attempts made outside of Mexico.

![image alt](https://github.com/mruiz4241/mruiz4241/blob/ad90f5e883e4b7ff8a6b6ef28c5b4c5224cac5e7/ScreenshotSQL3.jpg)

The first section of the screenshot depicts my query, while the second part shows a subset of the results.  This query returns all login attempts made in countries other than Mexico.  First, I selected all data from the `log_in_attempts` table.  Then I used a `WHERE` clause with `NOT` to exclude nations other than Mexico.  I used `LIKE` with `MEX%` as the pattern to match because the dataset refers to Mexico as `MEX` and `MEXICO`.  When used with `LIKE`, the percentage sign (`%`) represents an unspecified number of characters. 

### Retrieve employees in Marketing

My team would like to refresh the computers of some Marketing department personnel. To achieve this, I need to know which employee machines to update.

The code below shows how I wrote a SQL query to filter for employee machines in the Marketing department in the East building.

![image alt](https://github.com/mruiz4241/mruiz4241/blob/45d76d5e9bf8df1c6e785bdccba927393974d656/ScreenshotSQL4.jpg)

The first section of the screenshot depicts my query, while the second part shows a subset of the results.  This query retrieves all workers from the Marketing department in the East Building.  First, I selected all data from the `employees` table.  Then I used a `WHERE` clause with `AND` to find employees who work in the Marketing department and in the East Building.  I used `LIKE` with `East%` as the pattern to match because the data in the office column corresponds to the East building and the specific office number.  The first criteria is the `department = 'Marketing'` section, which selects employees from the Marketing department.  The second requirement is the office `LIKE 'East%'` part, which selects personnel from the East building.

### Retrieve employees in Finance or Sales

The equipment for personnel in the Finance and Sales departments must also be updated.  Because a new security upgrade is required, I must obtain information on personnel exclusively from these two departments.

The code below shows how I constructed a SQL query to filter for staff machines in the Finance or Sales divisions.

![image alt](https://github.com/mruiz4241/mruiz4241/blob/7679ca64f085ced165ec424462030465578af67b/ScreenshotSQL5.png)

The first section of the screenshot depicts my query, while the second part shows a subset of the results.  This query retrieves all personnel from the Finance and Sales departments.  First, I selected all data from the `employees` table.  Then I used a `WHERE` clause with `OR` to look for personnel in the Finance and Sales departments.  I used the `OR` operator rather than `AND` because I want all employees to be in either department.  The first criterion, `department = 'Finance'`, searches for personnel in the Finance department.  The second criterion, `department = 'Sales'`, searches for employees in the Sales department.

### Retrieve all employees not in IT

My team needs to provide another security update to personnel who are not in the Information Technology department.  To make the modification, I first need to gather information about these employees.

The following displays how I wrote a SQL query to separate employee machines from employees who are not in the Information Technology department.

![image alt](https://github.com/mruiz4241/mruiz4241/blob/128f1360ed229b9fb2fac39948268403b7bd047a/ScreenshotSQL6.png)

The first section of the screenshot depicts my query, while the second part shows a subset of the results.  The query returns all employees who do not work in the information technology department.  First, I selected all data from the `employees` table.  Then, using a `WHERE` clause with `NOT`, I filtered for employees who did not work in this department.

# Summary

To obtain particular information about login attempts and employee machines, I used SQL queries with filters.  I utilized two separate tables: `log_in_attempts` and `employees`.  I used the `AND`, `OR`, and `NOT` operators to find the exact information required for each assignment.  I also used the `LIKE` and percentage symbol (`%`) wildcards to look for patterns.
