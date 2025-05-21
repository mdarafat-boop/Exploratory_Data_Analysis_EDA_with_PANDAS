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
### Answer : We've to know how many entries & how many colmns,datatype,etc. plese follow this code:
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

