
# Ex-04-Multivariate-Analysis

# AIM

To perform Multivariate EDA on the given data set.

# Explanation:

Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM:

## STEP 1
Import the built libraries required to perform EDA and outlier removal.

## STEP 2
Read the given csv file

## STEP 3
Convert the file into a dataframe and get information of the data.

## STEP 4
Return the objects containing counts of unique values using (value_counts()).

## STEP 5
Plot the counts in the form of Histogram or Bar Graph.

## STEP 6
Use seaborn the bar graph comparison of data can be viewed.

## STEP 7
Find the pairwise correlation of all columns in the dataframe.corr()

## STEP 8
Save the final data set into the file

# PROGRAM
~~~

Name : kanimozhi s
Register Number : 212220220024

import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("SuperStore.csv")
df
df.info()
df.describe()
df.isnull().sum()
df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()
df.dtypes
sns.scatterplot(df['Row ID'],df['Sales'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
states=df.loc[:,["State","Row ID"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Row ID")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("ROW ID")
plt.show()
states=df.loc[:,["Segment","Row ID"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("ROW ID")
plt.show()
sns.barplot(df['Sales'],df['Ship Mode'],hue=df['Region'])
df.corr()
sns.heatmap(df.corr(),annot=True)
~~~


# OUTPUT

# DATA

![image](https://user-images.githubusercontent.com/129577149/230834108-cfacfbe8-0812-44df-be00-2dc859034871.png)

# Data.info

![image](https://user-images.githubusercontent.com/129577149/230834153-5f2dd265-f721-4e4d-9479-f94c4f23bc6b.png)

#  Data.describe

![image](https://user-images.githubusercontent.com/129577149/230834193-493cb455-1915-4fd2-99e0-bff4a128c061.png)

# Checking the null values and Cleaning it

![image](https://user-images.githubusercontent.com/129577149/230834283-757173eb-9f7f-493e-a086-f16666e2cab7.png)


![image](https://user-images.githubusercontent.com/129577149/230834309-cf3f4826-e25d-4aa7-8d6e-72f7ecf1fea8.png)

# DATA TYPES

![image](https://user-images.githubusercontent.com/129577149/230834387-02a1c0ee-699b-449b-a675-42ad07ab6ff6.png)

# SCATTER PLOT

![image](https://user-images.githubusercontent.com/129577149/230834499-1535e622-8962-4d35-8ff7-436dabd836b6.png)

# BAR PLOT

![image](https://user-images.githubusercontent.com/129577149/230834545-3ba959e2-2aa3-482d-bcad-43cf10b21588.png)

![image](https://user-images.githubusercontent.com/129577149/230835447-1d9a4d0d-b8d3-43d0-9f17-da55fe542108.png)

![image](https://user-images.githubusercontent.com/129577149/230835489-d6e31412-bf18-4bb1-93b2-0c36cb8ac333.png)

![image](https://user-images.githubusercontent.com/129577149/230835627-b9ce3717-0fc3-41cf-8d25-6a7d97c006fa.png)

#CORRELATION COEFFICIENT INTERPRETATION

![image](https://user-images.githubusercontent.com/129577149/230835692-ee1a5818-4a05-4fc1-9a45-a628550730f7.png)

# HEATMAP

![image](https://user-images.githubusercontent.com/129577149/230835863-74252742-6592-467c-89c0-d3b189f88c7c.png)

~~~
# RESULT

Thus we have read the given data and performed the multivariate analysis with different types of plots.
~~~






