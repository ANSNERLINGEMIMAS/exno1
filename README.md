# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output
```
import pandas as pd
data=pd.read_csv("/content/SAMPLEIDS.csv")
data
```
<br>
<img width="309" height="262" alt="image" src="https://github.com/user-attachments/assets/a02ad4be-49f9-441a-904c-a670a0e62ffe" />

```
data.info()
```
<br>

```
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 21 entries, 0 to 20
Data columns (total 12 columns):
 #   Column   Non-Null Count  Dtype  
---  ------   --------------  -----  
 0   SNO      21 non-null     int64  
 1   REGNO    21 non-null     int64  
 2   NAME     20 non-null     object 
 3   DOB      21 non-null     object 
 4   GENDER   20 non-null     object 
 5   ADDRESS  20 non-null     object 
 6   M1       18 non-null     float64
 7   M2       19 non-null     float64
 8   M3       17 non-null     float64
 9   M4       18 non-null     float64
 10  TOTAL    16 non-null     float64
 11  AVG      20 non-null     float64
dtypes: float64(6), int64(2), object(4)
memory usage: 2.1+ KB
```
<br>
```
data.describe()
```



    
  

    
  

# Result
          <<include your Result here>>
