# PowerBI-PWC_Virtual_Intership_Task-04

##Task-04 Diversity & Inclusion





###  *Table of Contents:

#### •		Problem Statement

#### •		Flow of work-:
```             
Step 1- Upload Data
             
Step 2-Cleaning data
            
Step 3-Transform data
             
Step 4-Load data 
```
#### •	Data Preparation
```
Data Modelling

Writing DAX 
```
#### •		Data Visualization

#### •		Data Analysis

#### •		Insights

#### •		Shareable link






#### •Problem Statement
Task is to do the following:

 •		Define relevant KPIs in hiring, promotion, performance and turnover, and create a visualisation.
 Write what you think some root causes of their slow progress might be.
 
 •		Currently, we get in touch after they have terminated the contract, but this is reactionary: it would be better to know in advance who is at risk.
 
Calculating the following measures could help to define proper KPIs:

 • # of men
 
 • # of women
 
•# of leavers

• % employees promoted (FY21)

• % of women promoted

• % of hires men

• % of hires women

• % turnover 

• Average performance rating: men

• Average Performance rating: women


#### •	Flow of work

##### Step 1- Upload Data

The Dataset used for this analysis was presented by PWC_Switzerland and available at their official website page - [Dataset_link]

##### Step 2-Cleaning data

Data transformation was done in Power Query and the dataset was loaded into Microsoft Power BI Desktop for modelling.The Customer Retention dataset is given by a table named:

•	Cdiversity and inclusion which has `32 columns and 500 rows` of observation

The tabulation below shows the Customer retention table with its column names and their description:

| Column Name	    | Description     | 
| ------------- | ------------- | 
| `Employee ID`        |Represents the unique number of the employee in the dataset|
| `Gender`         |Describes the gender of the employee |
| `Job Level after FY20 promotions` | Describes the job level of the employee after being promoted in FY20|
| `New hire FY20?` |	Describes if the employee is a new hire in FY20|
|`FY20 Performance Rating` |   Represents the performance rating of the employee in FY20|
| `Promotion in FY21?`                     |Describes if the employee is being promoted in FY21|
|  `In base group for Promotion FY21`	                    |Describes if the employee is being selected for promoted in FY21|
| `Target hire balance`	|Describes the target hire balance of the employee|
| `FY20 leaver?`              |	Describes if the employee is a leaver in FY20|
| `In base group for turnover FY20`	        |Describes if the employee is in a group for turnover in FY20|
| `Department @01.07.2020`	        |Describes the department each employee belongs to as at January 7, 2020|
| `Leaver FY`	        |Describes if the employee is a leaver in a FY|
| `Job Level after FY21 promotions`	        |Describes the job level of the employee after being promoted in FY21|
| `Last Department in FY20`	        |Describes the last department each employee belongs in FY20|
| `FTE group`	        |Describes if the employee belongs to a FTE group|
| `Time type`	        |Describes the contract type employee|
| `Department & JL group PRA status`	        |Describes the department and JL group PRA status of the employee|
| `Department & JL group for PRA`	        |Describes the department and JL group PRA of the employee|
| `Job Level group PRA status`	        |Describes the job level group PRA status of the employee|
| `Job Level group for PRA`	        |Describes the job level group PRA of the employee|
| `Time in Job Level @01.07.2020`	        |Describes the time in job level of the employee|
| `Job Level before FY20 promotions`	        |Describes the job level employee before being promoted in FY20|
| `Promotion in FY20?`	        |Describes if the employee is being promoted in FY20|
| `FY19 Performance Rating`	        |Describes the performance rating of the employee in FY19|
| `Age group`	        |Describes the age group of the employee|
| `Age @01.07.2020`	        |Represents the age of the employee as at January 07, 2020|
| `Nationality 1`	                       |Describes the nationality of the employee in state level|
| `Region group: nationality 1`	  |Describes the nationality of the employee in country level|
| `Broad region group: nationality 1`	  |Describes the nationality of the employee in regional level|
| `Last hire date`	     |	Describes the last hire date of the employee|
| `Years since last hire`		 |Represents the number of years since last hire of the employee|
| `Rand`		|generates random number for each entry in the dataset|

##### Step 3-Transform data
Data Cleaning and transformation for the dataset were done in power query as follows:
•	Each of the columns in the table was validated to have the correct data type.
•	Unnecessary rows were removed.
•	Unnecessary rows were filtered.

#### Data preparation: -

##### Data Modelling
After the dataset was cleaned and transformed, it was ready to be modelled.
•	The official dataset is marked as the `Pharma Group AG` table in the dataset.
       
•	Along with this, a separate table- `Basic Measuress` is created to store all the measures which we have used in this model.

`MEN_new_HIRES`-  it's  dim table which is created to store all the measures related to  men category in this model.

`women_new hires`-it's dim table which is created to store all the measures related to  women category in this model

##### Data Visualization

Data visualization for the datasets was done in Microsoft Power BI Desktop:

•	`KPI-1_Hiring`  : Shows the hiring history,age group wise distribution,job role wise male-female distribution,nationality wise female-male departmental distribution,and men-female distribution by Job level after FY21 promotion etc.


