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
```
 import pandas as pd
 import numpy as np
 import matplotlib.pyplot as plt
 import seaborn as sns
 df=pd.read_csv('/content/titanic_dataset.csv')
 df
```
![image](https://github.com/user-attachments/assets/6a29483f-ed54-422d-ba7e-39a93ba6d764)
```
df.info()
```
![image](https://github.com/user-attachments/assets/4920a3db-84c8-4079-ab7c-6efdb1088085)
```
df.shape
```
![image](https://github.com/user-attachments/assets/7e53dbcf-94ff-4fcb-96f3-2ea9bd074307)
```
df.set_index('PassengerId',inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/17b9efc3-880e-4740-a7cb-629d8f909847)
```
df.shape
```
![image](https://github.com/user-attachments/assets/4bbfcd1e-da9c-4038-a230-f0adb68d543f)
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/5b43a461-6801-40eb-a2ab-57101540cc10)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/d8286bed-f958-45d5-b943-9db346668915)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/712ac0e2-064e-44e3-a8f6-e38b8caaed92)
```
 sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/2db305be-bcb7-4b99-9205-59e4b5f33937)
```
df
```
![image](https://github.com/user-attachments/assets/34a2f9fa-8d28-422f-aaf6-d2ab22dbc412)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/557ab235-0e52-4cb6-8b46-712123393ee0)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/410b28c1-0358-4af4-bc52-cdf133df653d)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/0cd66ba4-01e7-450c-85ca-0e1a88680a16)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/1dbe58bc-0fd5-4109-9e5a-231bd368026c)
```
 df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/1fd98dcd-bb50-4fc9-8a6b-fffdcd3c2f18)
```
 sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/8ab55a25-1f4f-4dcf-a764-27e8bf3b5f2f)
```
 sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/c75ea71a-41b4-4d84-acc6-70b3840a2011)
```
fig, ax1 = plt.subplots(figsize=(8,5))
 plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/f5af4bd8-bf68-49ee-bda6-f02c10bb3f23)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/56335146-2474-45fc-affd-7c396644fe68)
```
numerical_df = df.select_dtypes(include=np.number)
corr = numerical_df.corr()
sns.heatmap(corr, annot=True)
```
![image](https://github.com/user-attachments/assets/892e42f3-e064-4248-a034-ba28a1a4b347)

```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/424cfaba-aa5e-4b84-a248-c5d4ccf84754)

# RESULT
Thus, the Exploratory Data Analysis on the given data set was performed successfully.
