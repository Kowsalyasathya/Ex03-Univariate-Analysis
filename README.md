# Ex03-Univariate-Analysis

##Aim:

To read the given data and perform the univariate analysis with different types of plots.
##Explanation:

Univariate analysis is basically the simplest form to analyze data. Uni means one and this means that the data has only one kind of variable. The major reason for univariate analysis is to use the data to describe. The analysis will take data, summarise it, and then find some pattern in the data.
## Algorithm:
## Step 1:
Read the given data.
## Step 2:
Get the information about the data.
## Step 3:
Remove the null values from the data.
## Step 4:
Mention the datatypes from the data.
## Step 5:
Count the values from the data.
## Step 6:
Do plots like boxplots,countplot,distribution plot,histogram plot.
## Program

Developed by : Kowsalya M
Registration Number : 212222230069


import pandas as pd
import numpy as np
import seaborn as sns

df=pd.read_csv('/content/SuperStore.csv')
df

df.head()

df.info()

df.describe()

df.isnull().sum()

df.dtypes

df['Postal Code'].value_counts()

sns.boxplot(x='Postal Code', data=df)

sns.countplot(x='Postal Code',data=df)

sns.distplot(df["Postal Code"])

sns.histplot(x='Postal Code',data=df)

import matplotlib.pyplot as plt

df_count = df.groupby(by=["Category"]).count()
df_sum = df.groupby(by=["Category"]).sum()
labels=[]
for i in df_count.index:
    labels.append(i)
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
myexplode = [0, 0.2,0]
plt.pie(df_count["Sales"], colors = colors,explode = myexplode, labels=labels, autopct = "%0.0f%%",shadow = False) 
plt.show()

## Output:
![rec3 1](https://user-images.githubusercontent.com/118671457/228624951-3b5c28a5-28c5-44be-9a54-1bdfbfafdb8c.png)
![rec3 2](https://user-images.githubusercontent.com/118671457/228624999-622c883a-a936-4cc1-b842-c44b15fbe6f6.png)
![rec3 3](https://user-images.githubusercontent.com/118671457/228625020-c76c68b0-d505-41ca-8328-82ebdb06ff7e.png)
![rec3 4](https://user-images.githubusercontent.com/118671457/228625074-d0713c0a-51c4-473f-a52f-5c1f85a186af.png)
![rec3 5](https://user-images.githubusercontent.com/118671457/228625114-22c37e3c-1de1-4344-ba6f-dbc6908c0a69.png)
![rec3 6](https://user-images.githubusercontent.com/118671457/228625149-2a3f5b68-929e-4bbc-89a6-cca98ee3ec68.png)
![rec3 7](https://user-images.githubusercontent.com/118671457/228625384-5e529212-ca8c-4526-b0af-d1114d920ea1.png)
![rec3 8](https://user-images.githubusercontent.com/118671457/228625415-217d719f-3112-464d-9e6a-f586ccc080a8.png)
![rec3 9](https://user-images.githubusercontent.com/118671457/228625467-2816c7a3-59d0-4dcf-aa90-a5d1c099a649.png)

![rec3 10](https://user-images.githubusercontent.com/118671457/228625583-8f515dd0-f32f-401d-bb7f-3b8111dcccce.png)
