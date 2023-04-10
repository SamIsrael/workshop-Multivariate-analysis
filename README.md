# workshop-Multivariate-analysis
## AIM:
Write a python code to visualize the given data using bivariate analysis.
## ALGORITHM:
### STEP 1:
Import the csv file using pandas package.
### STEP 2:
Store the dat as a dataframe in a variable.
### STEP 3:
Display the information of data such as datatypes, value counts, skewness
### STEP 4:
Display the data in the barplot, scatter plot and heatmap.
## CODE:
```
import pandas as pd
import seaborn as sns
from matplotlib import pyplot as plt
df=pd.read_excel('/content/FlightInformation.xlsx')
df
```
```
df.info()
df.dtypes
df['Airline'].value_counts()
df.describe()
```
```
plt.figure(figsize=(30,10))
sns.scatterplot(x=df['Airline'],y=df['Price'],hue=df['Source'])
```
```
prices=df.loc[:,["Airline","Price"]]
prices=prices.groupby(by=["Airline"]).sum().sort_values(by="Price")
plt.figure(figsize=(30,10))
sns.barplot(x=prices.index,y="Price",data=prices)
plt.xticks(rotation=90)
plt.xlabel=("Airline")
plt.ylabel=("Price")
plt.show()
```
```
df=pd.read_excel('/content/FlightInformation.xlsx')
sns.heatmap(df.corr())
```
## OUTPUT:
![image](.//Screenshot%20from%202023-04-10%2010-27-35.png)
![image](./Screenshot%20from%202023-04-10%2010-27-53.png)
![image](./Screenshot%20from%202023-04-10%2010-28-11.png)
![image](./Screenshot%20from%202023-04-10%2010-28-22.png)
## RESULT:
Thus, the given data is visualized using bivariate analysis.
