# Pewlett Hackard Analysis
This report is an analysis into employee data in order to help Bobby’s manager. If he needs to be prepared for the “silver tsunami” as many current employees reach retirement age.

## Overview of Project
Our client wants us to look into the employee dataset and find out the following:-

* Determine the number of retiring employees per title.
* Identify employees who are eligible to participate in a mentorship program.


## Results
Lets take a closer look at the analysis and our findings:-

* This table shows us how many people are going to retire and their job titles. A lot of senior engineering position will be open and needs to be filled up.

  ![image](https://user-images.githubusercontent.com/93144225/146445039-145f2161-ac31-42f5-bf21-c101f6bf0e86.png)

* This is a [list](https://github.com/tanzimamin2/Pewlett-Hackard-Analysis/blob/main/Data/retirement_titles.csv) of employees who will be retiring soon. But, there are duplicate entries for some employees because they have switched titles over the years. As such we had to create another list mentioned underneath.

* This is the list of **unique** employees who will be retiring soon according to their titles. The image below is an exerpt from the [full table](https://github.com/tanzimamin2/Pewlett-Hackard-Analysis/blob/main/Data/unique_titles.csv)

  ![image](https://user-images.githubusercontent.com/93144225/146445629-0448fc78-740c-4c10-b4a1-20c72f1aa0fe.png)

* We made a **mentorship eligibility** table that holds the employees who are eligible to participate in a mentorship program. The image below is an exerpt from the [full table](https://github.com/tanzimamin2/Pewlett-Hackard-Analysis/blob/main/Data/mentorship_eligibilty.csv)

  ![image](https://user-images.githubusercontent.com/93144225/146473434-602c3d5e-0df6-4748-bce4-f1bae5d622a2.png)

## Summary
To summarize our report we must answer two important questions-

_**How many roles will need to be filled as the "silver tsunami" begins to make an impact?**_

If we run the code below we can see that there will be 90,398 people that may be retiring. If we add up the number of mentorship eligible employees we only get 1,549 employees. From these data we can conclude that more new people need to be trained as soon as possible, or the effects of the "silver tsunami" could cause major problems.

![image](https://user-images.githubusercontent.com/93144225/146482333-b6f774a5-539c-4fa9-854a-5881fd5d8e1f.png)

```
SELECT SUM(count) FROM retiring_titles;
```

_**Are there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees?**_

We ran the following code to count the number of employees eligible for mentorship program by title. We found that there are **zero** managers that are eligible for mentorship, this is a big problem. If any mangers retire without training someone to take their place it will be very inconvinient.

![image](https://user-images.githubusercontent.com/93144225/146481224-c4c24cf2-87ad-446d-8100-f09def976e62.png)

```
-- Employees eligible for mentorship program by title
SELECT COUNT(me.title), me.title
FROM mentorship_eligibility as me
GROUP BY me.title
ORDER BY COUNT(me.title) ASC;
```

## Links
  * Visit this [link](https://github.com/tanzimamin2/Pewlett-Hackard-Analysis) for the excel dataset and other resources.
   
