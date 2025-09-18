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
import numpy as np 
import matplotlib.pyplot as plt 
import seaborn as sns 

df = pd.read_csv("titanic_dataset.csv")
df
```

<img width="1333" height="455" alt="image" src="https://github.com/user-attachments/assets/d9d41a2a-ab0e-4154-b90a-8acb391a362d" />

```py
df.info()
```

<img width="379" height="383" alt="image" src="https://github.com/user-attachments/assets/50916edc-770d-43ea-90b4-940035dd97cb" />

```py
df.describe()
```

<img width="826" height="332" alt="image" src="https://github.com/user-attachments/assets/e1fc20b6-c026-4c09-bab9-34e97b345260" />

```py
df.dtypes
```

<img width="215" height="466" alt="image" src="https://github.com/user-attachments/assets/547044bc-d72f-42ae-8959-a5eec2ad593d" />

```py
df.shape
```

<img width="96" height="24" alt="image" src="https://github.com/user-attachments/assets/a8879a48-4a21-4ece-a1ea-7178116ee0bc" />

```py
df.value_counts()
```

<img width="1364" height="504" alt="image" src="https://github.com/user-attachments/assets/30c70ad3-bd32-4c95-a12f-3047d52b71b0" />

```py
df['Age'].value_counts()
```

<img width="164" height="544" alt="image" src="https://github.com/user-attachments/assets/b9a6f054-0e76-498f-aa48-b356d36e054d" />

```py
df.set_index("PassengerId",inplace=True)
df
```


```py
df.nunique()
```

<img width="150" height="488" alt="image" src="https://github.com/user-attachments/assets/0fe51310-12a1-4054-a764-ad658f59d30c" />

```py
sns.countplot(data=df,x='Age')
```

<img width="575" height="432" alt="image" src="https://github.com/user-attachments/assets/33a0af74-a1af-4653-a935-ff3f32a8350b" />

```py
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
<img width="1245" height="507" alt="image" src="https://github.com/user-attachments/assets/df8ed5bf-59e1-413a-930f-5dfbbe26e41b" />

```py
sns.catplot(x='Gender',col='Survived',kind="count",data=df,height=5,aspect=1)
```

<img width="1008" height="490" alt="image" src="https://github.com/user-attachments/assets/c4e4b9d4-9d3a-441a-be44-09023656aeb7" />

```py
df.boxplot(column='Age',by='Survived')
df
```

<img width="1251" height="501" alt="image" src="https://github.com/user-attachments/assets/d380f0f1-fbaa-4345-b47d-d7c909472116" />

<img width="559" height="461" alt="image" src="https://github.com/user-attachments/assets/8a6163d7-1238-438f-a811-10a9e6adb2c6" />

```py
sns.scatterplot(x=df['Age'],y=df['Fare'])
```
<img width="571" height="432" alt="image" src="https://github.com/user-attachments/assets/8083219b-159d-4bc3-bdc7-6443de5cfacf" />

```py
plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="562" height="432" alt="image" src="https://github.com/user-attachments/assets/d6f4b955-ce31-42a1-81fb-1eec4153ce40" />


```py
sns.catplot(x='Pclass',y='Age',hue='Gender',col='Survived',kind='box',data=df)
```

<img width="1089" height="490" alt="image" src="https://github.com/user-attachments/assets/5b9c299b-9419-4e02-8489-d787106aa99b" />

```py
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```

<img width="527" height="418" alt="image" src="https://github.com/user-attachments/assets/b3d00009-1f66-458f-9647-fe17afe0f356" />


```py
corr=df.select_dtypes(include=np.number).corr()
sns.heatmap(corr)
```

<img width="527" height="418" alt="image" src="https://github.com/user-attachments/assets/aa867a40-12e4-4158-b85c-f1fa087b1b50" />



# RESULT
Thus, the Exploratory Data Analysis on the given data set was performed successfully.

# SUMMARY

