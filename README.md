## Ex-03EDA

## AIM
To perform EDA on the given data set.

## Explanation
The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM

### STEP 1
Import the required packages(pandas,numpy,seaborn).

### STEP 2
Read the given .csv file.

### STEP 3
Convert the file into a dataframe and get information of the data.

### STEP 4
Remove the non numerical data columns using drop() method.

### STEP 5
Replace the null values using (.fillna).

### STEP 6
Returns object containing counts of unique values using (value_counts()).

### STEP 7
Plot the counts in the form of Histogram or Bar Graph.

### STEP 8
Find the pairwise correlation of all columns in the dataframe(.corr()).

### STEP 9
Save the final data set into the file.

## CODE
~~~
import pandas as pd
import numpy as np
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df.info()
df.head()
df.tail()
df.isnull().sum()
df.drop("Cabin",axis=1,inplace=True)
df.info()
df.isnull().sum()
df["Age"]=df["Age"].fillna(df["Age"].median())
df.boxplot()
df.isnull().sum()
df["Embarked"]=df["Embarked"].fillna(df["Embarked"].mode()[0])
df.isnull().sum()
df["Embarked"].value_counts()
df["Pclass"].value_counts()
df["Survived"].value_counts()
sns.countplot(x="Survived",data=df)
sns.countplot(x="Pclass",data=df)
sns.countplot(x="Sex",data=df)
df.info()
sns.displot(df["Fare"])
sns.countplot(x="Pclass",hue="Survived",data=df)
sns.displot(df[df["Survived"]==0]["Age"])
pd.crosstab(df["Pclass"],df["Survived"])
pd.crosstab(df["Sex"],df["Survived"])
df.corr()
sns.heatmap(df.corr(),annot=True)
~~~
## OUPUT
![1](https://user-images.githubusercontent.com/95342910/162871813-1e64c3f4-e76e-4df9-b876-4ab9ac8eb3d0.png)

![2](https://user-images.githubusercontent.com/95342910/162871865-0471f15a-c8c1-4e9a-9790-b318bea2a716.png)

![3](https://user-images.githubusercontent.com/95342910/162871952-9b0f18cf-b93a-4128-b443-4a214a76de4f.png)

![4](https://user-images.githubusercontent.com/95342910/162872014-b93acdd7-d348-4b91-b4a9-08b2b4a46e89.png)

![5](https://user-images.githubusercontent.com/95342910/162872086-c2ffd763-3899-4a8a-a104-b25ed1a71a79.png)

![6](https://user-images.githubusercontent.com/95342910/162872142-c1d43690-1ad8-4803-b020-04b7c46e1b26.png)

![7](https://user-images.githubusercontent.com/95342910/162872208-cf9c1f33-0085-4ad1-bc7f-4b89507f7457.png)

![8](https://user-images.githubusercontent.com/95342910/162872248-2fe4565a-6910-44df-bff1-5700c32b5c9e.png)

![9](https://user-images.githubusercontent.com/95342910/162872277-37f93e97-ed5b-4b75-8940-fc991fb6eb58.png)

![10](https://user-images.githubusercontent.com/95342910/162872296-f8f198cd-5364-41b2-9b96-c081119c8135.png)

![11](https://user-images.githubusercontent.com/95342910/162872328-5e741b3d-195a-4362-8ed1-0018e7581d2e.png)

![12](https://user-images.githubusercontent.com/95342910/162872377-9fbe11d0-68a5-4e20-bb9d-e4760f57acbc.png)

![13](https://user-images.githubusercontent.com/95342910/162872539-0fad95a8-ca3e-4129-a3b6-aff31ef05eb8.png)

![14](https://user-images.githubusercontent.com/95342910/162872604-36ae1d12-3ffc-4a7f-a21a-a197b530383e.png)

![15](https://user-images.githubusercontent.com/95342910/162872639-7973771e-cba4-43dd-a84e-0d3f800df574.png)

![16](https://user-images.githubusercontent.com/95342910/162872665-5af6a138-ce0a-4a58-8d20-de27ad8ed846.png)

![17](https://user-images.githubusercontent.com/95342910/162872697-b14efcb1-7d1b-4aa7-823c-b297d44f0cd0.png)

![18](https://user-images.githubusercontent.com/95342910/162872721-08e484be-cafb-4baf-8e75-a4a4f63e3d5e.png)

## RESULT
Thus the EDA on the given data set is sucessfully done.
