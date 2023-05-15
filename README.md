# Ex-07-Data-Visualization-

## AIM
To Perform Data Visualization on the given dataset and save the data to a file. 

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

# Reading the given dataset

import pandas as pd
df=pd.read_csv("Superstore.csv",encoding='unicode_escape')

df.head()

# Data Visualization using Seaborn

import seaborn as sns
from matplotlib import pyplot as plt


# 1.Line Plotsns.lineplot(x="Category",y="Sales",data=df,marker='o')

plt.figure(figsize=(9,6))
sns.lineplot(x="Segment",y="Region",data=df,marker='o')
plt.xticks(rotation = 90)

sns.lineplot(x='Ship Mode',y='Category', hue ="Segment",data=df)

sns.lineplot(x="Category",y="Sales",data=df,marker='o')


# 2.Scatterplot

sns.scatterplot(x='Category',y='Sub-Category',data=df)

sns.scatterplot(x='Category', y='Sub-Category', hue ="Segment",data=df)

plt.figure(figsize=(10,7))
sns.scatterplot(x="Region",y="Sales",data=df)
plt.xticks(rotation = 90)

# 3.Boxplot

sns.boxplot(x="Sub-Category",y="Discount",data=df)

sns.boxplot( x="Profit", y="Category",data=df)

# 4.Violin Plot

sns.violinplot(x="Profit",data=df)

# 5.Barplot

sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)

sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)

# 6.Pointplot

sns.pointplot(x=df["Quantity"],y=df["Discount"])

# 7.Count plot

sns.countplot(x="Category",data=df)

sns.countplot(x="Sub-Category",data=df)

# 8.Histogram

sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')


# 9.KDE Plot

sns.kdeplot(x="Profit", data = df,hue='Category')

# Data Visualization Using MatPlotl

# 1.Plot

plt.plot(df['Category'], df['Sales'])
plt.show()

# 2.Heatmap

df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)

# 3.Piechart

df1=df.groupby(by=["Ship Mode"]).sum()
labels=[]
for i in df1.index:
    labels.append(i)
colors=sns.color_palette("bright")
plt.pie(df1["Sales"],labels=labels,autopct="%0.0f%%")
plt.show()

df3=df.groupby(by=["Category"]).sum()
labels=[]
for i in df3.index:
    labels.append(i) 
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.pie(df3["Profit"],colors = colors,labels=labels, autopct = '%0.0f%%')
plt.show()

# 4.Histogram

plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="blue",bins=10)
plt.show()

# 5.Bargraph

plt.bar(df.index,df['Category'])
plt.show()

# 6.Scatterplot

plt.scatter(df["Region"],df["Profit"], c ="blue")
plt.show() 

# 7.Boxplot

plt.boxplot(x="Sales",data=df)
plt.show()

# OUPUT

# Reading the given dataset

