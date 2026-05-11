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
<img width="309" height="262" alt="image" src="https://github.com/user-attachments/assets/a02ad4be-49f9-441a-904c-a670a0e62ffe" />

```
data.info()
```


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


```
data.describe()

```


<img width="299" height="112" alt="image" src="https://github.com/user-attachments/assets/921a5d22-b273-49d3-88ba-e070ab04b44b" /><br>
```
data.isnull()
```

<img width="262" height="262" alt="image" src="https://github.com/user-attachments/assets/c622640d-a103-4390-a5cd-a973dac63692" /><br>
```
data.notnull()
```
<img width="263" height="260" alt="image" src="https://github.com/user-attachments/assets/9d4e6998-a920-440e-a5ff-7d7370f529c1" /><br>
```
data.notnull().sum()
```

<img width="78" height="171" alt="image" src="https://github.com/user-attachments/assets/48d0a6eb-df91-4c52-ac75-64ba7a7352d9" /><br>
```
data.dropna()
```

<img width="327" height="169" alt="image" src="https://github.com/user-attachments/assets/fceda88b-099c-42b3-be0b-8b292d9d809a" /><br>
```
data.dropna(axis=1)
```

<img width="91" height="261" alt="image" src="https://github.com/user-attachments/assets/59d964db-d893-4f4f-a69f-2260d7e088a2" /><br>
```
data
```

<img width="314" height="266" alt="image" src="https://github.com/user-attachments/assets/0ade14f5-fa03-431b-9a64-020073263c9a" /><br>
```
data.dropna(inplace=True)
data
```

<img width="318" height="175" alt="image" src="https://github.com/user-attachments/assets/6a2920ff-139f-484c-9ffb-55b35abb647e" /><br>
```
import pandas as pd
data1=pd.read_csv("/content/Loan_data.csv")
data1
```

<img width="503" height="151" alt="image" src="https://github.com/user-attachments/assets/24951881-0de9-4e89-bbe3-5e6d685403ae" /><br>
```
data.fillna("Datascience")
```

<img width="326" height="167" alt="image" src="https://github.com/user-attachments/assets/ae6121a0-8aec-4818-a665-1ec359b82d88" /><br>
```
data1.fillna(method='ffill')
```

<img width="512" height="170" alt="image" src="https://github.com/user-attachments/assets/712448e9-1803-43b0-be00-a2cb17b175d7" /><br>
```
data
```

<img width="329" height="168" alt="image" src="https://github.com/user-attachments/assets/7eb648af-0356-4622-aaf8-dd91b6e3359e" /><br>
```
data=pd.read_csv("/content/SAMPLEIDS.csv")
data
```

<img width="314" height="265" alt="image" src="https://github.com/user-attachments/assets/bb3ab468-a89a-449b-b92e-3d86b30b40d7" /><br>
```
data.ffill()
```

<img width="317" height="257" alt="image" src="https://github.com/user-attachments/assets/06368e2d-c496-4e83-85a1-f93f835b24a0" /><br>
```
data=pd.read_csv("/content/SAMPLEIDS.csv")
data.bfill()
```

<img width="326" height="268" alt="image" src="https://github.com/user-attachments/assets/83c72b4c-a64e-4e1d-894d-9355f60300ed" /><br>
```
data['TOTAL'].fillna(method='bfill',inplace=True)
```

<img width="624" height="59" alt="image" src="https://github.com/user-attachments/assets/b1db6926-6bfd-4cee-9d16-2e9bc321e498" /><br>
```
data
```


<img width="338" height="260" alt="image" src="https://github.com/user-attachments/assets/7c5f7543-d7bf-433f-93ad-f9fdf0f1fe8a" /><br>
```
data['M4'].fillna(value=data['M4'].mean(),inplace=True)
```


<img width="624" height="51" alt="image" src="https://github.com/user-attachments/assets/706ead9e-4647-40bb-8422-295db4030534" /><br>
```
data
```


<img width="333" height="265" alt="image" src="https://github.com/user-attachments/assets/6403ae44-95b1-4fb7-b69e-57a64817d873" /><br>
```
data['M4'].fillna(value=data['M4'].median(),inplace=True)
```


<img width="631" height="50" alt="image" src="https://github.com/user-attachments/assets/a292934f-018c-4fd0-b35e-fb44e0484f05" /><br>
```
data
```



<img width="365" height="269" alt="image" src="https://github.com/user-attachments/assets/2bf02d34-c568-43aa-a87a-a3902a104a4b" /><br>
```
data['M4'].fillna(value=data['M4'].mode(),inplace=True)
```


<img width="630" height="53" alt="image" src="https://github.com/user-attachments/assets/d542323d-3ce2-4f9f-bd51-3382c8a329db" /><br>
```
data
```


<img width="334" height="262" alt="image" src="https://github.com/user-attachments/assets/a74b1a22-ab42-4a5e-9962-c7183fad106b" /><br>
























    
  

    
  

# Result

    The given dataset was successfully read and data cleaning operations were performed. Missing values, duplicate records, and inconsistent data entries were identified and handled appropriately. The cleaned dataset was then saved successfully into a new file for further analysis and processing.
