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
        import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
Screenshot 2024-03-09 111446

dt.info()
Screenshot 2024-03-09 111848

dt.shape
Screenshot 2024-03-09 111927

dt.set_index("PassengerId",inplace=True)
dt.describe()
Screenshot 2024-03-09 112037

dt.nunique()
Screenshot 2024-03-09 112112

dt["Survived"].value_counts()
Screenshot 2024-03-09 112211

per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
Screenshot 2024-03-09 112247

sns.countplot(data=dt,x="Survived")
Screenshot 2024-03-09 112334

dt
Screenshot 2024-03-09 113810

dt.Pclass.unique()
Screenshot 2024-03-09 112614

dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
Screenshot 2024-03-09 112728

sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
Screenshot 2024-03-09 112816

sns.catplot(x='Survived',hue="Gender",data=dt,kind='count')
Screenshot 2024-03-09 112845

dt.boxplot(column="Age",by="Survived")
Screenshot 2024-03-09 112906

sns.scatterplot(x=dt["Age"],y=dt["Fare"])
Screenshot 2024-03-09 113012

sns.jointplot(x="Age",y="Fare",data=dt)
Screenshot 2024-03-09 113049

fig,ax1=plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=dt)
Screenshot 2024-03-09 113142

sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
Screenshot 2024-03-09 113229

corr=dt.corr()
sns.heatmap(corr,annot=True)
Screenshot 2024-03-09 113316

sns.pairplot(dt)
Screenshot 2024-03-09 113415
# RESULT
        <<INCLUDE YOUR RESULT HERE>>
