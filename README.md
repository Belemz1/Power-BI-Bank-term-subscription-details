# Power-BI-Bank-term-subscription-details
## INTRODUCTION
This Power BI task involes importing and analysing the **Bank Term Deposit Subscription dataset**, applying some **DAX** functions, creating a conditional column and a dashboard.
## TASK
Using the ‘Bank Term Deposit Subscription’ dataset provided, carryout the following

- Create a measure for the ‘Average age of depositors’
- Create a new column named ‘Age band’ containing the following;
- ‘Young’ for ages below 30
- ‘Mid-aged’ for ages between 30 and 50
- ‘Old’ for ages above 50

Create a measure calculating the total balance for:
- Job: Technician
- Marital: Single and Married
- 
Create a measure to get the number of depositors on Loan

## STEPS
To get the average age of depositor, we apply this DAX query 
Average age of depositor = AVERAGE('bank-full'[age])
Then i proceeded in creating a new conditional column called **Age Band**

![](ageband.JPG)

Next we create a measure calculating the total balance for Technician by writting this DAX sybtax

- Total balance for Technician = CALCULATE(SUM('bank-full'[balance]),
FILTER('bank-full', 'bank-full'[job]="technician"))

Also we create more measures for the following

Marital: Single and Married

- Total balance for Married = CALCULATE(SUM('bank-full'[balance]),
  FILTER('bank-full','bank-full'[marital]="married"))
  
- Total balance for Single = CALCULATE(SUM('bank-full'[balance]),
FILTER('bank-full', 'bank-full'[marital]="single"))

- Depositors on loan = CALCULATE(COUNT('bank-full'[loan]),FILTER('bank-full','bank-full'[loan]="yes"))

- Depositors without loan = CALCULATE(COUNT('bank-full'[loan]),FILTER('bank-full','bank-full'[loan]="no"))

## DASHBOARD
After calculating the measure, i proceeded in creating the dashboard.In the design of this dashboard i made use of a gradient background, which i created on powerpoint.
I used the education column to create a slicer and also created 5 KPI's. The dashboard also features 4 charts. See dashboard below

![](Bank_term_deposit-1.png)

## CONCLUSION
I was able to create a catchy dashboard, which also conveys the key components needed from the table. 

