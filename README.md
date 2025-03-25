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
## Developed by: OVIYA N
## Register no: 212223040140
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/71f1c480-61b6-4fda-8afc-50f474cd1de8)
```
df.info()
```
![image](https://github.com/user-attachments/assets/6324b8c7-52a9-4f11-9bdd-79023a718914)
```
df.shape
```
![image](https://github.com/user-attachments/assets/f581fb90-1281-48c5-99d6-9a012c092252)
```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/545b101e-11bf-442c-a809-467fe523988c)
```
df.shape
```
![image](https://github.com/user-attachments/assets/8506b58e-8ec9-4d6f-895b-96f5fb317c48)
# Categorical data analysis:
```
df.nunique()
```
 ![image](https://github.com/user-attachments/assets/ee9c7d57-3234-4c69-94e7-7de2295623d0)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/11f489e5-a698-476b-8b76-1387c3456355)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/a4d4874a-06dc-4118-9ccc-b8deb1dc45c0)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/79dba162-9640-444b-83ef-d163f7f49f06)
```
df
```
![image](https://github.com/user-attachments/assets/ad91359e-ddc8-489f-8df9-b080a9ac6d49)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/44e20de3-63d1-4b49-8a22-8d30ddd91cba)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/d39cbce8-acb9-4939-8989-cad696673619)
# Bivariate Analysis:
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/29005bf8-40de-492c-9308-b0504442bee3)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/16348528-bf73-4bd2-92cb-12294424b87b)
```
df.boxplot(column="Age",by="Survived")
```
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/3da313b8-c194-47ea-9ded-9b3707c9cf45)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/d2fc9097-1ff6-48b3-ae07-a8e2f5cd3c88)
# Multivariate Analysis:
```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/75097e66-b683-43c2-84b4-869af31baa76)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/2ad8695b-b7fa-4e80-a93d-0c1d34a337cb)
```
numerical_data = df.select_dtypes(include=['number'])
sns.heatmap(numerical_data.corr(), annot=True)
```
![image](https://github.com/user-attachments/assets/07325b52-717c-419b-9f2b-824dc3b13d14)
```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/adeba821-ca43-4333-88f5-68d552ffc4e3)


# RESULT
   We have performed Exploratory Data Analysis on the given data set successfully
