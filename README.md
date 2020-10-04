# Pewlett-Hackard-Analysis

## Overview
The purpose of this analysis is to determine the number of retiring employees per title and identify employees who are eligible to participate in a mentorship program. The results will be presented in a bulleted list.


## Results

* A new [TABLE](https://w3resource.com/PostgreSQL/create-table.php) named **retirement_titles** was created by selecting employees who were born between January 1, 1952 and December 31, 1955 from the **employees** table and the **titles** tables by utilisizing an [INNER JOIN](https://www.w3resource.com/PostgreSQL/postgresql-inner-join.php)  clause.  This result containes duplicates because some employees changes titles over thier career.

* A new [TABLE](https://w3resource.com/PostgreSQL/create-table.php) named unique_titles was created by selecting all records from the **retirement_titles** tables and utilizing the [DISTINCT ON](https://www.geekytidbits.com/postgres-distinct-on/)  function on the title column.  The [DISTINCT ON](https://www.geekytidbits.com/postgres-distinct-on/) function selected the most recent title for the employees.

* A new [TABLE](https://w3resource.com/PostgreSQL/create-table.php) named **retiring_titles** was created by selecting all of titles from the **unique_titles** titles [TABLE](https://w3resource.com/PostgreSQL/create-table.php) and utilizing the [COUNT()](https://w3resource.com/PostgreSQL/postgresql-count-function.php) function.  This [TABLE](https://w3resource.com/PostgreSQL/create-table.php) shows the count of employees by titles.

  ##### Retiring titles
  ![image_name](https://github.com/jh2010/Pewlett-Hackard-Analysis/blob/master/images/retiring_employees_title_count.png)

* A new [TABLE](https://w3resource.com/PostgreSQL/create-table.php) named **mentorship_eligibility** was created selecting all current employees with a **to_date** equal to **9999-01-01**.  This [TABLE](https://w3resource.com/PostgreSQL/create-table.php) shows all current employees that are about to retire and that are eligible to mentor other employees in the company.





## Summary
