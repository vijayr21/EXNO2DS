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
df=pd.read_csv("/content/titanic_dataset.csv")
df
```

<img width="1102" height="382" alt="Screenshot (150)" src="https://github.com/user-attachments/assets/c877dadb-4729-43c8-9f01-df88301cef64" />

```
df.info()
```
<img width="519" height="316" alt="Screenshot (152)" src="https://github.com/user-attachments/assets/b65f75e7-8035-4b22-ba5d-d24d9f82f199" />


```
df.describe()
```
<img width="819" height="269" alt="Screenshot (153)" src="https://github.com/user-attachments/assets/51a8f537-ab21-488f-b5b7-c2c3dfb36582" />


```
df.dtypes
```
<img width="331" height="414" alt="Screenshot (154)" src="https://github.com/user-attachments/assets/eada6da2-7b82-49bd-9553-e066791c5afb" />


```
df.shape
```
<img width="1240" height="94" alt="Screenshot (155)" src="https://github.com/user-attachments/assets/e328d772-0bea-495d-bda0-38beb7a8a535" />


```
df.value_counts()
```
<img width="1135" height="391" alt="Screenshot (156)" src="https://github.com/user-attachments/assets/13b8f421-2f3a-46a9-88f8-61a1ae435998" />

```
df['Age'].value_counts()
```

<img width="240" height="443" alt="Screenshot (157)" src="https://github.com/user-attachments/assets/0763f64d-5d55-4bcf-8b8f-a6dce0481b7d" />


```
df.set_index("PassengerId",inplace=True)
df
```

<img width="1185" height="399" alt="Screenshot (158)" src="https://github.com/user-attachments/assets/6028729e-0912-4064-89a1-76a401e321a1" />

```
df.nunique()
```
<img width="214" height="372" alt="Screenshot (159)" src="https://github.com/user-attachments/assets/bf65943b-7978-4274-8928-9e4db88ef7f6" />


```
sns.countplot(data=df,x='Age')
```
<img width="718" height="414" alt="Screenshot (160)" src="https://github.com/user-attachments/assets/44cc4c35-0c34-4fbf-a81f-95463ef9e882" />


```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

<img width="1139" height="367" alt="Screenshot (161)" src="https://github.com/user-attachments/assets/245d04a5-9fc5-4857-9ec6-0798ba3434a6" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df)
```

<img width="888" height="414" alt="Screenshot (162)" src="https://github.com/user-attachments/assets/1b159dbb-f956-4434-aab3-549b98f9f0cf" />

```
df.boxplot(column="Age",by="Survived")
```
```
sns.scatterplot(x=df['Age'],y=df['Fare'])
```
```
sns.catplot(x='Pclass',y='Age',hue='Gender',col='Survived',kind="box",data=df)
```
```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```

        

# RESULT
        <<INCLUDE YOUR RESULT HERE>>
