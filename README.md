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
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![Screenshot 2024-09-10 094600](https://github.com/user-attachments/assets/4850692b-fb6b-4224-9e78-6d98931b52c3)

```
df.info()
```
![Screenshot 2024-09-10 094610](https://github.com/user-attachments/assets/3fbfb445-660b-45ad-8130-75f5898df83a)


```
df.shape
```
![Screenshot 2024-09-10 094614](https://github.com/user-attachments/assets/9a9c8f8a-df28-4798-9f08-8bbfe3e89c9f)

```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![Screenshot 2024-09-10 094620](https://github.com/user-attachments/assets/0c582414-6b50-4b66-850e-fee7b5805eaf)


```
df.shape()
```
![Screenshot 2024-09-10 094627](https://github.com/user-attachments/assets/e5260e4a-6d9b-4a0e-897a-5c45617c95ae)

```
df.nunique()
```
![Screenshot 2024-09-10 094633](https://github.com/user-attachments/assets/dfeabe1f-6c81-49a8-aef2-59528d254eea)

```
df["Survived"].value_counts()
```
![Screenshot 2024-09-10 094638](https://github.com/user-attachments/assets/f3e915ed-e1b7-446a-9052-487cecfc44c4)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![Screenshot 2024-09-10 094643](https://github.com/user-attachments/assets/db71e648-7599-4ecf-b0ef-86fdfc8c7598)

```
sns.countplot(data=df,x="Survived")
```
![Screenshot 2024-09-10 094650](https://github.com/user-attachments/assets/a936a37a-a69f-4213-b0fc-bbbad44d2381)

```
df
```
![Screenshot 2024-09-10 094658](https://github.com/user-attachments/assets/a53f229c-147c-4538-a91b-83445df986e7)

```
df.Pclass.unique()
```
![Screenshot 2024-09-10 094705](https://github.com/user-attachments/assets/41a2d4dd-b331-4c18-8569-51894b707b49)

```

df.rename(columns={'sex':'Gender'},inplace=True)
df
```
![Screenshot 2024-09-10 094714](https://github.com/user-attachments/assets/208a2086-b4da-4501-8e6a-f21ff30d9541)

```
sns.catplot(x="Sex",col='Survived',kind="count",data=df,height=5, aspect=.7)
```
![Screenshot 2024-09-10 094722](https://github.com/user-attachments/assets/dd9172e9-0032-48b5-a096-2428c9462026)

```
sns.catplot(x='Survived',hue='Sex',data=df,kind='count')
```
![Screenshot 2024-09-10 094730](https://github.com/user-attachments/assets/bfb7ef17-73ca-4f3f-8bad-907cd7e7b4c3)

```
df.boxplot(column='Age',by="Survived")
```
![Screenshot 2024-09-10 094737](https://github.com/user-attachments/assets/2580ebc5-0c2f-43e6-9636-ebbf5bc988cd)


```
sns.scatterplot(x=df['Age'],y=df["Fare"])
```
![Screenshot 2024-09-10 094744](https://github.com/user-attachments/assets/1628fb24-13d9-4587-9ca4-01bb76c21fa5)

```
sns.jointplot(x="Age",y="Fare",data=df)
```
![Screenshot 2024-09-10 094809](https://github.com/user-attachments/assets/02a685b3-ac0d-4501-98f7-4b9622586db3)

```
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Sex',data=df)
```
![Screenshot 2024-09-10 094826](https://github.com/user-attachments/assets/04e0793a-4387-4128-a0ff-5e0cdc575e91)


```
sns.catplot(data=df,col='Survived',x='Sex',hue='Pclass',kind='count')
```
![Screenshot 2024-09-10 094834](https://github.com/user-attachments/assets/fed9ad02-2858-42d5-933d-231f24013610)

```
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![WhatsApp Image 2024-09-10 at 10 23 14 AM](https://github.com/user-attachments/assets/427fb877-54b4-446d-ad69-43231cb6a4ab)

```
sns.pairplot(df)
```
![pairplot](https://github.com/user-attachments/assets/4bfc0a2d-f0dc-4548-b992-620bcae70960)

# RESULT
We have performed Exploratory Data Analysis on the given data set successfully 
