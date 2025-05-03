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
import seaborn as sns
import matplotlib.pyplot as plt
df = pd.read_csv('/content/titanic_dataset (2).csv')
df
```
![alt text](<Output Screenshots/Screenshot 2025-04-30 184858.png>)
```
df.info()
```
![alt text](<Output Screenshots/Screenshot 2025-04-30 184906.png>)
```
df.shape
```
![alt text](<Output Screenshots/Screenshot 2025-04-30 184912.png>)
```
df.set_index("PassengerId", inplace=True)
df.describe()
```
![alt text](<Output Screenshots/Screenshot 2025-04-30 184920.png>)
```
df.nunique()
```
![alt text](<Output Screenshots/Screenshot 2025-04-30 184926.png>)
```
df["Survived"].value_counts()
```
![alt text](<Output Screenshots/Screenshot 2025-04-30 184931.png>)
```
per = (df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![alt text](<Output Screenshots/Screenshot 2025-04-30 184936.png>)
```
sns.countplot(data=df, x="Survived")
```
![alt text](<Output Screenshots/Screenshot 2025-04-30 184943.png>)
```
df
```
![alt text](<Output Screenshots/Screenshot 2025-04-30 184958.png>)
```
df.Pclass.unique()
```
![alt text](<Output Screenshots/Screenshot 2025-04-30 185006.png>)
```
df.rename(columns= {'Sex':'Gender'},inplace=True)
df
```
![alt text](<Output Screenshots/Screenshot 2025-04-30 185016.png>)
```
sns.catplot(x='Gender',col='Survived',data=df,kind='count',height=5,aspect=.7)
```
![alt text](<Output Screenshots/Screenshot 2025-04-30 185026.png>)
```
sns.catplot(x='Survived',hue='Gender',data=df, kind='count')
```
![alt text](<Output Screenshots/Screenshot 2025-04-30 185033.png>)
```
sns.boxplot(x='Survived', y='Age', data = df)
```
![alt text](<Output Screenshots/Screenshot 2025-04-30 185700.png>)
```
sns.scatterplot(x=df['Age'], y=df['Fare'])
```
![alt text](<Output Screenshots/Screenshot 2025-04-30 185709.png>)
```
sns.jointplot(x='Age',y='Fare',data=df)
```
![alt text](<Output Screenshots/Screenshot 2025-04-30 185746.png>)
```
fig,ax1 = plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',data=df,hue='Gender')
```
![alt text](<Output Screenshots/Screenshot 2025-04-30 185754.png>)
```
sns.catplot(data=df,col='Survived',x='Gender',hue='Pclass',kind='count')
```
![alt text](<Output Screenshots/Screenshot 2025-04-30 185805.png>)
```
num_df = df.select_dtypes(include='number')
corr = num_df.corr()
sns.heatmap(corr,annot=True)
```
![alt text](<Output Screenshots/Screenshot 2025-04-30 185811.png>)
```
sns.pairplot(df)
```
![alt text](<Output Screenshots/Screenshot 2025-04-30 185838.png>)
# RESULT
EDA Analysis using Python was completed and the results have been successfully verified.
