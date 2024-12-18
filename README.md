# Banking Data Analysis
### By - Aryan Singh

### Banking Data Analytics Project 2024 

Git-hub repository at: 
https://github.com/httpsaryan/Holistic-Data-Driven-Banking

- Jupyter Notebook: **Banking Project**
- Csv data sets: accountsdata.csv, branches.csv, customer_data.csv, kyc.csv, loans.csv, payments.csv, transactionsdata.csv

# Table of contents
1. [Introduction](#introduction)

2. [Project overview](#section2)
   
   2.1 [Objective](#sec2.1)
   - [Understand Customer Behaviour](#sec2.1.1)
   - [Assess Branch Performance](#sec2.1.2)
   - [Identify Optimization Opportunities](#sec2.1.3)

   2.2 [Data Sources](#sec2.2)

   2.3 [Tools/Libraries](#sec2.3)

3. [Data Understanding](#dataunderstanding)

   3.1 [Data Description](#description)

   3.2 [Data Quality Issues & Cleaning](#quality)

   3.3 [Summary Statistics](#stats)


4. [Relationship building](#relations)

5. [Insights](#insights)

6. [Action Steps](#actionsteps)

7. [Risk & it's solutions](#risk)



## 1. Introduction <a name="introduction"></a>
- This README describes work on the 7 Datasets of Banking for the Fundamentals of Data Analysis module assessment, which is due 15 December 2024. Resources used include Python and the associated packages Jupyter, numpy, matplotlib, seaborn, and Pandas, which are all part of the Python distribution.
- The analysis takes the form of a single Jupyter notebook of the filename given above. To view this file, download it from this repository and start Jupyter Notebook in the folder containing the file. Use the command **python -m notebook** on the command line.
- All csv files intended for inclusion in this README are located in the **csv folder** subdirectory of this repository.
- I have tried to structure the Jupyter Notebook and this README so that they have corresponding sections. However, I do not wish to merely repeat here what has been stated, but I have given the detailed process and what all I got to know through this analysis. I will endeavor to have this README as in-detailed work of the notebook and, hopefully, complement the analyses done there.

## 2. Project Overview <a name="section2"></a>
The primary goal of this analysis is to gain deep insights into the bank's operations and customer behavior by examining seven core data sets. Through comprehensive data analysis and modeling, we aim to:

### 2.1 Objective <a name="sec2.1"></a>

#### 2.1.1 Understand Customer Behaviour <a name="sec2.1.1"></a>
Gain a comprehensive understanding of customer interactions with the bank, including account activity, loan utilization, and payment habits. 

#### 2.1.2 Assess Branch Performance <a name="sec2.1.2"></a>
Evaluate the efficiency and effectiveness of individual branches based on key metrics such as customer footfall, transaction volume, and loan disbursals.

#### 2.1.3 Identify Optimization Opportunities <a name="sec2.1.3"></a>
Discover potential areas for improvement in customer experience, operational efficiency, and revenue generation.

### 2.2 Data Sources <a name="sec2.2"></a>
The dataset for this analysis comprises seven CSV files:
- accountsdata.csv: Contains detailed information about customer accounts, including account numbers, opening dates, account types, and balances.
- branches.csv: Provides information about the bank's branches, such as branch IDs, locations, and contact details.
- customer_data.csv: Stores demographic and contact information of customers, including names, addresses, phone numbers, and email addresses.
- kyc.csv: Contains Know Your Customer (KYC) documents and verification details for each customer.
- loans.csv: Includes loan details, such as loan amounts, interest rates, tenure, and repayment schedules.
- payments.csv: Records payment transactions, including payment dates, amounts, and payment modes.
- transactionsdata.csv: Contains transaction history for all accounts, including transaction dates, amounts, and transaction types.

### 2.3 Tools and Libraries <a name="sec2.3"></a>
The tool that we have used to do this analysis was Python (Jupyter Notebook) with the following libraries:
- Pandas - Used for Data Manipulation and Analysis
  1. Loading and cleaning the CSV datasets.
  2. Handling missing values and outliers.
  3. Transforming and aggregating data.
  4. Merging and joining datasets based on common keys (e.g., customer ID, branch ID).
  5. Calculating summary statistics (mean, median, mode, standard deviation).
  6. Visualizing data distributions using histograms, box plots, and scatter plots.
- Numpy - Used for numerical computations
  1. Performing array operations for efficient data manipulation.
  2. Implementing statistical calculations.
- Matplotlib and Seaborn - Used for Data Visualization to explore data patterns and trends
  1. Line plots to track trends over time (e.g., loan disbursals).
  2. Bar plots to compare categorical data (e.g., branch performance, customer segments).


## 3. Data Understanding <a name="dataunderstanding"></a>
To delve deep into the bank's operations and customer behavior, we embarked on a comprehensive exploratory data analysis (EDA) of the seven core datasets. This involved meticulously examining each dataset to understand its structure, identify potential data quality issues, and uncover underlying patterns.

### 3.1 Data Description <a name="description"></a>
### 1. Accounts:
- This dataset provides granular information about customer accounts, including account numbers, opening dates, account types, and balances. By analyzing this data, we can identify trends in account openings, closures, and balance fluctuations.
- It contains 1054 rows and 5 columns.
- Data types of these columns -> account_id, customer_id, branch_id: integer/numbers ; account_type: string/text/object ; balance: float/decimal

![Accounts](png/accounts.png)  


### 2. Branches:
- This dataset contains details about the bank's branch network, such as branch IDs, locations, and contact information. By studying this data, we can assess the geographical distribution of branches and their potential impact on customer accessibility.
- It contains 10 rows and 3 columns.
- Data types of these columns -> branch_id: integer/numbers ; branch_name, branch_address: string/text/object

![Branches](png/branches.png)


### 3. Customer Data:
- This dataset stores customers' demographic and contact information, including names, addresses, phone numbers, and email addresses. Analyzing this data allows us to understand the customer base and identify potential target segments.
- This file contains 1124 rows and 6 columns.
- Data types of these columns -> customer_id, phone: integer/numbers ; first_name, last_name, email, address: string/text/object

![Customers Data](png/customer_data.png)


### 4.  KYC:
- This dataset contains Know Your Customer (KYC) documents and verification details for each customer. By reviewing this data, we can ensure compliance with regulatory requirements and assess the quality of customer onboarding processes.
- This file contains 500 rows and 4 columns.
- Data types of these columns -> kyc_id, customer_id: integer/numbers ; aadhar_number: complex ; kyc_status: string/text/object

![KYC](png/kyc.png)


### 5. Loans:
- This dataset includes loan details, such as loan amounts, interest rates, tenure, and repayment schedules. Analyzing this data helps us understand the bank's lending portfolio, identify trends in loan disbursals, and assess credit risk.
- This file contains 550 rows and 6 columns.
- Data types of these columns -> loan_id, customer_id: integer/numbers ; loan_type, loan_status: string/text/object ; loan_amount, interest_rate: float/decimal

![Loans](png/loans.png)


### 6. Payments:
- This dataset records payment transactions, including payment dates, amounts, and payment modes. By analyzing this data, we can gain insights into customer payment preferences, identify potential payment issues, and optimize payment processes.
- This file contains 2000 rows and 3 columns.
- Data types of these columns -> payment_id, loan_id: integer/numbers ; payment_amount: float/decimal

![Payments](png/payments.png)


### 7. Transactions:
- This dataset contains transaction history for all accounts, including transaction dates, amounts, and transaction types. By analyzing this data, we can understand customer spending patterns, identify high-value customers, and detect potential fraudulent activities.
- This file contains 2061 rows and 4 columns.
- Data types of these columns -> transaction_id, account_id: integer/numbers ; transaction_type: string/text/object ; amount: float/decimal

![Transactions](png/transactions.png)



### 3.2 Data Quality Issues & Cleaning<a name="quality"></a>

#### Null and Duplicates Handling: Dealing with missing values

#### 1. Accounts: Null handling

![image](https://github.com/user-attachments/assets/0ae7a02d-b6b3-4211-a22a-721f8598c09e)


Columns      |  No. of Nulls  |
-------------|----------------|
account_id   |       11       |
customer_id  |       11       |
branch_id    |       11       |
account_type |       0        |
balance      |       0        |


![image](https://github.com/user-attachments/assets/cad8a84a-91e0-4480-ac4d-b0ef538006b3)


Here I'm dropping all values because filling all those 33 missing values will not make sense in this dataset

![image](https://github.com/user-attachments/assets/0004f407-104f-44b5-99ac-1dfad0a48908)


Columns after null dropping: 1043 entries
Data columns: 5


Sr  |  Column    |    Non-Null Count 
----|----------|-------------------- 
 0  | account_id  |  1043 non-null | 
 1  | customer_id |  1043 non-null |  
 2  | branch_id   |  1043 non-null | 
 3  | account_type | 1043 non-null | 
 4  | balance   |    1043 non-null | 


#### Duplicates handling

The total duplicated rows in the accounts dataset were 43.

![image](https://github.com/user-attachments/assets/0a2916f8-4d0b-4f35-aaa0-fbd853e7923c)

Dropping duplicates:

![image](https://github.com/user-attachments/assets/def677e4-7248-493f-b570-ec6e2b640db0)


Sr |  Column    |    Non-Null Count    
---|------------|-------------------  
 0 | account_id  |  1000 non-null  
 1 | customer_id |  1000 non-null   
 2 | branch_id  |   1000 non-null  
 3 | account_type | 1000 non-null   
 4 | balance   |    1000 non-null   


#### 2. Branches:
This dataset just has 10 rows and doesn't have any null missing values or any inconsistencies

#### 3. Customers: Null handling
In this dataset before handling null values and duplicates, I have removed the Phone column, because, in the phase of data understanding, I analyzed Phone column doesn't contribute to any insights or give any valuable information.

![image](https://github.com/user-attachments/assets/36dd4eb7-db8c-4e03-b980-66fe36ca2ece)




Column-wise null values

![image](https://github.com/user-attachments/assets/0e589beb-8c71-4a07-974b-b9b65d521e54)



Dropping all null values of this dataset

![image](https://github.com/user-attachments/assets/15199032-3056-45a5-9b9a-3ce32e219e33)




Sr |  Column   |    Non-Null Count    
---|-----------|--------------------   
 0 |  customer_id | 1119 non-null   
 1 |  first_name | 1119 non-null   
 2 |  last_name  | 1119 non-null   
 3 |  email    |   1119 non-null   
 4 |  address   |  1119 non-null   


#### Duplicates:

![image](https://github.com/user-attachments/assets/5d4e1e4b-3410-41d9-a194-ce7f2e17cd78)



Dropping all duplicates from the Customer dataset

![image](https://github.com/user-attachments/assets/fb3102aa-af0a-429f-a17b-6e37321e8402)





Sr | Column    |    Non-Null Count  
--- | ------   |    --------------  
 0 | customer_id | 1000 non-null  
 1 | first_name  | 1000 non-null    
 2 | last_name  |  1000 non-null   
 3 | email     |   1000 non-null   
 4 | address   |   1000 non-null


#### 4. KYC:
This dataset doesn't have any null, duplicates, or any inconsistencies

#### 5. Loans: Null handling

![image](https://github.com/user-attachments/assets/e9fedb81-3727-45c8-b7de-5f14e33d5f5d)


![image](https://github.com/user-attachments/assets/8f128376-8238-44fb-97ea-3c8036d43955)


![image](https://github.com/user-attachments/assets/f54304be-7032-4f1a-9305-fe415ee2905e)



#### Duplicates:

![image](https://github.com/user-attachments/assets/ccd2c610-58c3-4256-a6f7-02f449fdf2d7)





#### 6. Payments: Null handling

No null values in this dataset


![image](https://github.com/user-attachments/assets/206645d3-174f-465f-9285-25ce5f2fcbc5)




No duplicates in this dataset



![image](https://github.com/user-attachments/assets/ba9e2671-2cdb-4612-88a1-406de41c926a)




#### 7. Transactions: Null handling
No null values in this dataset

#### Duplicates:

![image](https://github.com/user-attachments/assets/4c857e20-749a-47aa-8717-48c6f015d6b1)


Dropping duplicates

![image](https://github.com/user-attachments/assets/db96dfdb-4272-41b3-929c-19bcb455d919)





### 3.3 Summary Statistics <a name="stats"></a>

#### 1. Accounts
![image](https://github.com/user-attachments/assets/a32ace53-cba4-4c15-b294-cc7b6b5f2aec)




#### 2. Customer
![image](https://github.com/user-attachments/assets/fa61d485-f1e3-4c3c-8419-886b4d4a4df6)




#### 3. KYC
![image](https://github.com/user-attachments/assets/96a75853-63ed-4ef0-bd1f-427d06231419)




#### 4. Loans
![image](https://github.com/user-attachments/assets/e5dfb84c-1a62-4a2e-a855-fa84462a22a8)




#### 5. Payments
![image](https://github.com/user-attachments/assets/18a6bc0f-f5cd-421c-adfa-8d26edd37e38)




#### 6. Transactions
![image](https://github.com/user-attachments/assets/bd391432-31f9-49f2-87bf-88c95258b416)




## 4. Relationship Building <a name="relations"></a>
Relationship building is like merging datasets, so that once the relation is been build between the datasets, then we can extract the information/insights for the analysis of this complete project.

To establish meaningful relationships between the datasets, we employed a comprehensive data integration strategy. By identifying common keys and leveraging the power of SQL joins, we were able to link related information across different tables. For instance, the customer_id field served as a primary key to connect customer_data.csv with accountsdata.csv, loans.csv, and transactionsdata.csv. Similarly, the branch_id field linked branches.csv with transactionsdata.csv. This integrated dataset provided a holistic view of customer behavior, branch performance, and overall bank operations. By combining data from multiple sources, we were able to uncover deeper insights and make more informed decisions.

A few dataset merging that I have used to establish relationships between datasets are:

![image](https://github.com/user-attachments/assets/9c1b1ac1-ff0e-4d12-8877-13d7b9e63060)


![image](https://github.com/user-attachments/assets/b376a54b-2e3a-4d29-a0eb-ed8577f82eab)


![image](https://github.com/user-attachments/assets/9ce4bbf5-9ba6-4ecf-afd8-53a62429d40b)


![image](https://github.com/user-attachments/assets/3cd63034-108b-49d7-a939-b4afffeaa838)


![image](https://github.com/user-attachments/assets/ffca5389-00b9-468d-9fbc-9962728af682)


![image](https://github.com/user-attachments/assets/9552cbaf-d3d9-4dbb-a2e8-cd37d8bd3215)




## 5. Insights <a name="insights"></a>

This section will be the culmination of my analysis. I have presented the key findings and actionable insights derived from the data exploration and modeling.

The Insights section is crucial in communicating the value of your analysis to stakeholders and demonstrating the potential impact of data-driven decision-making.


### Branch Performance Analysis

Firstly, I have added "Branch Performance Analysis" to highlight key findings on branch performance, such as identifying top-performing branches, identifying branches with high customer churn, and pinpointing areas for improvement in customer service.


#### 1. Total number of Savings and Current Accounts per Branch





Illustrates a clear distinction in the distribution of Savings and Current accounts across various branches. Savings accounts significantly outnumber Current accounts in almost all branches, indicating a higher inclination toward savings-oriented financial products among customers.

Key Observations and In-Depth Analysis

1. Savings Accounts Dominate Across Branches:

In all branches, Savings accounts have higher counts compared to Current accounts.
The highest count of Savings accounts is observed at branches N12n and O11r, both exceeding 80 accounts. Branches B16a, P14i, and R17i also report high Savings accounts, with counts hovering around 70-80 accounts.
This reflects customer behavior favoring savings, possibly due to their desire for long-term deposits, interest earnings, and financial security.

2. Current Accounts Show Limited Presence:

The number of Current accounts remains consistently low across branches, with no branch exceeding 75 accounts.
Branch N12n reports the highest number of Current accounts (around 75 accounts), making it an outlier compared to others where Current accounts are generally between 15-35.
Branches like R13n and P14i have the least number of Current accounts, with figures as low as 15-25 accounts, indicating relatively lower demand for Current accounts in those locations.

3. Branch-Specific Trends:

N12n is a standout branch, showing both the highest number of Current accounts (75) and a large number of Savings accounts. This indicates balanced financial activity across both account types in this branch.
Branches like R13n and B16a have a large gap between Savings and Current accounts, reflecting a stronger customer inclination toward savings products.
Consistency in Savings account dominance across all branches suggests a uniform trend in customer preferences across the regions.

Overall Insights

Savings accounts form the backbone of account distributions across branches, highlighting a customer preference for low-risk, interest-bearing accounts. This could be attributed to:
- Individual customers seeking financial security.
- Savings-related promotions or higher interest rates incentivizing deposits.

Current accounts are significantly fewer, suggesting:
- Limited business activity or a smaller commercial customer base in these regions.
- Lower demand for Current accounts, which are typically used for frequent transactions by businesses or organizations.


#### 2. Customer count per branch




This chart illustrates variations in customer engagement across different branches.

Key Observations and In-Depth Analysis

1. Branch-wise Customer Distribution:

Highest Customer Base: Branch O11r stands out with the highest customer count, suggesting strong customer engagement and potentially a larger market share in its region. This may be attributed to factors such as effective customer service, convenient location, or a wider range of products and services offered at this branch.
Lowest Customer Base: Branch P14i has the lowest customer count, indicating potential areas for improvement in customer acquisition and retention. Analyzing factors like accessibility, service quality, and marketing efforts in this branch is crucial to understanding and address the lower customer engagement.

2. Branch Performance Trends:

High-Performing Branches: Branches like O11r, N12n, and Y15a show consistently high customer counts, suggesting they are effectively attracting and retaining customers. These branches could serve as models for other branches to emulate their successful strategies.
Branches with Room for Improvement: Branches like P14i and R13n have lower customer counts, indicating a need for focused efforts to improve customer engagement. Analyzing factors like customer feedback, competitor analysis, and local market trends can provide valuable insights for improvement.


Overall Insights:
The analysis highlights the importance of understanding branch-level performance and customer engagement. By identifying high-performing branches and addressing the needs of branches with lower engagement, the bank can optimize its operations, enhance customer satisfaction, and drive overall business growth.


#### 3. Highest and lowest balance per branch 




This chart illustrates variations in account balances across different branches.

Key Observations and In-Depth Analysis

1. Branch-wise Balance Distribution:

- Branches with High Balances: Branch Y15a stands out with the highest overall balance, indicating a strong customer base with substantial deposits. This suggests effective customer acquisition and retention strategies in this region. Other branches with high balances like O11r and S19i also demonstrate strong customer engagement and financial activity.
- Branches with Low Balances: Branch B16a exhibits the lowest overall balance, indicating potential areas for improvement in customer acquisition and deposit mobilization. This branch may need targeted strategies to attract new customers, increase customer engagement, and encourage higher deposit balances.

2. Branch Performance Trends:

- High-Performing Branches: Branches with high balances like Y15a, O11r, and S19i can be considered high-performing branches. Analyzing factors like customer demographics, product offerings, and marketing efforts in these branches can provide valuable insights for replication in other branches.
- Branches with Room for Improvement: Branches like B16a and M20i with lower balances require focused attention to improve customer engagement and deposit mobilization. This could involve targeted marketing campaigns, personalized product offerings, and enhanced customer service.

Overall Insights:
The analysis highlights the importance of understanding branch-level performance and customer behavior. By identifying high-performing branches and addressing the needs of branches with lower balances, the bank can optimize its operations, enhance customer satisfaction, and drive overall business growth.



#### 4. Total balance per branch 




This chart illustrates variations in total account balances across different branches.

Key Observations and In-Depth Analysis

1. Branch-wise Balance Distribution:
- Branches with High Balances: Branchs O11r and Y15a stand out with the highest total balances, indicating strong customer bases with substantial deposits. This suggests effective customer acquisition and retention strategies in these regions, as well as a high level of customer financial activity.
- Branches with Lower Balances: Branch B16a exhibits the lowest total balance, suggesting potential areas for improvement in customer acquisition and deposit mobilization. This branch may need targeted strategies to attract new customers, increase customer engagement, and encourage higher deposit balances.

2. Branch Performance Trends:
- High-Performing Branches: Branches with high total balances like O11r and Y15a can be considered high-performing branches. Analyzing factors like customer demographics, product offerings, and marketing efforts in these branches can provide valuable insights for replication in other branches.
- Branches with Room for Improvement: Branches like B16a with lower balances require focused attention to improve customer engagement and deposit mobilization. This could involve targeted marketing campaigns, personalized product offerings, and enhanced customer service.


Overall Insights:
The analysis highlights the importance of understanding branch-level performance and customer behavior. By identifying high-performing branches and addressing the needs of branches with lower balances, the bank can optimize its operations, enhance customer satisfaction, and drive overall business growth.


#### 5. Balances across different account types per branch




This chart illustrates variations in account balances across different branches, segmented by account type (Current and Savings).

Key Observations and In-Depth Analysis

1. Branch-wise Balance Distribution:
- Branch O11r: This branch stands out with the highest total balances across both Current and Savings accounts. The Current account balance appears to be significantly higher, suggesting a strong customer base with high transaction volumes and a preference for transactional accounts.
- Branch B16a: This branch exhibits the lowest total balances across both Current and Savings accounts. This suggests lower customer engagement and deposit mobilization in this branch, potentially due to lower customer activity or a smaller customer base.
- Branch Y15a: This branch shows a relatively higher balance in Savings accounts compared to Current accounts. This suggests a customer base with a preference for savings-oriented financial products.

2. Branch Performance Trends:
- High-Performing Branches: Branches like O11r and Y15a can be considered high-performing branches based on their overall balance figures. Analyzing factors like customer demographics, product offerings, and marketing efforts in these branches can provide valuable insights for replication in other branches.
- Branches with Room for Improvement: Branches like B16a with lower balances require focused attention to improve customer engagement and deposit mobilization. This could involve targeted marketing campaigns, personalized product offerings, and enhanced customer service.

3. Branch-Specific Strategies:
- Branch O11r: Leverage its strong performance by expanding its product offerings, focusing on customer relationship management, and potentially expanding its branch size or service hours.
- Branch B16a: Implement targeted marketing campaigns to attract new customers, introduce attractive deposit schemes, and enhance customer service to improve engagement.
- Branch Y15a: Capitalize on the customer preference for savings by offering a wider range of savings products, such as fixed deposits, recurring deposits, and investment options.

The analysis highlights the importance of understanding branch-level performance and customer behavior. By identifying high-performing branches and addressing the needs of branches with lower balances, the bank can optimize its operations, enhance customer satisfaction, and drive overall business growth.


#### 6. Total no. of transactions processed per branch




Key Observations and In-Depth Analysis

1. Branches with High Transaction Volumes:
- Branch 1: Leads with the highest number of transactions at 220. This indicates high customer engagement and activity in this branch.
- Branch 8: Follows closely with 220 transactions, suggesting a similar level of high customer activity.
- Branch 2: Shows a significant transaction volume with 210 transactions.

2. Branches with Moderate Transaction Volumes:
- Branch 3: Has 190 transactions, indicating a moderate level of customer activity.
- Branch 6: Also shows moderate activity with 200 transactions.
- Branch 7: Records 190 transactions, similar to Branch 3.

3. Branches with Lower Transaction Volumes:
Branch 4: Has the lowest transaction volume with 150 transactions, suggesting lower customer engagement or activity in this branch.
Branch 5: Records 210 transactions, indicating moderate activity.
Branch 9: Shows 200 transactions, indicating moderate activity.
Branch 10: Has 190 transactions, indicating moderate activity.

4. Branch Performance Trends:
- High-Performing Branches: Branches 1, 2, and 8 are top performers in terms of transaction volume. Analyzing factors like customer demographics, product offerings, and marketing efforts in these branches can provide valuable insights for replication in other branches.
Branches with Room for Improvement: Branch 4 with the lowest transaction volume requires focused attention to improve customer engagement and activity. This could involve targeted marketing campaigns, personalized product offerings, and enhanced customer service.

Overall Insights:
The analysis highlights the importance of understanding branch-level transaction activity. By identifying branches with high and low transaction volumes, the bank can optimize resource allocation, enhance customer satisfaction, and drive overall business growth.



### Customer Behavior Analysis 

This project delves into customer behavior by analyzing key datasets such as accounts, transactions, loans, and payments. By examining these data points, we can gain valuable insights into how customers interact with the bank. This includes understanding customer spending and saving patterns, identifying high-value customers, segmenting customers based on their financial behavior and needs, and detecting potential fraud or anomalies. The analysis will enable the bank to tailor its products and services to individual customer preferences, enhance customer engagement, and improve overall customer satisfaction.


#### 1. Distribution of Customers by Account Type




The analysis of customer distribution by account type reveals a strong preference for Savings accounts among the bank's customer base.

Key Observations and In-Depth Analysis

1. Savings Accounts (600 Customers):
Savings accounts are the most popular account type, with a substantial 600 customers utilizing them.
This significant number indicates a strong inclination towards savings-oriented financial behavior among the bank's customer base.
Possible factors contributing to this preference include a focus on long-term financial security, interest-earning potential, and the ease of accessing funds when needed.

2. Current Accounts (350 Customers):
Current accounts are held by 350 customers, representing a smaller segment compared to Savings accounts.
This lower number may suggest a lower demand for transactional accounts, potentially due to a lower proportion of businesses and individuals with frequent transaction needs.
However, Current accounts still constitute a significant portion of the customer base, indicating their importance for a subset of customers.

Overall Insights:
The analysis highlights a clear preference for Savings accounts among the bank's customer base. While Savings accounts are currently dominant, there is potential for growth in the Current account segment. The bank can leverage these insights to tailor its product offerings, marketing strategies, and customer service to better meet the needs of its diverse customer base.



#### 2. Number of Customers having Active loan status




The analysis of customer distribution by loan type reveals that customers show a clear preference for Home loans over other types, followed by Personal loans and Auto loans. Each category holds a significant share of customers, but there is a noticeable variation in their proportions.

Key Observations and In-Depth Analysis

1. Home Loans (102 Customers):
Home Loans dominate the distribution with 102 active customers, indicating it is the most preferred loan type.
This trend suggests a strong demand for housing finance, possibly driven by favorable interest rates, real estate growth, or government incentives.
From a business perspective, this presents an opportunity to expand home loan offerings, target customers seeking housing finance, and provide tailored services like long-term repayment options and competitive interest rates.

2. Personal Loans (66 Customers):
Personal Loans account for 66 active customers, making it the second most popular loan type.
The popularity of personal loans could be due to their flexibility in usage, shorter approval processes, and increasing consumer needs for immediate financial support (e.g., medical emergencies, travel, or education).
Businesses can capitalize on this demand by offering competitive interest rates, flexible terms, and digital tools to expedite the loan approval process.

3. Auto Loans (71 Customers):
Auto Loans represent 71 active customers, placing it between Home and Personal Loans.
This indicates a significant demand for vehicle financing, possibly driven by the need for personal transportation.
The bank can capitalize on this demand by offering competitive interest rates, extended loan terms, and partnerships with car dealerships to enhance its auto loan offerings.

Overall Insights:
- Home Loans are the leading choice for customers, reflecting a growing interest in real estate and long-term investments.
- Personal Loans have a significant following, indicating a demand for flexible and readily available financing.
- Auto Loans represent a substantial market segment, highlighting the need for competitive financing options in this area.
By understanding these customer preferences, the bank can optimize its lending portfolio, tailor its product offerings, and improve its overall market share in the lending business.



### 3. Loan status of customers 





The pie chart titled "% of Loan Status of Customers" illustrates the distribution of loan statuses among the bank's customers, revealing a relatively balanced portfolio.

Key Observations and In-Depth Analysis

1. Active Loans (49.2%): Approximately 49.2% of the loans are currently active, indicating ongoing customer borrowing activity. This suggests a dynamic lending environment with a steady flow of new loans and ongoing loan servicing.
2. Closed Loans (50.8%): Around 50.8% of the loans have been closed, indicating successful loan repayment and completion of loan terms. This reflects the bank's ability to effectively manage loan portfolios and ensure timely loan repayments.

Overall Insights:
The near-equal distribution of active and closed loans indicates a healthy loan portfolio. The bank's focus on both originating new loans and effectively managing existing loans contributes to its overall financial health and sustainability.



#### 4. Type of Loans customers are preferring most





The analysis of customer distribution by loan type reveals that customers show a clear preference for Home loans over other types, followed by Personal loans and Auto loans. Each category holds a significant share of customers, but there is a noticeable variation in their proportions.

Key Observations and In-Depth Analysis

1. Home Loans (37.6%):

The Home Loan category dominates the distribution with 37.6% of the total customers, indicating it is the most preferred loan type.
This trend suggests a strong demand for housing finance, possibly driven by favorable interest rates, real estate growth, or government incentives.
From a business perspective, this presents an opportunity to expand home loan offerings, target customers seeking housing finance, and provide tailored services like long-term repayment options.

2. Personal Loans (32.4%):

Personal Loans account for 32.4% of customers, making it the second most popular loan type.
The popularity of personal loans could be due to their flexibility in usage, shorter approval processes, and increasing consumer needs for immediate financial support (e.g., medical emergencies, travel, or education).
Businesses can capitalize on this demand by offering competitive interest rates, flexible terms, and digital tools to expedite the loan approval process.

3. Auto Loans (30.0%):

The Auto Loan category represents 30.0% of customers, placing it slightly behind the other two loan types.
This lower share may indicate a relatively slower demand for vehicle financing, possibly due to changing transportation habits, rising fuel costs, or growth in car leasing models.
However, the auto loan market still holds potential, especially with increasing demand for electric vehicles (EVs) and the availability of financing options for them. Targeted campaigns promoting auto loans for EVs or new vehicles could help boost this segment.

Overall Insights:
Home Loans are the leading choice for customers, reflecting a growing interest in real estate and long-term investments.
Personal Loans follow closely, highlighting an increasing need for immediate and flexible financing.
Auto Loans remain significant but show a comparatively lower preference, signaling a need for strategies to stimulate demand in this sector.



#### 5. KYC Status of Customers





The distribution of customers based on their KYC (Know Your Customer) status reveals an uneven but relatively balanced spread across three primary categories:

- Completed
- Pending
- Under Review

Key Observations

1. Completed KYC Status (36.2%):

The largest proportion of customers fall under the "Completed" category, accounting for 36.2% of the total.
This indicates that a significant number of customers have successfully fulfilled their KYC requirements.
From a business perspective, this is a positive sign as these customers are compliant and ready to use the services without regulatory concerns.

2. Pending KYC Status (32.4%):

The "Pending" category, which forms 32.4% of the total, highlights a notable portion of customers whose KYC processes are yet to be completed.
This signals a potential backlog or delay in the verification process, which could impact customer onboarding timelines.
Addressing this group is critical for improving customer experience and ensuring regulatory compliance.

3. Under Review KYC Status (31.4%):

The "Under Review" category comprises 31.4%, representing customers whose documents or applications are being actively assessed.
This is an operational phase where businesses need to expedite review processes to move these customers either to the "Completed" category or provide feedback for further action.
Prolonged reviews could frustrate customers and increase churn rates.

Overall Insights:
A combined 63.8% of customers (Pending + Under Review) are in various stages of the KYC process, signaling significant room for improvement in speeding up KYC completion.
Prioritizing automation tools and streamlining the verification pipeline may help convert "Pending" and "Under Review" customers into "Completed" status faster.
While the 36.2% Completed figure is encouraging, improving this metric further would enhance customer satisfaction, reduce regulatory risks, and promote better business growth.




## 6. Actions Steps <a name="actionsteps"></a>

### Brach recommendation:
The analysis reveals a diverse landscape of branch performance across the bank's network. Branch O11r emerges as a top performer, boasting a high total balance (approximately 2,900,000), a significant number of customers (105), and a substantial transaction volume. This suggests strong customer engagement, effective marketing, and a wide range of services offered. In contrast, Branch B16a exhibits lower performance with a low total balance (around 1,800,000), a lower number of customers, and lower transaction volume. This indicates potential areas for improvement in customer acquisition, engagement, and service delivery.

Key Takeaways:

Branch Performance Variation: Significant variations exist in customer engagement, transaction volumes, account balances, and loan performance across different branches.
High-Performing Branches: O11r, Y15a, and S19i demonstrate strong performance across various metrics, including high customer counts, significant transaction volumes, and a balanced loan portfolio.
Branches with Room for Improvement: Branches like B16a and P14i require focused attention to enhance customer engagement, service delivery, and loan portfolio management.

Top 3 Performing Branches:
Branch O11r: High total balance, significant customer count, high transaction volume, and likely a balanced loan portfolio with a healthy mix of active and closed loans. This suggests strong customer engagement, effective marketing, and a wide range of services offered.
Branch Y15a: High total balance, a significant customer base, and a preference for savings products. This suggests strong customer engagement and a focus on long-term financial planning.
Branch S19i: High total balance and a significant number of customers. This indicates strong customer engagement and a potentially diverse product offering.

Bottom 3 Performing Branches:
Branch B16a: Low total balance, lower customer count, and lower transaction volume. This suggests potential areas for improvement in customer acquisition, engagement, and service delivery.
Branch P14i: Low customer count and potentially lower transaction volume. This indicates a need for focused efforts to improve customer engagement and attract new customers.
Branch R13n: While specific loan performance data is not provided, the lower overall balance and potentially lower transaction volume suggest areas for improvement in customer engagement and deposit mobilization.

Actionable Insights:
- Resource Allocation: Allocate resources strategically, prioritizing branches with high potential (O11r, Y15a, S19i) and providing targeted support to those with lower performance (B16a, P14i).
- Customer-Centric Approach: Tailor marketing and service offerings to the specific needs of customers in each branch.
- Performance Monitoring: Continuously monitor key performance indicators (KPIs) such as customer count, transaction volume, and account balances to track progress and identify areas for improvement.


### Customer recommendation:
The analysis reveals several key customer insights. Savings accounts are highly popular, with approximately 600 customers holding them, demonstrating a strong preference for savings-oriented financial behavior. Home loans are the most preferred loan type, with 102 active customers, followed by Personal Loans (66 customers) and Auto Loans (71 customers).

Key Takeaways:
- Savings-Oriented Customers: A significant portion of the customer base prioritizes savings, indicating a focus on long-term financial security.
- Strong Demand for Home Loans: Home loans are the most popular loan type, reflecting a significant demand for housing finance.
- Balanced Loan Portfolio: The loan portfolio exhibits a balanced distribution of active and closed loans, suggesting effective loan origination and recovery processes.

Actionable Insights:
- Leverage Savings Preference: Offer a diverse range of savings products, including high-yield accounts, fixed deposits, and retirement savings plans.
- Capitalize on Home Loan Demand: Expand home loan offerings with competitive interest rates and flexible repayment options.
- Enhance Current Account Features: Attract more customers to Current accounts by offering competitive interest rates, fee waivers, and innovative digital banking features.
- Improve Personal Loan Accessibility: Streamline the personal loan application process and offer flexible repayment options to cater to diverse customer needs.

Overall, understanding customer preferences for savings, loan types, and account usage is crucial for the bank to develop targeted products and services, enhance customer engagement, and drive sustainable growth.



## Risk and its solutions:

#### Risk: Customers_id 721, 835, 384 with multiple loans having “Pending”& "Under Review" KYC status are indeed a concern. This could indicate a lack of proper identity verification, potentially leading to fraud or default.

Elaboration:
- Lack of Proper Verification: Customers with "Pending" or "Under Review" KYC statuses have not undergone thorough identity verification checks. This creates significant risks:
- Fraudulent Applications: Individuals may have submitted false information to obtain loans, potentially leading to loan defaults or fraudulent activities.
Money Laundering: Loans could be used for illegal activities, such as money laundering, if proper identity verification is not conducted.
- Increased Risk of Default: Incomplete KYC information can hinder the bank's ability to assess risk accurately, potentially leading to loans being granted to high-risk borrowers with a higher likelihood of default.

Solutions:
- Stricter KYC Procedures: Implement robust and thorough KYC procedures, including verification of identity documents, address verification, and employment verification.
- Regular KYC Audits: Conduct regular audits of KYC procedures to identify and address any gaps or inconsistencies.
- Real-time Monitoring: Implement real-time monitoring systems to flag accounts with incomplete KYC information and trigger immediate action.
- Automated Alerts: Set up automated alerts for loan applications from customers with incomplete or suspicious KYC information.

#### Risk: It’s important to have its income, debt-to-income ratio, and date in transaction data to ensure the complete and trustworthy process of repayment.

Elaboration:
- Incomplete Risk Assessment: Without access to income and debt-to-income ratio information, the bank cannot accurately assess a borrower's ability to repay the loan. This can lead to lending decisions that are not based on a comprehensive risk assessment.
- Limited Ability to Predict Default: The lack of income and debt-to-income ratio data limits the bank's ability to predict the likelihood of loan default. This can result in higher loan losses and increased credit risk.
- Difficulty in Monitoring Repayment Capacity: Without transaction data, it's difficult to track a borrower's repayment capacity and identify potential financial difficulties early on. This can hinder proactive measures to prevent loan defaults.

Solutions:
- Data Enrichment: Integrate income, debt-to-income ratio, and transaction data into the loan application and monitoring processes.
- Credit Bureau Integration: Leverage credit bureau data to obtain income and debt-to-income information for borrowers.
- Develop Predictive Models: Use historical data and machine learning techniques to develop predictive models that assess repayment risk based on various factors, including income, debt-to-income ratio, and transaction history.

#### Risk: Customer_id 835: has a low balance 7832.6 but has taken multiple loans, including a home loan and an auto loan, with relatively high-interest rates. This could suggest potential financial distress or predatory lending practices.

Elaboration:
- Potential Financial Distress: A low account balance combined with multiple loans, especially high-interest loans, can indicate potential financial distress. This customer may be struggling to manage their debt - obligations and could be at risk of default.
- Predatory Lending Practices: The combination of a low balance and multiple high-interest loans raises concerns about potential predatory lending practices. It is important to investigate whether the customer was appropriately informed about the terms and conditions of the loans and whether the loans were suitable for their financial situation.

Solutions:
- Conduct a Thorough Review: Conduct a thorough review of Customer_id 835's loan applications and account activity to assess the appropriateness of the loans and identify any potential signs of predatory lending.
- Offer Debt Counseling: If financial distress is suspected, offer debt counseling services to the customer to help them manage their debt and improve their financial situation.
- Review Lending Policies: Review and refine lending policies to ensure that loans are only granted to customers who can reasonably afford to repay them.

#### Risk: Customers_id 809 and 702 have a history of frequent withdrawals, which could indicate potential misuse of funds or financial instability.

Elaboration:
- Potential Misuse of Funds: Frequent withdrawals could indicate that the funds are being used for unintended purposes or may be indicative of fraudulent activity.
- Financial Instability: Frequent withdrawals, especially if accompanied by low account balances, could suggest financial instability or difficulty in managing finances.

Solutions:
- Transaction Monitoring: Implement transaction monitoring systems to identify unusual withdrawal patterns and flag suspicious activity.
- Customer Communication: Contact customers with frequent withdrawals to inquire about their financial situation and offer assistance if needed.
- Fraud Prevention Measures: Implement robust fraud prevention measures, such as fraud scoring models and real-time transaction monitoring, to detect and prevent fraudulent activity.

#### By addressing these risks proactively, the bank can mitigate potential losses, protect its customers, and maintain a healthy and sustainable lending portfolio.
