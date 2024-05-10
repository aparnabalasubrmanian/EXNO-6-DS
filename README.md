# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
```
NAME : aparna 
REG NO : 212222220005
```
```
import seaborn as sns
import matplotlib.pyplot as plt
x=[1,2,3,4,5]
y=[3,6,2,7,1]
sns.lineplot(x=x,y=y)
```
![329442957-e2a31382-aadf-4c1b-889c-906d93a63802](https://github.com/aparnabalasubrmanian/EXNO-6-DS/assets/123351172/af330d33-ea49-4619-80d9-831512667b27)





```
df=sns.load_dataset("tips")
df
```
![329442996-3af95da2-0874-42b8-88e3-9bbea9995996](https://github.com/aparnabalasubrmanian/EXNO-6-DS/assets/123351172/93ce2eb5-1823-4e7f-a2b1-577d31e63d3e)



```
sns.lineplot(x="total_bill",y="tip",data=df,hue="sex",linestyle='solid',legend="auto")
```
![329443027-4f99e2ba-4449-494b-a4cf-0dc6117e8657](https://github.com/aparnabalasubrmanian/EXNO-6-DS/assets/123351172/98c488cb-0260-4d42-b20e-5942f1ef865e)



```
x=[1,2,3,4,5]
y1=[3,5,2,6,1]
y2=[1,6,4,3,8]
y3=[5,2,7,1,4]
sns.lineplot(x=x,y=y1)
sns.lineplot(x=x,y=y2)
sns.lineplot(x=x,y=y3)
plt.title("Multi-line Plot")
plt.xlabel('X Label')
plt.ylabel('Y Label')
```

```
import seaborn as sns
import matplotlib.pyplot as plt
tips=sns.load_dataset('tips')
avg_total_bill = tips.groupby('day')['total_bill'].mean()
avg_tip=tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
plt.xlabel('Day of the week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
![329443123-c98a61fa-0f15-4a79-a137-81e1b1df47b0](https://github.com/aparnabalasubrmanian/EXNO-6-DS/assets/123351172/cd4ba2ac-cd4e-49e2-87c7-09ebc8205425)



```
avg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip = tips.groupby('time')['tip'].mean()
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip', width=0.4)

plt.xlabel('Time of Day')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Time of Day')
plt.legend()
```
![329443138-a50066b6-f31a-4617-9080-dd4e0b8e4153](https://github.com/aparnabalasubrmanian/EXNO-6-DS/assets/123351172/f36ee867-949e-474e-8c45-3575060db91d)



```
years=range (2000, 2012)
apples = [0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```

![329443154-dfed0207-fe82-402d-9a92-eb53d0b1aa0a](https://github.com/aparnabalasubrmanian/EXNO-6-DS/assets/123351172/33d41535-b502-40c9-8402-9e7e432fe03c)

```
import seaborn as sns
dt= sns.load_dataset('tips')
# Bar plot with hue parameter
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the week')
plt.ylabel('Total Bill')
plt.title('Total Bill by Day and Gender')
```
![329443173-21fb5370-5549-4321-83d0-d1019adb0711](https://github.com/aparnabalasubrmanian/EXNO-6-DS/assets/123351172/9eb2735d-50ca-4f88-af64-d2326cd4a0ec)



```
import seaborn as sns
# Load the tips dataset
tips = sns.load_dataset('tips')
# Scatter plot of total bill vs. tip amount
sns.scatterplot(x= 'total_bill', y='tip', hue='sex',data=tips)
# Set labels and title
plt.xlabel('Total Bill')
plt.ylabel('Tip Amount')
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```
![329443199-f263836c-2ce9-4ae9-9a79-6eb4f6a4dd59](https://github.com/aparnabalasubrmanian/EXNO-6-DS/assets/123351172/3d686735-cedc-4039-9a64-3261b3ddbaf2)



```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
np.random.seed(0)
marks = np.random.normal(loc=70, scale=10, size=100)
marks
```
![329443228-f8dd9e04-4832-4360-b956-a53fa07e1d74](https://github.com/aparnabalasubrmanian/EXNO-6-DS/assets/123351172/c848530f-128a-4ce7-9d06-c232d5bdb1d7)


```
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6,
palette="Set3", inner="quartile")
# Add labels and title
plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
![329443246-74dd4973-c56f-4747-9840-04fa9d63c4b0](https://github.com/aparnabalasubrmanian/EXNO-6-DS/assets/123351172/798337be-8712-4c99-8ea4-24d51fed3ab3)




```
import seaborn as sns
sns.set(style = 'whitegrid')
tip = sns.load_dataset('tips')
sns.violinplot(x ='day', y ='tip', data = tip)
```

![329443260-8c095b04-8b65-4836-be07-0bb5b5402e0d](https://github.com/aparnabalasubrmanian/EXNO-6-DS/assets/123351172/7c793d8e-ce03-445a-8573-e3b0815883ec)


```
import seaborn as sns
sns.set(style = 'whitegrid')
tip = sns.load_dataset('tips')
sns.violinplot(x=tip["total_bill"])
```

![329443283-99cb04a8-95f6-4459-b460-08e2440efdec](https://github.com/aparnabalasubrmanian/EXNO-6-DS/assets/123351172/ab175d2e-5a38-4bae-b880-48ca70bb0b1b)


```
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='fill',linewidth=3,palette='Set2',alpha=0.8)
```![329443310-8b977776-0917-4842-b956-056cf94b90aa](https://github.com/aparnabalasubrmanian/EXNO-6-DS/assets/123351172/8e0fc991-b62d-4940-9f3a-394f6e5a65d7)




```
sns.histplot(data=marks, bins=10, kde=True, stat='count', cumulative=False, multiple='stack', element='bars', palette='Set1', shrink=0.7)
plt.xlabel('Marks')
plt.ylabel('Density')
plt.title('Histogram of students Marks')
```
![329443324-8f459c84-31d1-4935-858e-83ff06c847a7](https://github.com/aparnabalasubrmanian/EXNO-6-DS/assets/123351172/c958551a-bf2e-4133-89bb-0c4d0b883713)

![329443343-a5cdf3b7-6605-4f7e-99b5-84700d8b8920](https://github.com/aparnabalasubrmanian/EXNO-6-DS/assets/123351172/a5686968-07f4-41fa-a490-e6a70a30541f)

# Result:
Thus, the Data Visualization using seaborn python library for the given data is implemented successfully
