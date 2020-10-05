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
How many roles will need to be filled as the "silver tsunami" begins to make an impact?

Are there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees?


4275	"Engineer"
3869	"Senior Staff"
3750	"Staff"
3705	"Senior Engineer"
817	"Technique Leader"
564	"Assistant Engineer"
1	"Manager"

424	"Senior Staff"
396	"Engineer"
300	"Staff"
292	"Senior Engineer"
77	"Technique Leader"
60	"Assistant Engineer"


**Engineer** - There are 4275 Engineers retiring and 396 eligible mentors available to train thier replacements.  Each mentor would need to train 10 replacements which would not be ideal.

**Senior Staff** - There are 3869 Engineers retiring and 424 eligible mentors available to train thier replacements.  Each mentor would need to train 9 replacements which would not be ideal.

**Staff** - There are 3750 Engineers retiring and 300 eligible mentors available to train thier replacements.  Each mentor would need to train 12.5 replacements which would not be ideal.

**Senior Engineer** - There are 3705 Engineers retiring and 292 eligible mentors available to train thier replacements.  Each mentor would need to train 13 replacements which would not be ideal.

**Technique Leader** - There are 817 Engineers retiring and 77 eligible mentors available to train thier replacements.  Each mentor would need to train 11 replacements which would not be ideal.

**Assistant Engineer** - There are 564 Engineers retiring and 60 eligible mentors available to train thier replacements.  Each mentor would need to train 9.5 replacements which would not be ideal.

**Manager** - Since there is only one manager a suitable mentor should be easy to find.

