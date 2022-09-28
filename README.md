# Ex-04-Multivariate-Analysis
# AIM
To perform Multivariate EDA on the given data set.

## Explanation
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM
# STEP 1
Import the built libraries required to perform EDA and outlier removal.

# STEP 2
Read the given csv file

# STEP 3
Convert the file into a dataframe and get information of the data.

# STEP 4
Return the objects containing counts of unique values using (value_counts()).

# STEP 5
Plot the counts in the form of Histogram or Bar Graph.

# STEP 6
Use seaborn the bar graph comparison of data can be viewed.

# STEP 7
Find the pairwise correlation of all columns in the dataframe.corr()

# STEP 8
Save the final data set into the file

## CODE
~~~
Name : Easwar.J
Register Number : 212221230024

import pandas as pd
import numpy as np
import seaborn as sbn
import matplotlib.pyplot as plt
df = pd.read_csv("/content/SuperStore.csv")
df.head(10)
df.info()
df.describe()
df.isnull().sum()
df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()
df.dtypes
sbn.scatterplot(df['Postal Code'],df['Sales'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sbn.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
states=df.loc[:,["State","Postal Code"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Postal Code")
plt.figure(figsize=(17,7))
sbn.barplot(x=states.index,y="Postal Code",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("Postal Code")
plt.show()
states=df.loc[:,["Segment","Sales"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Sales")
#plt.figure(figsize=(10,7))
sbn.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("SALES")
plt.show()
sbn.barplot(df['Postal Code'],df['Ship Mode'],hue=df['Region'])
df.corr()
sbn.heatmap(df.corr(),annot=True)
~~~
## OUTPUT

# EDA - SuperStore.csv
<img width="558" alt="k1" src="https://user-images.githubusercontent.com/94154683/192805324-ab0e2588-65db-4dc8-809b-0c127ffa3b54.png">


# Displaying information about Dataset
<img width="202" alt="k2" src="https://user-images.githubusercontent.com/94154683/192805368-64bd8ff0-e20c-48c2-8fe3-36748bd1c6b4.png">

# Checking the null values and Cleaning it
<img width="313" alt="k3" src="https://user-images.githubusercontent.com/94154683/192805681-d937df08-29f9-4463-a499-7ef686930466.png">


# Displaying datatypes of each features
<img width="116" alt="k4" src="https://user-images.githubusercontent.com/94154683/192805699-d3d7b642-7012-45a6-b4b5-a7d4695c8da5.png">

# Multivariate Analysis - Scatterplot
<img width="421" alt="k5" src="https://user-images.githubusercontent.com/94154683/192805750-18b3f714-1a63-424d-9806-07d6c3424923.png">


# Multivariate Analysis - Barplot
<img width="378" alt="k6" src="https://user-images.githubusercontent.com/94154683/192805760-cada4c2c-f973-4f8b-a325-1f35aa97b91f.png">
<img width="434" alt="k7" src="https://user-images.githubusercontent.com/94154683/192805778-9099d680-d0e4-49cf-b547-0ee51b7d9431.png">
<img width="422" alt="k8" src="https://user-images.githubusercontent.com/94154683/192805803-f7cb70d0-2618-4b78-a7bb-ad26db9e4ebd.png">

# Correlation Coefficient Interpretation using HeatMap
<img width="319" alt="k9" src="https://user-images.githubusercontent.com/94154683/192805842-82fefe67-5f32-4bcb-8240-7838dddf27bb.png">

## RESULT
Thus the program to perform EDA on the given data set is successfully executed.
