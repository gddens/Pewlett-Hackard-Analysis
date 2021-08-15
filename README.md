# Pewlett-Hackard Analysis
## Overview
The purpose of this analysis is to determine how many employees will potentially be retiring to help the company anticipate future hiring needs. The first deliverable was to aggregate a table of potential retiring employees by title, and then creating a table that had the number of potential retirees by each unique title. In the second deliverable, a table was made that listed potential eligible mentors to help train the new generation of employees that will be coming as older employees start to retire. 

## Results
* There is a total of 90,398 potential retirees per the sum of all Employee IDs on the "unique_titles" table.
* The two positions with the highest number of potential retirees are both senior level (Senior Engineer and Senior Staff):
![image](https://user-images.githubusercontent.com/86032451/129462362-29071c58-876d-419a-90a9-d004c8423bca.png)
* However, as seen in the screenshot above, only 2 Manager positions will need to be filled. 
* From the "mentorship_eligibility" table, there are 1549 eligible mentors. 

## Summary
While it is tempting to just simply state that 90,398 positions will need to be replaced based solely on the data from the "unique_titles" table, the data in that table is in fact misleading, as it didn't factor out employees that have already left the company. When updating the "unique_titles" query to include "from" and "to" dates, it becomes apparent that some employees have already left the company:

![image](https://user-images.githubusercontent.com/86032451/129462754-7aff05a1-e3ab-4615-85ea-174daaf218a3.png)

To remedy this, a condition was added to the code where only rows with an end date of '9999-01-01' are selected, and the resulting table exported as "unique_titles2":

![image](https://user-images.githubusercontent.com/86032451/129462790-8871258c-1bd7-48b0-893d-8542966a4d71.png)

The result of this is 72,458 potential retirees, which means somewhere between ~65,000 - 75,000 roles will need to be filled, based on project company growth, internal hires, and whether any positions will be made redundant due to automation, offshoring, etc. There's also the consideration of how the mentorship program can affect this since they will be kept on as part-time and therefore someone else may need to be hired to take over their normal job duties. 

To consider if there are enough mentors to mentor the next generation of Pewlett Hackard employees, another query and resulting table will need to be ran to determine how many mentors there are by department. This can be accomplished by refactoring the code that was ran to get the count of retirees by title and instead using it to get the count of mentors by title instead:

![image](https://user-images.githubusercontent.com/86032451/129462966-d9d22898-ee29-4e82-a828-2172c82ba5e8.png)

The result of this analysis is as follows:

![image](https://user-images.githubusercontent.com/86032451/129462973-05cb7f8d-3647-44f3-8a34-637d3f7a31b9.png)

While "Senior Engineer" had the highest number of potential retirees based on the original analysis, there are only 292 available mentors based on this most recent table, and there are currently no mentors available for the two "Manager" positions that will need to be filled (which remained unchanged after updating the "unique_titles" table), so more mentors will need to made available for the amount of new hires that could be coming into the company.
