![image](https://github.com/Niranjanasuresh2003/Ex-08-Data-Visualization-/assets/129851738/38d7a008-4fb5-4d75-909c-322531d5babd)

# Data Visualization Using Seaborn:

# 1.Line Plot

![image](https://github.com/Niranjanasuresh2003/Ex-08-Data-Visualization-/assets/129851738/bf0a5af2-68b6-4a78-9a91-ac1b9e184fdf)

![image](https://github.com/Niranjanasuresh2003/Ex-08-Data-Visualization-/assets/129851738/688eabbd-aafa-402b-96de-ec7e43929f00)

![image](https://github.com/Niranjanasuresh2003/Ex-08-Data-Visualization-/assets/129851738/80bb89ab-a979-4d95-b531-d1fd12199a49)


# 2.Scatterplot

![image](https://github.com/Niranjanasuresh2003/Ex-08-Data-Visualization-/assets/129851738/c6aa084f-3fcc-4c58-8495-75cf607fbf3f)

![image](https://github.com/Niranjanasuresh2003/Ex-08-Data-Visualization-/assets/129851738/ea9880fe-0e7c-454f-95f5-74f131b8777e)

![image](https://github.com/Niranjanasuresh2003/Ex-08-Data-Visualization-/assets/129851738/d3a01aaf-f33c-4ae5-bbbb-d57fedbbbf39)


# 3.Boxplot

![image](https://github.com/Niranjanasuresh2003/Ex-08-Data-Visualization-/assets/129851738/4e78ca5c-5556-4f43-92cf-774fa03077e6)

![image](https://github.com/Niranjanasuresh2003/Ex-08-Data-Visualization-/assets/129851738/40a83560-ef43-47af-af41-3f0ed92e5007)


# 4.Violin Plot
![image](https://github.com/Niranjanasuresh2003/Ex-08-Data-Visualization-/assets/129851738/988c2798-2003-4ca7-a140-df67652fa073)


# 5.Barplot

![image](https://github.com/Niranjanasuresh2003/Ex-08-Data-Visualization-/assets/129851738/b0a31a27-0394-4a73-bc33-363689f19d77)

![image](https://github.com/Niranjanasuresh2003/Ex-08-Data-Visualization-/assets/129851738/7e580f82-612b-4c65-9145-48c8ed516b5a)

# 6.Pointplot

![image](https://github.com/Niranjanasuresh2003/Ex-08-Data-Visualization-/assets/129851738/57a43744-8c88-45f4-bfb3-a5841284dd21)

# 7.Count plot

![image](https://github.com/Niranjanasuresh2003/Ex-08-Data-Visualization-/assets/129851738/457e3685-599e-473d-81e5-fd3f7b310315)

![image](https://github.com/Niranjanasuresh2003/Ex-08-Data-Visualization-/assets/129851738/29e55957-3a95-4b6b-a0c3-a8259bbf4317)

# 8.Histogram

![image](https://github.com/Niranjanasuresh2003/Ex-08-Data-Visualization-/assets/129851738/4e362d46-3791-406d-9af4-4b4a26ab3700)

# 9.KDE Plot
![image](https://github.com/Niranjanasuresh2003/Ex-08-Data-Visualization-/assets/129851738/d17e3257-8db9-460e-b6c4-c75266d9359c)


# Data Visualization Using Matplotlib:

# 1.Plot
![image](https://github.com/Niranjanasuresh2003/Ex-08-Data-Visualization-/assets/129851738/ee839f89-c590-4212-90af-c3bf8df156af)

# 2.Heatmap

![image](https://github.com/Niranjanasuresh2003/Ex-08-Data-Visualization-/assets/129851738/1811db12-4fad-47b5-9c6b-3dd66121eb4a)

# 3.Piechart

![image](https://github.com/Niranjanasuresh2003/Ex-08-Data-Visualization-/assets/129851738/f4ff254e-cfae-4b18-b80f-fe430e3d6d40)

![image](https://github.com/Niranjanasuresh2003/Ex-08-Data-Visualization-/assets/129851738/51c8aabd-6a1d-4699-8ccf-7d3d4fd7aa45)

# 4.Histogram
![image](https://github.com/Niranjanasuresh2003/Ex-08-Data-Visualization-/assets/129851738/48588be0-d707-446c-bc4a-6e5fa68e0734)

# 5.Bargraph

![image](https://github.com/Niranjanasuresh2003/Ex-08-Data-Visualization-/assets/129851738/000f9e9b-1df3-4612-a80d-ed84ab78a03c)

# 6.Scatterplot

![image](https://github.com/Niranjanasuresh2003/Ex-08-Data-Visualization-/assets/129851738/fe5f35f0-95ef-460e-8b1d-b4812cb7bd84)

# 7.Boxplot

![image](https://github.com/Niranjanasuresh2003/Ex-08-Data-Visualization-/assets/129851738/daf08abd-7e87-49df-9683-45931cb1dae5)


# RESULT
~~~

Hence,Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.

~~~







