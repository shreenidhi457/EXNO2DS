# EXNO2DS
## Date:8.8.2026
## Name: Shreenidhi S 
## Reg no: 212225040410
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
~~~
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
~~~


~~~
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
~~~
<img width="1912" height="1013" alt="Screenshot 2026-08-06 204057" src="https://github.com/user-attachments/assets/0e5e558b-911e-47c3-adc0-02bf0a41edcc" />

~~~
dt.info()
~~~

~~~
dt.shape
~~~

<img width="1907" height="998" alt="Screenshot 2026-08-06 204105" src="https://github.com/user-attachments/assets/0930e42b-eafc-4917-9e21-eaa4f1ffe524" />

~~~
dt.set_index("PassengerId",inplace=True)
~~~

~~~
dt.describe()
~~~
~~~
dt.nunique()
~~~

<img width="1917" height="1012" alt="Screenshot 2026-08-06 204115" src="https://github.com/user-attachments/assets/f48d035e-c552-481b-a168-0b21a31457da" />

~~~
dt["Survived"].value_counts()
~~~



<img width="1917" height="997" alt="Screenshot 2026-08-06 204123" src="https://github.com/user-attachments/assets/bd28d840-f780-41f5-be4f-dfc528d9c956" />

~~~
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
~~~

~~~
sns.countplot(data=dt,x="Survived")
~~~

<img width="1917" height="1000" alt="Screenshot 2026-08-06 204132" src="https://github.com/user-attachments/assets/a61d1b6d-0d67-4d28-85e1-ac8b586f0332" />

~~~
dt
~~~

<img width="1917" height="1030" alt="Screenshot 2026-08-06 204141" src="https://github.com/user-attachments/assets/c3b200d4-669f-4216-a5ef-8b2ed6f78280" />

~~~
dt.Pclass.unique()
~~~



<img width="1917" height="1005" alt="Screenshot 2026-08-06 204156" src="https://github.com/user-attachments/assets/fe821551-af86-4b74-a9ba-74b8d0c4d359" />

~~~
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
~~~

~~~
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
~~~

<img width="1916" height="1013" alt="Screenshot 2026-08-06 204206" src="https://github.com/user-attachments/assets/fede45ce-c2bf-4726-964e-20ff6405ac48" />

~~~
sns.catplot(x="Survived",hue="Gender",data=dt,kind="count")
~~~

<img width="1903" height="992" alt="Screenshot 2026-08-06 204216" src="https://github.com/user-attachments/assets/fb71ed31-5af9-4632-8392-e81035cae323" />

~~~
dt.boxplot(column="Age",by="Survived")
~~~

<img width="1916" height="970" alt="Screenshot 2026-08-06 204225" src="https://github.com/user-attachments/assets/54fcdfa1-024a-4dc3-94e1-8af92b862784" />

~~~
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
~~~

<img width="1917" height="972" alt="Screenshot 2026-08-06 204245" src="https://github.com/user-attachments/assets/7b3cee8e-3f28-4b33-b44e-0ad226b0007a" />

~~~
sns.jointplot(x="Age",y="Fare",data=dt)
~~~

<img width="1917" height="1000" alt="Screenshot 2026-08-06 204259" src="https://github.com/user-attachments/assets/1d196262-03a4-4ea5-a205-e1eb94a00b2f" />

~~~
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
~~~


<img width="1386" height="1023" alt="Screenshot 2026-08-06 204307" src="https://github.com/user-attachments/assets/98fec690-35a4-4508-897a-1ced58f153d3" />

~~~
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
~~~

<img width="1917" height="1016" alt="Screenshot 2026-08-06 204315" src="https://github.com/user-attachments/assets/fc422947-d6c8-47cd-b839-b2974d291e37" />

~~~
## Co-relation
corr=dt.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
~~~

<img width="1917" height="1055" alt="Screenshot 2026-08-06 204334" src="https://github.com/user-attachments/assets/96a116e0-6e5f-4902-aabb-5f486326817d" />

~~~
sns.pairplot(dt)
~~~

<img width="1917" height="1010" alt="Screenshot 2026-08-06 204416" src="https://github.com/user-attachments/assets/8e60b863-b436-45cc-aab7-13372bc983dd"> 
<img width="1917" height="1006" alt="Screenshot 2026-08-06 204432" src="https://github.com/user-attachments/assets/34107fb6-cef2-4a74-b74a-fd4bd0216370" />


# RESULT
~~~
    Data analysis was completed successfully
~~~~
