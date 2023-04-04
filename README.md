# Ex-04-Multivariate-Analysis

# AIM
To perform Multivariate EDA on the given data set.

# Explanation
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM
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

# CODE

```

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
sbn.barplot(data=df, x="Postal Code",y="Ship Mode",hue="Region")
df.corr()
sbn.heatmap(df.corr(),annot=True)

```

# Output

## EDA-Superstore.csv

![11](https://user-images.githubusercontent.com/120620842/229703944-9f50d386-4f90-4de4-99bf-e09cc991530f.png)

## Displaying information about Dataset

![12](https://user-images.githubusercontent.com/120620842/229704101-6aad5a07-9572-4f25-ad70-5f1586fc4a9f.png)

## Checking the null values and Cleaning it

![12](https://user-images.githubusercontent.com/120620842/229704199-5b545348-2deb-4729-b811-b8431ca9ae28.png)

## Displaying datatypes of each features

![43](https://user-images.githubusercontent.com/120620842/229704535-c46adfff-360d-4075-b0c9-fddd0fbfcb01.png)

## Multivariate Analysis - Scatterplot

![44](https://user-images.githubusercontent.com/120620842/229704841-cd1400dd-3519-4080-a42b-bf3325c3d4c2.png)

## Multivariate Analysis - Barplot

![14](https://user-images.githubusercontent.com/120620842/229704975-58e5f694-b139-43b1-a1a7-b9f91816f0d7.png)

![15](https://user-images.githubusercontent.com/120620842/229705096-9db4f7c1-b7e1-4ffb-9f14-c5d4cef22ef8.png)

![16](https://user-images.githubusercontent.com/120620842/229705294-c9bdcc7c-a46f-4af5-ba18-8abe990e8a9b.png)

![45](https://user-images.githubusercontent.com/120620842/229705482-2dc729c1-11e6-4b95-896f-768cb9a6a685.png)

## Correlation Coefficient Interpretation using HeatMap

![17](https://user-images.githubusercontent.com/120620842/229705626-2f399da6-2acb-4603-a496-679684501352.png)

# RESULT
Thus the program to perform EDA on the given data set is successfully executed
