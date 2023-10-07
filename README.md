# ODD2023-Datascience-Ex-04
## AIM:
To perform Multivariate EDA on the given data set.
## EXPLANATION:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
## ALGORITHM:
### STEP 1:
Import the built libraries required to perform EDA and outlier removal.
### STEP 2:
Read the given csv file
### STEP 3:
Convert the file into a dataframe and get information of the data.
### STEP 4:
Return the objects containing counts of unique values using (value_counts()).
### STEP 5:
Plot the counts in the form of Histogram or Bar Graph.
### STEP 6:
Use seaborn the bar graph comparison of data can be viewed.
### STEP 7:
Find the pairwise correlation of all columns in the dataframe.corr()
### STEP 8:
Save the final data set into the file.
## PROGRAM:
```
Name : Deepika S
Register Number : 212222230028
```
### SuperStore.csv file:
```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("/content/SuperStore (1).csv")
df=pd.DataFrame(data)
df.head()
df.info()
df.describe()
df.isnull().sum()
df['Postal Code']=df['Postal Code'].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()

sns.scatterplot(x=df['Region'],y=df['Sales'])

states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=states.index,y="Sales",data=states)

states=df.loc[:,["Ship Mode","Row ID"]]
states=states.groupby(by=["Ship Mode"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SHIP MODE")
plt.ylabel=("ROW ID")
plt.show()

sns.boxplot(x=df['Ship Date'],y=df['Sales'])
sns.displot(df, x="Region", hue="Category")
df.corr()
sns.heatmap(df.corr(),annot=True)
```
### diabetes.csv file:
```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("/content/diabetes.csv")
df
df.describe()
df.info
df.isnull().sum()

sns.scatterplot(x=df['Glucose'],y=df['BloodPressure'])

sns.scatterplot(x=df['Glucose'], y=df['BloodPressure'], hue=df['Outcome'])

Age=df.loc[:,["Age","BMI"]]
Age=Age.groupby(by=["Age"]).sum().sort_values(by="BMI")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=Age.index,y="BMI",data=Age)

Age=df.loc[:,["BloodPressure","Glucose"]]
Age=Age.groupby(by=["BloodPressure"]).sum().sort_values(by="Glucose")
sns.barplot(x=Age.index,y="Glucose",data=Age)
plt.xticks(rotation = 90)
plt.xlabel=("BloodPressure")
plt.ylabel=("Glucose")
plt.show()

sns.boxplot(x=df['DiabetesPedigreeFunction'],y=df['Insulin'])

sns.displot(df, x="Glucose", hue="Outcome")

df.corr()

sns.heatmap(df.corr(),annot=True)
```
## OUTPUT:
### DATA FRAME OF SUPERSTORE
![ds4 superstore](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-04/assets/119393935/022389f4-1c5a-4dab-9f66-40913683c510)
### Data information
![ds4info](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-04/assets/119393935/d1bde069-3fb8-4e0e-9ed8-33d7feba8fee)
### Data describing
![ds4describe](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-04/assets/119393935/7779f69d-17a6-413a-955a-65b003f8e802)
### Sum of null values
![ds4new4](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-04/assets/119393935/5d9e25fc-0983-4450-a43d-c47846b496e8)
### After removing null values
![ds4new5](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-04/assets/119393935/0ee3d281-46bd-439f-aac8-869f241b769b)
### Scatter plot
![ds4new6](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-04/assets/119393935/4f3657f1-18df-4216-8653-75a3c1880ac0)
### Bar plot
![ds4new7](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-04/assets/119393935/742ba782-43a3-4587-8d67-1aec3798e289)
![ds4new8](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-04/assets/119393935/72b5b30e-229e-4b80-8311-ba692b16ba71)
### Box plot
![ds4new9](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-04/assets/119393935/2c4c5c66-4c11-4bd3-b77c-1619658a9cc8)
### Dist plot
![ds4new10](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-04/assets/119393935/7ea3e1cf-e276-43e9-8ec0-725bbff2e290)
### Correlation coefficient interpretation
![ds4new11](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-04/assets/119393935/84629696-760d-4937-bb97-8cf7b560cb33)
### Heat map
![ds4new10](https://github.com/deepikasrinivasans/ODD2023-Datascience-Ex-04/assets/119393935/7ea3e1cf-e276-43e9-8ec0-725bbff2e290)
## DATA FRAME FOR DIABETES
