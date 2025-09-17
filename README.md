# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT

```py
import pandas as pd
df=pd.read_csv("supermarket.csv")
df
```
<img width="1699" height="867" alt="image" src="https://github.com/user-attachments/assets/01ea8a21-6f5f-4ba5-8097-6369a22a5ea5" />

```py
df.info()
```

<img width="415" height="488" alt="image" src="https://github.com/user-attachments/assets/3c795ac4-8090-4951-8379-557fe993fc94" />

```py
df.describe()
```
<img width="460" height="338" alt="image" src="https://github.com/user-attachments/assets/881b3e32-94e1-4102-b4e6-1598b34ce22d" />

```py
df.shape
```
<img width="131" height="42" alt="image" src="https://github.com/user-attachments/assets/37399d7f-ceb3-4381-9a36-32257087616e" />

```py
df.isnull().sum()
```

```py
df1=df.copy()
df1['Order Date']  = pd.to_datetime(df1['Order Date'],format = "%d/%m/%Y")
df1['Ship Date'] = pd.to_datetime(df1['Ship Date'],format= "%d/%m/%Y")
df.info()
```

<img width="392" height="495" alt="image" src="https://github.com/user-attachments/assets/4ef892b8-c48b-4009-8935-d09bcab1b136" />

```py
df1['Order ID'].value_counts()
```
<img width="217" height="542" alt="image" src="https://github.com/user-attachments/assets/2f99322b-458a-4979-99c3-6631ec569d32" />

```py
df1.query('`Order ID` == "CA-2018-100111"')
```
<img width="1718" height="745" alt="image" src="https://github.com/user-attachments/assets/c031a820-b77f-4635-8444-f87eddf46e5a" />

```py
df1.query("`Order ID` == 'CA-2018-157987'")
```
<img width="1733" height="657" alt="image" src="https://github.com/user-attachments/assets/801b250a-3f96-4b18-b192-9567c155eb95" />

```py
df1.head()
```

<img width="1710" height="383" alt="image" src="https://github.com/user-attachments/assets/b15c35c4-e405-4ab9-976b-03b873f6c70d" />

```py
df1['Ship Mode'].unique()
```

<img width="701" height="65" alt="image" src="https://github.com/user-attachments/assets/7dcc2329-762d-4054-b316-26bf4f40d554" />

```py
import matplotlib.pyplot as plt
df1['Ship Mode'].value_counts().plot(kind='bar',figsize=(8,5),color='pink')
plt.title("Different Ship Mode")
plt.xlabel('Ship Mode')
plt.ylabel('Count')
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()
```

<img width="530" height="506" alt="image" src="https://github.com/user-attachments/assets/b14ca4cc-40ec-4c6c-a741-2166861def21" />

```py
df1.info()
```

<img width="790" height="489" alt="image" src="https://github.com/user-attachments/assets/20463cb2-f50b-4556-a97b-a2767cfe7574" />

```py
df1['Customer ID'].value_counts().head(1)
```

<img width="169" height="150" alt="image" src="https://github.com/user-attachments/assets/3078f4ad-f9d8-4699-95d5-4d73f4d4d085" />

```py
df1.query('`Customer Name` == "Seth Vernon"')['Ship Mode'].value_counts().plot(kind='bar')
```
<img width="556" height="523" alt="image" src="https://github.com/user-attachments/assets/61b5d8ec-b7a7-496a-8376-4a587a322f62" />

# RESULT
Thus, the Exploratory Data Analysis on the given data set was performed successfully.

