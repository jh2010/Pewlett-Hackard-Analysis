# Pewlett-Hackard-Analysis

## Overview
The purpose of this analysis is to determine the number of retiring employees per title and identify employees who are eligible to participate in a mentorship program. The results will be presented in a bulleted list.


## Results

A new [TABLE](https://w3resource.com/PostgreSQL/create-table.php) named **retirement_titles** was created by selecting employees who were born between January 1, 1952 and December 31, 1955 from the **employees** table and the **titles** tables by utilisizing an [INNER JOIN](https://www.w3resource.com/PostgreSQL/postgresql-inner-join.php)  clause.  This result containes duplicates because some employees changes titles over thier career.

A new [TABLE](https://w3resource.com/PostgreSQL/create-table.php) named unique_titles was created by selecting all records from the **retirement_titles** tables and utilizing the [DISTINCT ON](https://www.geekytidbits.com/postgres-distinct-on/)  function on the title column.  The [DISTINCT ON](https://www.geekytidbits.com/postgres-distinct-on/)  function selected the most recent title for the employee.

A new [TABLE](https://w3resource.com/PostgreSQL/create-table.php) named **retiring_titles** was created all of titles from the **unique_titles** titles [TABLE](https://w3resource.com/PostgreSQL/create-table.php) and utilizing the [COUNT()](https://w3resource.com/PostgreSQL/postgresql-count-function.php) function.

[TABLE](https://w3resource.com/PostgreSQL/create-table.php) 



retirement_titles.csv
unique_titles.csv
retiring_titles.csv
mentorship_eligibilty.csv


The retiring_titles tables shows that the Sr. Engineers and Sr. Staff retirements will have a big impact on the company.



### Place Holder
![image_name](https://github.com/jh2010/Pewlett-Hackard-Analysis/blob/master/images/retiring_employees_title_count.png)


## Summary
