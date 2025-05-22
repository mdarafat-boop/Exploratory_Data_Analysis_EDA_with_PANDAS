# Exploratory_Data_Analysis_EDA_with_PANDAS
## This repository contains 20 question for many kinds of query & analysis
### Firstly, we've read csv file with follow this code:
---
```python
import pandas as pd
import csv
cust = pd.read_csv('Cust_Purch_FakeData.csv')
```
---
---
### Secondly, we show first 5 row for the view of structure:
```python
cust.head(5)
```
---
---
### Question no. 1 : How many entries your data have? Can you tell the no. of columns in your data?
### Answer : We've to know how many entries & how many colmns, how many non null, null, datatype,etc. plese follow this code:
```python
cust.info
```
This output like this:
```output
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 30000 entries, 0 to 29999
Data columns (total 20 columns):
 #   Column      Non-Null Count  Dtype  
---  ------      --------------  -----  
 0   prefix      30000 non-null  object 
 1   first       30000 non-null  object 
 2   last        30000 non-null  object 
 3   email       30000 non-null  object 
 4   gender      30000 non-null  object 
 5   age         30000 non-null  int64  
 6   company     30000 non-null  object 
 7   profession  30000 non-null  object 
 8   phone       30000 non-null  object 
 9   postal      30000 non-null  object 
 10  province    30000 non-null  object 
 11  cc_no       30000 non-null  int64  
 12  cc_exp      30000 non-null  object 
 13  cc_type     30000 non-null  object 
 14  price(CAD)  30000 non-null  float64
 15  fav_color   30000 non-null  object 
 16  ip          30000 non-null  object 
 17  weekday     30000 non-null  object 
 18  ampm        30000 non-null  object 
 19  date        30000 non-null  object 
dtypes: float64(1), int64(2), object(17)
```
---
### Question no. 2 : What are the max and min ages of your customer? Can you find mean of your customer?
```python
print('The maximun ages of the customers: ',cust['age'].max())
print('The minimum ages of the customers: ',cust['age'].min())
print('The avarege ages of the customers: ',cust['age'].mean().round(2))
```
---
---
### Question no. 3: What are the three most common customer's names?
```python
cust['first'].value_counts().head(3)
```
---
---
### Question no. 4 : Two customers have the same phone number, can you find those customers?
```python
cust.groupby('phone')['first'].count().sort_values(ascending=False).head(1)
```
---
###Question no. 5 :  How many customers have profession "Structural Engineer"?
```python
cust[(cust['profession'] == 'Structural Engineer') & (cust['gender'] == 'Male')].count()['first']
```
---
---
### Question no. 6 : How many 'male' customers are 'Structural Engineer'?
```python
cust[(cust['profession'] == 'Structural Engineer') & (cust['gender'] == 'Male')].count()['first']
```
---
---
### Question no. 7 : Find out the female Structural Engineers from province Alberta (AB)?
```python
cust[(cust['profession'] == 'Structural Engineer') & (cust['gender'] == 'Female') & (cust['province'] == 'AB')].count()
```
---
---
### Question no. 8 : What is the max, min and average spending?
```python
print('The maximum spending: ',cust['price(CAD)'].max())
print('The minimum spending: ',cust['price(CAD)'].min())
print('The average spending: ',cust['price(CAD)'].mean().round(2))
```
---
---
### Question no. 9:  Who did not spend anything? Company wants to send a deal to encourage the customer to buy stuff!
```python
cust[cust['price(CAD)'] == 0.0]
```
---
---
### Question no. 10: As a loyalty reward, company wants to send thanks coupon to those who spent 100CAD or more, please find out the customers?
```python
cust[cust['price(CAD)'] >= 100.0]
```
---
###
---
