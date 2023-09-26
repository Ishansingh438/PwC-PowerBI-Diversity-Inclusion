# PwC-PowerBI-Diversity-Inclusion
![image](https://github.com/Ishansingh438/PwC-PowerBI-Diversity-Inclusion/assets/105629591/3736cda4-450a-4431-9f5f-bf687d739340)


# Table of Contents:

• Problem Statement

• Data Preparation

• Data Analysis (DAX)

• Insights

# Problem Statement :
The purpose of this task is to:

Define proper KPIs in hiring, promotion, performance and turnover
Create a visualisation for the HR manager that reflects all relevant Key Performance indicators(KPIs) and metrics in the dataset.
Calculating the following measures could help to define proper KPIs:

Number of men
Number of women
Number of leavers
% employees promoted (FY21)
% of women promoted
% of hires men
% of hires women
% turnover
Average performance rating: men
Average Performance rating: women

# Data Preparation:
Completed the Data transformation in Power Query and the dataset loaded into Microsoft Power BI Desktop for modeling.

Diversity and Inclusion dataset is give table named:

Diversity and Inclusion dataset which has 500 rows and 31 Column of observation

Data Cleaning for the dataset was done in the power query editor as follows:

• Changed the header row of dataset

• Replaced the value is New hire FY20? N coverted No and Y converted Yes

• Replaced the value is In base group for turnover FY20 N coverted No and Y converted Yes

• Replaced the value is Promotion in FY20? N coverted No and Y converted Yes

• Removed Unnecessary columns

• Removed Unnecessary rows

• Each of the columns in the table were validated to have the correct data type

# Data Analysis (DAX):

Measures used in all visualization are:

#of leavers = CALCULATE(COUNTA('HR Manager'[Employee ID]), 'HR Manager'[Leaver FY] IN { "FY20" })

#of men =Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[Gender]="Male"))

#of women = Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[Gender]="Female"))

% employees promoted (FY21) =Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[Promotion in FY21?]="Yes")),Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[In base group for Promotion FY21]="Yes")))

% of hires men = Divide('HR Manager'[# of men],('HR Manager'[# of men]+'HR Manager'[# of women]))

% of hires women = Divide('HR Manager'[# of women],('HR Manager'[# of women]+'HR Manager'[# of men]))

% Promotees who were men = Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[Gender]="Male")),distinctcount('HR Manager'[Employee ID]))

% Promotees who were women = Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[Gender]="Female")),distinctcount('HR Manager'[Employee ID]))

% Turnover = Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[FY20 leaver?]="Yes")),Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[In base group for turnover FY20]="Y"))+Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager',NOT('HR Manager'[Department @01.07.2020]=BLANK()))),2))

Avg Rating Men = Calculate(Average('HR Manager'[FY20 Performance Rating]),Filter('HR Manager','HR Manager'[Gender]="Male"))

Avg Rating Women = Calculate(Average('HR Manager'[FY20 Performance Rating]),Filter('HR Manager','HR Manager'[Gender]="Female"))

I# nsights:

As shown the data Visualization, It can be deduced that:

♦ 41 % Female hires of the year and 59 % Male hires of the years.

♦ 53.8% of promoted were Female in the Junior Officer category, the highest for the year.

♦ 47% of promoted were Male in the Junior Officer category, the lowest for the year.

♦ Director is the highest Average time of job level promoted in this year.

♦ Finance department 22% highest turnover of the year.

♦ Average Rating Female 2.42%

♦ Average Rating Male 2.41%

♦ Employees promoted year of 2021 is 54.34% Male and 45.66% Female.

♦ The most common age group is 20-29 having 223 employees fall in this category.
