# PowerBi-Telecom-Customer-Retention-Dashboard
This project aims to assist the retention department of a telecom company in improving customer retention strategies by leveraging data-driven insights. The goal is to create a comprehensive Power BI dashboard that provides a clear, visual representation of key performance indicators (KPIs) related to customer retention.

## Objectives
**1.Define KPIs**: Identify and define relevant KPIs that provide insights into customer retention and risk factors.

**2.Create Dashboard**: Develop a Power BI dashboard reflecting these KPIs, making it easy for the retention manager to visualize and interpret the data.

**3.Provide Recommendations**: Offer actionable suggestions to enhance customer retention strategies based on the dashboard insights.

## Problem Statement
The telecom company faces difficulties in maintaining customer retention and effectively managing customer churn. Current methods are reactionary, with insufficient tools for proactive identification of at-risk customers.

## Data Source
The dataset used for this task was presented by [Pwc](https://www.pwc.in/) and the call centre trends dataset:
- Dataset: [Call Centre Trends](https://github.com/Jayanthkulal/PowerBi-Telecom-Customer-Retention-Dashboard/blob/main/02%20Churn-Dataset%20(1).xlsx)


## Data Preparation:

Completed the Data transformation in Power Query and the dataset loaded into Microsoft Power BI Desktop for modeling.
Churn dataset is give table named:

 - churn dataset has 23 columns and 7044 rows

  Data Cleaning for the dataset was done in the power query editor as follows:

 - Removed Unnecessary columns.
 - Removed Unnecessary rows.
 - Each of the columns in the table were validated to have the correct data type.

## Data Modeling:
And then dataset was cleaned and transformed, it was ready to the data modeled.
- The customer churn tables as show below:


![Screenshot 2024-09-17 224420](https://github.com/user-attachments/assets/49ca9687-e63b-46f9-b5f9-c7f4461a9c41)

## Data Analysis (DAX):

- % dependent = DIVIDE(CALCULATE(COUNT(Churn[Dependents]), Churn[Dependents]="yes", Churn[Churn]="yes"), CALCULATE(COUNT(Churn[Dependents]),Churn[Churn]="yes"),0)*100

- % device protection = DIVIDE(CALCULATE(COUNT(Churn[DeviceProtection]), Churn[DeviceProtection]="yes", Churn[Churn]="yes"),CALCULATE(COUNT(Churn[DeviceProtection]), Churn[Churn]="yes"),0)

- % online backup = DIVIDE(CALCULATE(COUNT(Churn[OnlineBackup]), Churn[OnlineBackup]="yes", Churn[Churn]="yes"),CALCULATE(COUNT(Churn[OnlineBackup]), Churn[Churn]="yes"),0)

- % online security = DIVIDE(CALCULATE(COUNT(Churn[OnlineSecurity]), Churn[OnlineSecurity]="yes", Churn[Churn]="yes"),CALCULATE(COUNT(Churn[OnlineSecurity]), Churn[Churn]="yes"),0)

- % phone service = DIVIDE(CALCULATE(COUNT(Churn[PhoneService]), Churn[PhoneService]="yes", Churn[Churn]="yes"),CALCULATE(COUNT(Churn[PhoneService]), Churn[Churn]="yes"),0)

- % phone service = DIVIDE(CALCULATE(COUNT(Churn[PhoneService]), Churn[PhoneService]="yes", Churn[Churn]="yes"),CALCULATE(COUNT(Churn[PhoneService]), Churn[Churn]="yes"),0)

- % SENIOR CITIZEN = DIVIDE(CALCULATE(COUNT(Churn[SeniorCitizen]), Churn[SeniorCitizen]=1, Churn[Churn]="YES"),CALCULATE(COUNT(Churn[SeniorCitizen]),Churn[Churn]="YES"),0)*100

- % streaming movies = DIVIDE(CALCULATE(COUNT(Churn[StreamingMovies]), Churn[StreamingMovies]="yes", Churn[Churn]="yes"),CALCULATE(COUNT(Churn[StreamingMovies]), Churn[Churn]="yes"),0)*100

- % streaming tv = DIVIDE(CALCULATE(COUNT(Churn[StreamingTV]), Churn[StreamingTV]="yes", Churn[Churn]="yes"),CALCULATE(COUNT(Churn[StreamingTV]), Churn[Churn]="yes"),0)

- % tech support = DIVIDE(CALCULATE(COUNT(Churn[TechSupport]), Churn[TechSupport]="yes", Churn[Churn]="yes"),CALCULATE(COUNT(Churn[TechSupport]), Churn[Churn]="yes"),0)

- %PARTNER = DIVIDE(CALCULATE(COUNT(Churn[Partner]),Churn[Partner]="yes", Churn[Churn]="yes"), CALCULATE(COUNT(Churn[Partner]),Churn[Churn]="yes"),0)*100

- churn rate % = DIVIDE(CALCULATE(COUNT(Churn[Churn]),Churn[Churn]="yes"), CALCULATE(COUNT(Churn[Churn]),ALLSELECTED(Churn[Churn])))

- Count of Churn for Yes =  CALCULATE(COUNTA('churn'[Churn]), 'churn'[Churn] IN { "Yes" })

- Multiple Lines no in % = DIVIDE(CALCULATE(COUNT(churn[MultipleLines]), churn[MultipleLines]="no", churn[Churn]= "Yes"), CALCULATE(COUNT(churn[MultipleLines]), churn[Churn]="Yes", churn[MultipleLines] <> "No phone service"),0)

- Multiple Lines yes in % = DIVIDE(CALCULATE(COUNT(churn[MultipleLines]), churn[MultipleLines]="Yes", churn[Churn]= "Yes"), CALCULATE(COUNT(churn[MultipleLines]), churn[Churn]="Yes", churn[MultipleLines] <> "No phone service"),0)*100

## Data Visualization (Dashboard):

Data visualization for the data analysis (DAX) was done in Microsoft Power BI Desktop:

Dashboard: View Dashboard

Shows visualizations from Customer Retention analysis:
Customer Churn
![Screenshot 2024-09-17 221459](https://github.com/user-attachments/assets/a68262a8-695e-4167-9e9e-83c216a00ba7)

Customer Risk

![Screenshot 2024-09-17 221512](https://github.com/user-attachments/assets/edc32856-a740-42d7-98f7-743ced011ff1)


## Insights:
As shown the data Visualization, It can be deduced that:


Out of the total customers, 1,869 are at risk of churn.


25.47% of customers are senior citizens, indicating a notable proportion of older customers.


57.30% use electronic checks, which could indicate a higher risk group. Companies should analyze if these customers face issues that could lead to churn.


55.48% of customers have been subscribed for less than a year, and this group likely has a high churn risk.


88.55% of customers are on a month-to-month contract, indicating a highly volatile customer base that could easily cancel services.


26.54% churn rate, which is significant and indicates an urgent need for retention strategies.


Fiber optic customers have the highest churn rate at 41.89%, suggesting potential issues with the service quality or pricing that need to be addressed.


Month-to-month contracts are associated with the highest churn rate (~45%), while one-year and two-year contracts exhibit significantly lower churn rates.


Customers with higher monthly charges tend to churn less. For example, churn rates decrease as monthly charges increase, indicating that customers who pay more tend to stay longer.







  
  
