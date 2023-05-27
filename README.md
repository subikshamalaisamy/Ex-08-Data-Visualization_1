# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.

# CODE
import pandas as pd

import seaborn as sns

import matplotlib.pyplot as plt

df = sns.load_dataset("tips")

df.head()

df.isnull().sum()

plt.figure(figsize=(5,5))

plt.title("Data with Outliers")

df.boxplot()

plt.show()

plt.figure(figsize=(5,5))

cols = ['size','tip','total_bill']

Q1 = df[cols].quantile(0.25)

Q3 = df[cols].quantile(0.75)

IQR = Q3 - Q1

df = df[~((df[cols] < (Q1 - 1.5 * IQR)) |(df[cols] > (Q3 + 1.5 * IQR))).any(axis=1)]

plt.title("Dataset after removing outliers")

df.boxplot()

plt.show()

sns.barplot(x=df['day'], y=df['total_bill'])

plt.title("Highest Total Bill Amount by day")

plt.show()

sns.boxplot(x=df['smoker'], y=df['tip'],hue=df['smoker'])

plt.title("Average Tip Amount given by smokers and non-smokers")

plt.show()

df["tip_percent"] = df["tip"] / df["total_bill"]

sns.barplot(x=df['size'],y=df['tip_percent'],data=df)

plt.title("Tip Percentage by Dining Party Size")

plt.show()

sns.barplot(x=df['sex'], y=df['tip'])

plt.title("Highest tips based on gender")

plt.show()

sns.barplot(x=df['day'],y=df['total_bill'])

plt.title("Total bill amount by day of the week")

plt.show()

sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")

plt.title("Distribution of Total Bill Amounts by Time of Day")

plt.show()

sns.barplotdata=df,(x=df['size'],y=df['total_bill'])

plt.title("Average Total Bill Amount by Dining Party Size")

plt.show()

sns.violinplot(x="day", y="tip", data=df)

plt.title("Tip Amount by Day of Week")

plt.show()

sns.barplot(x="time", y="tip", data=df)

plt.title("Tip Amount by Time of Day")

plt.show()

sns.scatterplot(x="total_bill", y="tip", data=df)

plt.title("Correlation between Tip Amount and Total Bill Amount")

plt.show()

# OUPUT
<img width="317" alt="image" src="https://github.com/subikshamalaisamy/Ex-08-Data-Visualization_1/assets/87276633/6fe3d942-4d2f-4d5e-80a6-b5eef7665336">
<img width="100" alt="image" src="https://github.com/subikshamalaisamy/Ex-08-Data-Visualization_1/assets/87276633/66649b03-f535-477d-b648-c8562714dcf7">
<img width="376" alt="image" src="https://github.com/subikshamalaisamy/Ex-08-Data-Visualization_1/assets/87276633/7ddc392b-8938-4bd3-9663-a374d884207b">
<img width="398" alt="image" src="https://github.com/subikshamalaisamy/Ex-08-Data-Visualization_1/assets/87276633/16af9709-c4f1-4571-b419-2b30bbe866e5">
<img width="365" alt="image" src="https://github.com/subikshamalaisamy/Ex-08-Data-Visualization_1/assets/87276633/f354a759-ab2d-4c33-89bb-f90191bde30e">
<img width="354" alt="image" src="https://github.com/subikshamalaisamy/Ex-08-Data-Visualization_1/assets/87276633/3eb67e45-a898-477d-92ab-b083b67636e9">
<img width="368" alt="image" src="https://github.com/subikshamalaisamy/Ex-08-Data-Visualization_1/assets/87276633/c856ee0c-927b-428d-b479-9758aaa83a0c">
<img width="364" alt="image" src="https://github.com/subikshamalaisamy/Ex-08-Data-Visualization_1/assets/87276633/1aee4d2a-7793-4f6c-b83e-fb2087c595b8">
<img width="369" alt="image" src="https://github.com/subikshamalaisamy/Ex-08-Data-Visualization_1/assets/87276633/70bf5e39-3572-4fa0-bfec-f8700364c196">
<img width="386" alt="image" src="https://github.com/subikshamalaisamy/Ex-08-Data-Visualization_1/assets/87276633/83cbd825-1d2f-44dd-bb43-cedc43140d56">
<img width="365" alt="image" src="https://github.com/subikshamalaisamy/Ex-08-Data-Visualization_1/assets/87276633/99fedd27-3fc8-40cb-90ce-d4ecf63ddc43">
<img width="341" alt="image" src="https://github.com/subikshamalaisamy/Ex-08-Data-Visualization_1/assets/87276633/c73fa383-d5ac-49dd-a72b-ec89a65530da">
<img width="375" alt="image" src="https://github.com/subikshamalaisamy/Ex-08-Data-Visualization_1/assets/87276633/c61ef90c-6eea-41c5-8a3c-e9de08c6c884">
<img width="360" alt="image" src="https://github.com/subikshamalaisamy/Ex-08-Data-Visualization_1/assets/87276633/c1513d55-0f51-4731-95d5-6fda81b82654">

# RESULT

Thus the data visualization on the complex data set is performed successfully.
