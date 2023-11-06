# Ex-08-Data-Visualization-
# AIM
To Perform Data Visualization on a complex dataset and save the data to a file.

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
## STEP 1
Read the given Data

## STEP 2
Clean the Data Set using Data Cleaning Process

## STEP 3
Apply Feature generation and selection techniques to all the features of the data set

## STEP 4
Apply data visualization techniques to identify the patterns of the data.

# CODE
```python
import matplotlib.pyplot as plt
import seaborn as sns
import numpy as np
df=sns.load_dataset("tips")
df=df.head(10)
df
```
# OUTPUT
![image](https://github.com/Vijisdurai/ODD2023-Datascience-Ex-08/assets/118343184/0a83555e-b1f9-406c-a28f-34fdb900dad1)

# Line graphs
```using seaborn```
```python
sns.lineplot(data=df,x="total_bill",y="tip")
```
## output
![image](https://github.com/Vijisdurai/ODD2023-Datascience-Ex-08/assets/118343184/72a93650-4d8b-47f0-b0ea-8bd0c040a9f3)

``` using matplot```
```python
x=df["total_bill"]
y=df["tip"]
plt.plot(x,y)
plt.xlabel("Total_bill")
plt.ylabel("Tip")
plt.title("Total_bill and Tip")
plt.show()
```
## output
![image](https://github.com/Vijisdurai/ODD2023-Datascience-Ex-08/assets/118343184/df30ab3f-2d7f-4a9e-967e-4c60cbeb5fe4)

# Area chart
```using matplot```
```python
x=df["total_bill"]
y1=df["tip"]
y2=df["size"]
plt.fill_between(x,y1,color='yellow')
plt.fill_between(x,y2,color='black')
plt.plot(x,y1,color='red')
plt.plot(x,y2,color='violet')
plt.legend(['y1','y2'])
plt.show()
```
## output
![image](https://github.com/Vijisdurai/ODD2023-Datascience-Ex-08/assets/118343184/e5d1393e-ec72-4b93-a2d0-da914597f81b)

# bar chart
```using matplot```
```python
values=df["tip"]
names=df["sex"]
plt.bar(names,values,color="teal")
plt.show()
```
## output
![image](https://github.com/Vijisdurai/ODD2023-Datascience-Ex-08/assets/118343184/23b02249-2238-4155-88d8-ca8fcfdf5506)

```using seaborn```
```python
sns.barplot(data=df1,x='day',y='total_bill',hue='sex',palette='Set1')
plt.xlabel('day of the week')
plt.ylabel('Total Bill')
plt.title('Total Bill by day and Gender')
```
## output
![image](https://github.com/Vijisdurai/ODD2023-Datascience-Ex-08/assets/118343184/998e4d64-1dcd-4b7d-948b-577a56fc1b2b)

# SCATTER PLOT
```using matplot```
```python
plt.scatter(x=df['total_bill'],y=df["tip"],s=50,color='orange')
plt.show()
```
## output
![image](https://github.com/Vijisdurai/ODD2023-Datascience-Ex-08/assets/118343184/1c01f62f-dec1-4c19-a280-6dd2377fc2c2)

```using seaborn```
```python
sns.scatterplot(data=df,x='total_bill',y='tip',hue='sex',palette='Set1')
plt.xlabel('day of the week')
plt.ylabel('Total Bill')
plt.title('Total Bill by day and Gender')
plt.show()
```
## output
![image](https://github.com/Vijisdurai/ODD2023-Datascience-Ex-08/assets/118343184/6113bc5d-5cf4-461b-951e-056c48c77d0c)

#HISTOGRAM
```using matplot```
```python
x=df['total_bill']
range=(0,100)
bins=10
plt.hist(x,bins,range,color='red',histtype='bar',rwidth=0.8)
plt.title('my Histogram')
plt.show()
```
## output
![image](https://github.com/Vijisdurai/ODD2023-Datascience-Ex-08/assets/118343184/1beb0151-469c-4a14-99ee-bb84e3448cd2)

```using seaborn```
```python
sns.histplot(data=df,x='total_bill',y=df['tip'])
plt.xlabel('Total Bill')
plt.ylabel('Tip')
plt.title('Total Bill by day and Gender')
plt.show()
```
## output
![image](https://github.com/Vijisdurai/ODD2023-Datascience-Ex-08/assets/118343184/26e8697d-6136-4a42-a886-5fc61e3c8db6)

# BOX PLOT
```using matplot```
```python
plt.boxplot(df['tip'])
plt.show()
```
## output
![image](https://github.com/Vijisdurai/ODD2023-Datascience-Ex-08/assets/118343184/bde632b5-7462-4c97-abf7-2e3f6eee52f5)

```using seaborn```
```python
sns.boxplot(data=df,x='day',y='total_bill',hue=df['sex'])
plt.xlabel('Total Bill')
plt.ylabel('Tip')
plt.title('Total Bill by day and Gender')
plt.show()
```
## output
![image](https://github.com/Vijisdurai/ODD2023-Datascience-Ex-08/assets/118343184/2f6e9a1c-6101-4d36-b6e4-6a269bccf59d)

# violin plot
```python
sns.violinplot(data=df,x='day',y='total_bill',hue=df['sex'])
plt.xlabel('Total Bill')
plt.ylabel('Tip')
plt.title('Total Bill by day and Gender')
plt.show()
```
## output
![image](https://github.com/Vijisdurai/ODD2023-Datascience-Ex-08/assets/118343184/72d9d419-f020-449e-8538-1292c10c5d86)

# # KDE PLOT
```python
sns.kdeplot(data=df,x='tip')
plt.xlabel('Total Bill')
plt.ylabel('Tip')
plt.title('Total Bill by day and Gender')
plt.show()
```
## output
![image](https://github.com/Vijisdurai/ODD2023-Datascience-Ex-08/assets/118343184/a532cdae-c4b0-4ec8-a080-ec8b30606de7)

# Heat Map
```python
data=np.random.randint(low=1,high=100,size=(10,10))
sns.heatmap(data=data,annot=True)
```
## output
![image](https://github.com/Vijisdurai/ODD2023-Datascience-Ex-08/assets/118343184/6f7a2a5c-1872-416c-8396-5d4c67a19bd7)



