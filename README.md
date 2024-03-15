# EXNO2DS-Exploratory Data Analysis
## AIM:
  To perform Exploratory Data Analysis on the given data set.
      
## EXPLANATION:
 The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
## ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
### Developed by: KANISHKAR M
### Register no: 212222240044
```py
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns  
df=pd.read_csv("titanic_dataset.csv")
df
```
![image](https://github.com/KANISHKAR2607/EXNO2DS/assets/118886772/cbc6ff39-35dd-49dd-a0cd-117037d75fb4)


```py
df.info()
```
![image](https://github.com/KANISHKAR2607/EXNO2DS/assets/118886772/a7f4c211-ecce-486b-ae56-4c5da1e62762)


```py
df.shape
```
![image](https://github.com/KANISHKAR2607/EXNO2DS/assets/118886772/f4f935b6-380e-45b6-b4f9-d331575e93df)


```py
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/KANISHKAR2607/EXNO2DS/assets/118886772/47a96dfe-0311-4ac2-9d48-fff094ba076a)


```py
df.shape
```
![image](https://github.com/KANISHKAR2607/EXNO2DS/assets/118886772/c08b7c53-a1e4-4652-9dfc-f66731b060dd)


### Categorical data analysis
```py
df.nunique()
```
![image](https://github.com/KANISHKAR2607/EXNO2DS/assets/118886772/441e26e2-3f93-4718-bf52-05e59103306e)


```py
df["Survived"].value_counts()
```
![image](https://github.com/KANISHKAR2607/EXNO2DS/assets/118886772/50624d54-2a45-4a10-9ad5-0c5fa0103dc3)

```py
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/KANISHKAR2607/EXNO2DS/assets/118886772/dab227b9-b81e-47f7-81dd-1eef9e28af61)

```py
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/KANISHKAR2607/EXNO2DS/assets/118886772/b2bdd5b7-481b-46bb-8546-a2c27d05019b)

```py
df
```
![image](https://github.com/KANISHKAR2607/EXNO2DS/assets/118886772/88592867-d69d-4a5d-ae86-7d8dfa51dc9f)

```py
df.Pclass.unique()
```
![image](https://github.com/KANISHKAR2607/EXNO2DS/assets/118886772/7f4159bd-2c63-4f5d-baa6-1a85eeac2639)


```py
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/KANISHKAR2607/EXNO2DS/assets/118886772/0456afe7-0374-4b06-b87e-e912d4c364d4)


### Bivariate Analysis
```py
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/KANISHKAR2607/EXNO2DS/assets/118886772/74b64d86-3964-4108-8e02-bbad27507b76)


```py
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/KANISHKAR2607/EXNO2DS/assets/118886772/68f675f1-d3fa-4ea2-8204-ff686d841381)


```py
df.boxplot(column="Age",by="Survived")
```

![image](https://github.com/KANISHKAR2607/EXNO2DS/assets/118886772/04bc1139-16f7-4d8b-aadb-f9ccbdf3562b)


```py
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

![image](https://github.com/KANISHKAR2607/EXNO2DS/assets/118886772/9a62a6ee-97d5-478d-8b9e-99fb77f710cb)


```py
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/KANISHKAR2607/EXNO2DS/assets/118886772/f5248986-6bfa-4286-9c63-71b72b6850f0)


### Multivariate Analysis
```py
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/KANISHKAR2607/EXNO2DS/assets/118886772/e9befbd3-7dee-445b-970d-df3fc86fe761)


```py
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

![image](https://github.com/KANISHKAR2607/EXNO2DS/assets/118886772/ad4387d0-fb03-4f24-b484-d6a6a57c5f96)


# Co-relation
```py
corr=df.corr()
sns.heatmap(corr,annot=True)
```

![image](https://github.com/KANISHKAR2607/EXNO2DS/assets/118886772/ae70cf87-e7f3-415c-b727-5e3591ac19da)


```py
sns.pairplot(df)
```
![image](https://github.com/KANISHKAR2607/EXNO2DS/assets/118886772/5e3c59a9-b1a4-46a6-bdb7-9db8f3cd767d)


## RESULT
We have performed Exploratory Data Analysis on the given data set successfully.
