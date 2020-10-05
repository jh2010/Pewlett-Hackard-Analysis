# Pewlett-Hackard-Analysis

## Overview
The purpose of this analysis is to determine the number of retiring employees per title and identify employees who are eligible to participate in a mentorship program. The results will be presented in a bulleted list.


## Results

* **Retirement Titles** - A new [table](https://w3resource.com/PostgreSQL/create-table.php) named **retirement_titles** was created by selecting employees who were born between January 1, 1952 and December 31, 1955 from the **employees** table and the **titles** tables by utilisizing an [INNER JOIN](https://www.w3resource.com/PostgreSQL/postgresql-inner-join.php) clause.  This result containes duplicates because some employees changes titles over their career.

* **Unique Titles** - A new [table](https://w3resource.com/PostgreSQL/create-table.php) named **unique_titles** was created by selecting all records from the **retirement_titles** [table](https://w3resource.com/PostgreSQL/create-table.php) and utilizing the [DISTINCT ON](https://www.geekytidbits.com/postgres-distinct-on/)  function on the title column.  The [DISTINCT ON](https://www.geekytidbits.com/postgres-distinct-on/) function selected the most recent title for the employees.

* **Retiring Titles** - A new [table](https://w3resource.com/PostgreSQL/create-table.php) named **retiring_titles** was created by selecting all of the titles from the **unique_titles** titles [table](https://w3resource.com/PostgreSQL/create-table.php) and utilizing the [COUNT()](https://w3resource.com/PostgreSQL/postgresql-count-function.php) function.  This [table](https://w3resource.com/PostgreSQL/create-table.php) shows the count of employees by title.

  ##### Retiring titles
  ![image_name](https://github.com/jh2010/Pewlett-Hackard-Analysis/blob/master/images/retiring_employees_title_count.png)

* **Mentorship Eligibility** - A new [table](https://w3resource.com/PostgreSQL/create-table.php) named **mentorship_eligibility** was created by selecting all current employees with a **to_date** equal to **9999-01-01**.  This [table](https://w3resource.com/PostgreSQL/create-table.php) shows all current employees that are about to retire and that are eligible to mentor other employees in the company.


## Summary
After reviewing the output of the employees that are ready to retire, we established that there will be 16981 vacancies once the first wave of retirements start.

In order to establish wether or not there are enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees, we needed to create two additional tables and the results are listed below.

**Engineer** - There are 4275 Engineers retiring and 396 eligible mentors available to train thier replacements.  Each mentor would need to train 10 replacements.

**Senior Staff** - There are 3869 Engineers retiring and 424 eligible mentors available to train thier replacements.  Each mentor would need to train 9 replacements.

**Staff** - There are 3750 Engineers retiring and 300 eligible mentors available to train thier replacements.  Each mentor would need to train 12.5 replacements.

**Senior Engineer** - There are 3705 Engineers retiring and 292 eligible mentors available to train thier replacements.  Each mentor would need to train 13 replacements.

**Technique Leader** - There are 817 Engineers retiring and 77 eligible mentors available to train thier replacements.  Each mentor would need to train 11 replacements.

**Assistant Engineer** - There are 564 Engineers retiring and 60 eligible mentors available to train thier replacements.  Each mentor would need to train 9.5 replacements.

**Manager** - Since there is only one manager a suitable mentor should be easy to find.

Since we do not have sufficient information about mentors workload, we cannot determine wether or not the company will have enough mentors.
