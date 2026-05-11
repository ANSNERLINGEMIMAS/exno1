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
 
  
    

    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }


  
    
      
      SNO
      REGNO
      NAME
      DOB
      GENDER
      ADDRESS
      M1
      M2
      M3
      M4
      TOTAL
      AVG
    
  
  
    
      0
      1
      1220121
      ARUN
      2000-02-10
      MALE
      THANDALAM
      82.0
      81.0
      90.0
      NaN
      NaN
      NaN
    
    
      1
      2
      1220122
      BABU
      1999-01-25
      MALE
      KANCHIPURAM
      56.0
      61.0
      80.0
      56.0
      253.0
      84.333333
    
    
      2
      3
      1220123
      CHARAN
      2000.09.21
      MALE
      THANDALAM
      NaN
      59.0
      60.0
      70.0
      NaN
      0.000000
    
    
      3
      4
      1220124
      DEVA
      2000-11-09
      MALE
      POONAMALEE
      74.0
      79.0
      80.0
      74.0
      307.0
      102.333333
    
    
      4
      5
      1220125
      ESTER
      2000-11-21
      FEMALE
      CHITHUR
      92.0
      95.0
      96.0
      92.0
      375.0
      125.000000
    
    
      5
      6
      1220126
      FARHANA
      1999-03-05
      FEMALE
      THANDALAM
      91.0
      88.0
      90.0
      91.0
      360.0
      120.000000
    
    
      6
      7
      1220127
      GANI
      2000-10-02
      MALE
      KANCHIPURAM
      49.0
      51.0
      70.0
      49.0
      219.0
      73.000000
    
    
      7
      7
      1220127
      GANI
      2000-10-02
      MALE
      KANCHIPURAM
      49.0
      51.0
      70.0
      49.0
      219.0
      73.000000
    
    
      8
      8
      1220128
      HEMA
      1999-01-25
      FEMALE
      POONAMALEE
      95.0
      96.0
      90.0
      95.0
      376.0
      125.333333
    
    
      9
      9
      1220129
      INDRA
      2000.09.21
      FEMALE
      KANCHIPURAM
      64.0
      NaN
      NaN
      64.0
      NaN
      0.000000
    
    
      10
      10
      1220130
      JAHITH
      2000-11-09
      MALE
      THANDALAM
      34.0
      45.0
      50.0
      34.0
      163.0
      54.333333
    
    
      11
      11
      1220131
      KANI
      2000-11-21
      FEMALE
      CHITHUR
      96.0
      95.0
      96.0
      96.0
      383.0
      127.666667
    
    
      12
      12
      1220132
      LATHESSH
      1999-03-05
      MALE
      THANDALAM
      NaN
      68.0
      70.0
      70.0
      208.0
      69.333333
    
    
      13
      13
      1220133
      MANI
      2000-10-02
      MALE
      KANCHIPURAM
      71.0
      76.0
      NaN
      71.0
      NaN
      0.000000
    
    
      14
      14
      1220134
      NANI
      20001109
      MALE
      POONAMALEE
      79.0
      77.0
      80.0
      79.0
      315.0
      105.000000
    
    
      15
      15
      1220135
      NaN
      19990125
      NaN
      NaN
      NaN
      NaN
      NaN
      NaN
      0.0
      0.000000
    
    
      16
      16
      1220136
      PRATHAP
      20000921
      MALE
      KANCHIPURAM
      86.0
      84.0
      90.0
      86.0
      346.0
      115.333333
    
    
      17
      17
      1220137
      RAGHU
      20001109
      MALE
      POONAMALEE
      67.0
      64.0
      70.0
      NaN
      201.0
      67.000000
    
    
      18
      18
      1220138
      RATHI
      20001121
      FEMALE
      KANCHIPURAM
      81.0
      86.0
      90.0
      81.0
      338.0
      112.666667
    
    
      19
      19
      1220139
      SARVESH
      19990305
      MALE
      THANDALAM
      84.0
      87.0
      NaN
      84.0
      NaN
      0.000000
    
    
      20
      20
      1220140
      SANTHOSH
      20001002
      MALE
      KANCHIPURAM
      76.0
      69.0
      80.0
      76.0
      301.0
      100.333333
    
  


    

  
    

  
    
  
    

  
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  

    
      const buttonEl =
        document.querySelector('#df-db0577f9-b3ed-4012-ac01-9d4b26b0032d button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-db0577f9-b3ed-4012-ac01-9d4b26b0032d');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    
  


  
    
      .colab-df-generate {
        background-color: #E8F0FE;
        border: none;
        border-radius: 50%;
        cursor: pointer;
        display: none;
        fill: #1967D2;
        height: 32px;
        padding: 0 0 0 0;
        width: 32px;
      }

      .colab-df-generate:hover {
        background-color: #E2EBFA;
        box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
        fill: #174EA6;
      }

      [theme=dark] .colab-df-generate {
        background-color: #3B4455;
        fill: #D2E3FC;
      }

      [theme=dark] .colab-df-generate:hover {
        background-color: #434B5C;
        box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
        filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
        fill: #FFFFFF;
      }
    
    

  
    
  
    
    
      (() => {
      const buttonEl =
        document.querySelector('#id_069c8ecc-1b63-43f6-83fa-5a09786ffb8f button.colab-df-generate');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      buttonEl.onclick = () => {
        google.colab.notebook.generateWithVariable('data');
      }
      })();
    
  

    
  

# Result
          <<include your Result here>>