•	` KPI-2_Promotion` : shows gender distribution for FY20 promotion and FY21 promotion,Promotion by age group nationwise promotion etc.

•	` KPI-3 Performance rating` : shows average rating for FY19 & FY20 ,age group wise performance rating with gender distribution etc.

•	`KPI-4 Turnover` : shows turnover rate, # of levaers by gender,# of levers by time type,by last department, by year etc.

•	`Insights`: Insights and suggestions figured out from the above analysis which will help to made changes.
 
#### Data Analysis

Measures used in visualization are:

•	`# of leavers` = CALCULATE([#Total No.of employees],'Pharma Group AG'[FY20 leaver?]="Yes")

•	`#Total_employees_promoted_in_FY20` = CALCULATE(COUNT( 'Pharma Group AG'[Employee ID]),'Pharma Group AG'[Promotion in FY20?]="Y")

•	`# Total_employees_promted_in_FY21` = CALCULATE(COUNT('Pharma Group AG'[Employee ID]),'Pharma Group AG'[Promotion in FY21?]="Yes")

•	`#count after hiring` = 'Basic Measuress'[#Total_men] + [#Total_female]

•	`#Total No.of employees` = COUNT('Pharma Group AG'[Employee ID])

•	`#Total_female` = CALCULATE(COUNT('Pharma Group AG'[Employee ID]),'Pharma Group AG'[Gender]="female")

• `#Total_men` = CALCULATE(COUNTROWS('Pharma Group AG'),FILTER('Pharma Group AG','Pharma Group AG'[Gender]="male"))

•	`#Total_promted` = SUMX('Pharma Group AG',[# Total_employees_promoted_in_FY20]+[# Total_employees_promted_in_FY21])

•	`% employees promoted (FY21)` = DIVIDE(CALCULATE(COUNT('Pharma Group AG'[In base group for Promotion FY21]),FILTER('Pharma Group AG','Pharma Group AG'[Promotion in FY21?]="Yes")),[#Total No.of employees])*100

•	`% employees promoted in FY20` = DIVIDE(CALCULATE([#Total No.of employees],'Pharma Group AG'[Promotion in FY20?]="Y"),[#Total No.of employees])*100

•	`% employees promoted in FY21` = DIVIDE(CALCULATE([#Total No.of employees],'Pharma Group AG'[Promotion in FY21?]="Yes"),[#Total No.of employees])*100
•	`% MEN NEW HIRES` = DIVIDE(MEN_new_HIRES[men new hires count],[New_Hires])*100

•	`% of hires men` = DIVIDE([#Total_men],'Basic Measuress'[#Total_men]+[#Total_female])

•	`% of hires women` = DIVIDE([#Total_female],'Basic Measuress'[#Total_female]+[#Total_men])

•	`% of men promoted in FY20` = DIVIDE(CALCULATE([#Total No.of employees],FILTER('Pharma Group AG','Pharma Group AG'[Gender]="Male"),FILTER('Pharma Group AG','Pharma Group AG'[Promotion in FY20?]="Y")),[#Total No.of employees])

•	`% of men promoted in FY21` = DIVIDE(
CALCULATE([#Total No.of employees],
FILTER('Pharma Group AG','Pharma Group AG'[Gender]="Male"),   
FILTER('Pharma Group AG','Pharma Group AG'[Promotion in FY21?]="Yes")),[#Total No.of employees])

•	`% of women` = DIVIDE([#Total_female],([#Total_men]+[#Total_female]))*100

•	`% of women promoted in FY20` = DIVIDE(CALCULATE([#Total No.of employees],FILTER('Pharma Group AG','Pharma Group AG'[Gender]="Female"),FILTER('Pharma Group AG','Pharma Group AG'[Promotion in FY20?]="Y")),[#Total No.of employees])

•	`% of women promoted in FY21` = DIVIDE(
    CALCULATE([#Total No.of employees],
    FILTER('Pharma Group AG','Pharma Group AG'[Gender]="Female"),
    FILTER('Pharma Group AG','Pharma Group AG'[Promotion in FY21?]="Yes")),[#Total No.of employees])

•	`% total employees promoted` = DIVIDE(CALCULATE(COUNT('Pharma Group AG'[In base group for Promotion FY21]),'Pharma Group AG'[Promotion in FY21?]="Yes"), CALCULATE(COUNT('Pharma Group AG'[Promotion in FY21?]), 'Pharma Group AG'[In base group for Promotion FY21]="Yes"))

•	`% WOMEN NEW HIRES` = DIVIDE([total women hires count],[New_Hires])*100

•	`% women promoted` = DIVIDE(CALCULATE(COUNT('Pharma Group AG'[In base group for Promotion FY21]),'Pharma Group AG'[Promotion in FY21?]="Yes", 'Pharma Group AG'[Gender]="Female"), CALCULATE(COUNT('Pharma Group AG'[Promotion in FY21?]),'Pharma Group AG'[Promotion in FY21?]="Yes"))

•	`%_Turnover` = [# of leavers]/'Basic Measuress'[Avg of employee count]

•	`%Total_Promoted` = DIVIDE([#Total_promted],[#Total No.of employees])*100

•	`Average Performance Rating (men)` = CALCULATE(AVERAGE('Pharma Group AG'[FY20 Performance Rating]),'Pharma Group AG'[Gender]="Male")

•	`Average Performance Rating (women)` = CALCULATE(AVERAGE('Pharma Group AG'[FY20 Performance Rating]),'Pharma Group AG'[Gender]="Female")

•	`Average rating performance (FY19)` = AVERAGE('Pharma Group AG'[FY19 Performance Rating])

•	`Average rating performance (FY20)` = AVERAGE('Pharma Group AG'[FY20 Performance Rating])

•	`Avg of employee count` = ('Basic Measuress'[Count before hiring]+'Basic Measuress'[#count after hiring])/2

•	`Avg performance rating Men (FY19)` = CALCULATE(AVERAGE('Pharma Group AG'[FY19 Performance Rating]),'Pharma Group AG'[Gender]="Male")

•	`Avg Performance rating MEN(FY20)` = CALCULATE(AVERAGE('Pharma Group AG'[FY20 Performance Rating]),'Pharma Group AG'[Gender]="Male")

•	`Avg performance rating women (FY19)` = CALCULATE(AVERAGE('Pharma Group AG'[FY19 Performance Rating]),'Pharma Group AG'[Gender]="Female")

•	`Avg performance rating women (FY20)` = CALCULATE(AVERAGE('Pharma Group AG'[FY20 Performance Rating]),'Pharma Group AG'[Gender]="Female")

•	`Count before hiring = CALCULATE(COUNT('Pharma Group AG'[Employee ID]),'Pharma Group AG'[In base group for turnover FY20]="Y")
•	`FTE = CALCULATE(COUNT('Pharma Group AG'[FTE group]), FILTER('Pharma Group AG','Pharma Group AG'[FTE group]="Full Time"))

•	`MEN_new_HIRES` = FILTER('Pharma Group AG','Pharma Group AG'[Gender]="Male" && 'Pharma Group AG'[New hire FY20?]="Y")

•	`New_Hires` = CALCULATE(COUNT('Pharma Group AG'[Employee ID]),FILTER('Pharma Group AG','Pharma Group AG'[New hire FY20?]="Y"))

•	`Not FTE` = CALCULATE(COUNT('Pharma Group AG'[FTE group]),FILTER('Pharma Group AG','Pharma Group AG'[FTE group] <> "Full Time" ))

•	`total women hires count` = COUNTROWS('women_new hires')

•	`Turnover_YES` = calculate(COUNT('Pharma Group AG'[In base group for turnover FY20]),FILTER('Pharma Group AG','Pharma Group AG'[In base group for turnover FY20]="Y"))


### Insights

####As shown by Data Visualization, It can be deduced that:

•	The average performance rating of the employees decreased from to in FY20.. 

• Maximum hiring of employees  is done from Switzerland ,France & Germany respectively, hence in order to increase diversity need to hire talented employees from different part of globe.

• The slow progress in the executive level is of the fact  that only less than 20% female is promoted to this  managerial and executive roles. 

• Employee promotion rate is increase by 3% in FY21 than FY20.

• Performance rating is drop by 0.57 in FY20 than FY19

• FTE's are more likely to leave  as well as male as highly leaver than females.



### Suggestions

####To ensure progress in diversity and inclusion  in the executive level; 

• More women should be hired and most especially promoted because the gap in the ratio of men to women is quite large. 

• Forthe  Executive and Director position ,female employee count as well as the promotio  count is too low compared to male employee     hence more women should be hired as well as promoted.

 • Age group 30-39 has more rate of promotion compared to 40-49 age group, experience should be consider as one of the the one of the criteria for promotion checklist.



#### Dashboard image

| Figure 1 shows visualizations from `KPI-1_Hiring`|
| ----------- |
| ![image](https://github.com/Priyankamore-DA/PowerBI-PWC_Virtual_Intership_Task-04/blob/main/1.png)|

|Figure 2 shows visualizations from ` KPI-2_Promotion` |
| ----------- |
|![image](https://github.com/Priyankamore-DA/PowerBI-PWC_Virtual_Intership_Task-04/blob/main/22.png)|

|Figure 3 shows visualizations from ` KPI-3 Performance rating` |
| ----------- |
|![image](https://github.com/Priyankamore-DA/PowerBI-PWC_Virtual_Intership_Task-04/blob/main/3.png)|


|Figure 4 shows visualizations from `KPI-4 Turnover` |
| ----------- |
|![image](https://github.com/Priyankamore-DA/PowerBI-PWC_Virtual_Intership_Task-04/blob/main/4.png)|

|Figure 5 shows visualizations from `Insights ` |
| ----------- |
|![image](https://github.com/Priyankamore-DA/PowerBI-PWC_Virtual_Intership_Task-04/blob/main/5.png)|

|Figure 6 shows visualizations from `Internship_Completion_Certificate` |
| ----------- |
|![image](https://github.com/Priyankamore-DA/PowerBI-PWC_Virtual_Intership_Task-04/blob/main/Screenshot%202023-04-07%20001630.png)
