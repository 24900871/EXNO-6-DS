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

~~~

import seaborn as sns
import matplotlib.pyplot as plt
x=[1,2,3,4,5]
y=[3,6,2,7,1]
sns.lineplot(x=x,y=y)

~~~

![image](https://github.com/user-attachments/assets/44ccbf6a-3c04-4f66-8b55-20ec21b13e78)

~~~

df=sns.load_dataset("tips")
df

~~~

![image](https://github.com/user-attachments/assets/0ff1fe95-c2ee-4e50-8088-513d95bfe531)

~~~

sns.lineplot(x="total_bill",y="tip",data=df,hue="sex",linestyle='solid',legend="auto")

~~~

![image](https://github.com/user-attachments/assets/b4479582-bd3f-42d4-8898-9fcb5d919635)

~~~

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

~~~

![image](https://github.com/user-attachments/assets/bca50805-8974-4acb-91cd-9ee572af6ca7)

~~~

tips=sns.load_dataset('tips')
avg_total_bill=tips.groupby('day')['total_bill'].mean()
avg_tip=tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8,6))
p1=plt.bar(avg_total_bill.index,avg_total_bill,label='Total Bill')
p2=plt.bar(avg_tip.index,avg_tip,label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()

~~~

![image](https://github.com/user-attachments/assets/6967fe2c-5e7a-4e5b-af4b-3364feee83f0)

~~~

avg_total_bill=tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time')['tip'].mean()
p1=plt.bar(avg_total_bill.index,avg_total_bill,label='Total Bill',width=0.4) # Added a comma after 0.4
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip',width=0.4) # Added a comma after 0.4
plt.xlabel('Time of Day')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Time of Day')
plt.legend()

~~~

![image](https://github.com/user-attachments/assets/bd575b68-4c30-450d-b186-46a8f3627206)

~~~

years = range(2000, 2012)
apples = [0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0] # Added comma after 0
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.8] # Added comma after 0.8
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)

~~~

![image](https://github.com/user-attachments/assets/6f61b509-7151-4464-a13b-2d784c250dd8)

~~~

import seaborn as sns
dt=sns.load_dataset('tips')
sns.barplot(x='day',y='total_bill',hue='sex',data=dt,palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel('Total Bill')
plt.title('Total Bill by Day and Gender')

~~~

![image](https://github.com/user-attachments/assets/21a16c2c-9587-485e-aa58-7a70dfc3ef6d)

~~~

import pandas as pd
tit=pd.read_csv("/content/titanic_dataset (2).csv")
tit

~~~

![image](https://github.com/user-attachments/assets/367b4a47-6441-4ae6-b3c0-098def39662a)

~~~

plt.figure(figsize=(8,5))
sns.barplot(x='Embarked',y='Fare',data=tit,palette='rainbow')
plt.title("Fare of Passenger by Embarked Town")

~~~

![image](https://github.com/user-attachments/assets/40e2f550-ce8e-4b3c-bb74-b27df6182702)

~~~

plt.figure(figsize=(8,5))
sns.barplot(x='Embarked',y='Fare',data=tit,palette='rainbow',hue='Pclass')
plt.title("Fare of Passenger by Embarked Town,Divided by Class")

~~~

![image](https://github.com/user-attachments/assets/2e01668e-6aa6-41db-b8d4-e7b1d0c46860)

~~~

tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill',y='tip',hue='sex',data=tips)
plt.xlabel('Total Bill')

~~~

![image](https://github.com/user-attachments/assets/28729bd4-52c4-4bc5-b26b-f6ff3cf4a331)

~~~

import seaborn as sns
import numpy as np
import pandas as pd
np.random.seed(1)
num_var=np.random.randn(1000)
num_var=pd.Series(num_var,name="Numerical Variable")
num_var

~~~

![image](https://github.com/user-attachments/assets/2e07f457-5bf4-4fed-9c6c-fe8310f0c198)

~~~

sns.histplot(data=num_var,kde=True)

~~~

![image](https://github.com/user-attachments/assets/4df10a91-e00b-4f71-8fb6-3277a526037a)

~~~

sns.histplot(data=tit,x="Pclass",hue="Survived",kde=True)

~~~

![image](https://github.com/user-attachments/assets/3af41213-b700-4498-9e47-e4515bebef27)

~~~

import matplotlib.pyplot as plt
np.random.seed(0)
marks=np.random.normal(loc=70,scale=10,size=100)
marks

~~~

![image](https://github.com/user-attachments/assets/a313cf3e-18c0-4b1b-a3c2-dc61ba2803c6)

~~~

sns.histplot(data=marks,bins=10,kde=True,stat='count',cumulative=False) # Added closing parenthesis
plt.xlabel('Marks')
plt.ylabel('Density')
plt.title('Histogram of Student Marks')

~~~

![image](https://github.com/user-attachments/assets/597eb3fe-b318-4563-9cc6-4caa4a9ba1fc)

~~~

tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'],y=tips['total_bill'],hue=tips['sex'])

~~~

![image](https://github.com/user-attachments/assets/5e291f42-afd3-4294-8a2b-69e93fc018c3)

~~~

sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.8,
          whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5})

~~~

![image](https://github.com/user-attachments/assets/334a91fa-7388-4235-8f05-3d574439f716)


~~~

sns.boxplot(x='Pclass',y='Age',data=tit,palette='rainbow')
plt.title("Age by Passenger Class,Titanic")

~~~

![image](https://github.com/user-attachments/assets/19c28024-26ed-4cb3-b9ab-16cfd0a55d11)

~~~

sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.8) # Added closing parenthesis and provided a value for width
plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")

~~~

![image](https://github.com/user-attachments/assets/9c0e79a4-755d-44b1-b63f-44843e644151)

~~~

import seaborn as sns
sns.set(style='whitegrid')
tip=sns.load_dataset('tips')
sns.violinplot(x='day',y='tip',data=tip)

~~~

![image](https://github.com/user-attachments/assets/bbae2215-e977-4bc4-b34b-464bdffa096e)

~~~

sns.set(style='whitegrid')
tip=sns.load_dataset('tips')
sns.violinplot(x=tip["total_bill"])

~~~

![image](https://github.com/user-attachments/assets/9ead590b-a06c-4eac-9cca-f34ee08e88ee)

~~~

sns.set(style='whitegrid')
tip=sns.load_dataset('tips')
sns.violinplot(x="tip",y="day",data=tip)

~~~~

![image](https://github.com/user-attachments/assets/0d9c9864-a320-4ec0-b8d4-acb9b72f41b0)

~~~

sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='fill',linewidth=3) # Added closing parenthesis

~~~

![image](https://github.com/user-attachments/assets/771c9c30-cf9f-4644-b221-bd5d069578f7)

~~~

sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='layer',linewidth=3)

~~~~


![image](https://github.com/user-attachments/assets/1c1dffc6-bff6-4f19-829e-37b66ec8a5a0)

~~~

sns.kdeplot(data=tips, x='total_bill', hue='time', multiple='stack', linewidth=3)

~~~

![image](https://github.com/user-attachments/assets/95cb389d-318f-4d20-9798-0986be07982a)

~~~

data=np.random.randint(low=1,high=100,size=(10,10))
print("The data to be plotted:\n")
print(data)

~~~


![image](https://github.com/user-attachments/assets/af5e5814-3f9e-48bf-954f-0223761e70d2)

~~~

hm=sns.heatmap(data=data)

~~~~

![image](https://github.com/user-attachments/assets/0c3e3b2b-260a-4e8c-b660-c7d527290139)

~~~

tips=sns.load_dataset('tips')
numeric_cols=tips.select_dtypes(include=np.number).columns
corr=tips[numeric_cols].corr()
sns.heatmap(corr,annot=True,cmap="plasma",linewidth=0.5)

~~~~

![image](https://github.com/user-attachments/assets/2b772e68-9d95-4f1a-9015-951f1c6d5b40)


# Result:

Data Visualization using seaborn python library for the given datas has been performed successfully
