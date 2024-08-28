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
![image](https://github.com/user-attachments/assets/6cc8bc4f-d3f5-4a92-8f0e-920a821e8b2e)
```
df.info()
```
![image](https://github.com/user-attachments/assets/9c246dac-1f95-4d3e-a5e0-d5a40d3e3c25)
```
df.shape
```
![image](https://github.com/user-attachments/assets/3f02363b-f515-4928-9f1a-9c64778d3a40)
```
import pandas as pd
df=pd.read_csv("/content/titanic_dataset.csv")
df.set_index("PassengerId",inplace=True)
print(df.set_index)
```
![image](https://github.com/user-attachments/assets/2114b0b1-757c-4ac4-a417-291c57471b0c)
```
df.describe()
```
![image](https://github.com/user-attachments/assets/23cdda74-97da-4893-9715-b7e51fcc8a33)
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/282a8199-ab4d-4d58-af46-5a9a230b8194)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/129bf268-e920-4b26-b637-7b5c45929320)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/d3e51749-608d-4c34-a5a6-d058982c2bc6)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/425bab29-b6d5-410e-ab9a-9623e4a2b1bb)
```
df
```
![image](https://github.com/user-attachments/assets/9376d185-1dfe-4981-beed-7b7d6fe00094)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/807707af-6dfc-465e-b193-f898f6ac1de6)
```
df.rename(columns={'sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/afb7cc6d-8d67-40b4-9205-55c86fe9f914)
```
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
sns.catplot(x="Sex",col='Survived',kind="count",data=df,height=5, aspect=.7)
```
![image](https://github.com/user-attachments/assets/741e4df4-dd49-49cc-bbff-0d40aeab8bd9)
```
sns.catplot(x='Survived',hue='Sex',data=df,kind='count')
```
![image](https://github.com/user-attachments/assets/b30cee77-7436-455f-bbd6-8d16c8388e76)
```
df.boxplot(column='Age',by="Survived")
```
![image](https://github.com/user-attachments/assets/3471acee-a949-49c0-8338-f01f71d97cf4)
```
sns.scatterplot(x=df['Age'],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/441eb904-ce45-4792-9be7-19cf0b4195d7)
```
import matplotlib.pyplot as plt
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Sex',data=df)
```
![image](https://github.com/user-attachments/assets/a8303a77-e573-4aab-8a5f-1a6c7c8983b7)
```
sns.catplot(data=df,col='Survived',x='Sex',hue='Pclass',kind='count')
```
![image](https://github.com/user-attachments/assets/664099dd-6d28-4c5c-a047-902a92738bbb)
```
import seaborn as sns
import pandas as pd

# Select only numeric columns for correlation calculation
numeric_df = df.select_dtypes(include=['number'])  # Select numeric columns only
corr = numeric_df.corr()

sns.heatmap(corr, annot=True)
```
![image](https://github.com/user-attachments/assets/2c07f4a4-3125-4701-a746-0787919a0b21)
```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/0210b185-3e5d-40b8-b74a-4cb73756e846)


# RESULT
Thus the data analysis has been implemented succesfully.  
