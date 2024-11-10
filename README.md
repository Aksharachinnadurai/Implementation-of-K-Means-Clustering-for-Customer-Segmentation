# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Start the program
2.Import pandas and matplotlib.pyplot
3.Read the dataset and transform it
4.Import KMeans and fit the data in the model
5.Plot the Cluster graph
6.End the program 

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: AKSHARA C
RegisterNumber: 212223220004 
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers (1) (1).csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []  #Within-Cluster sum of square. 
for i in range(1,11):
  kmeans=KMeans(n_clusters = i,init = "k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])data.head() function
y_pred = km.predict(data.iloc[:,3:])
y_pred
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
![380591789-bb84a177-076e-461a-b41f-4f3bc9ec1e4f](https://github.com/user-attachments/assets/4a24e3c3-1e97-4353-b275-ba1907502a6f)

![380591930-eebae6b6-4a7e-4393-a7ec-984a7b5ac9e9](https://github.com/user-attachments/assets/589b7fd7-8c88-4097-9381-67496103ca44)

![380591976-498d6d35-6cb5-4f56-bf26-95bb9076ad25](https://github.com/user-attachments/assets/bd9029ad-0548-4575-b7cb-e4a5a56be3fe)

![380592028-830b894c-7ec3-44c3-a348-2b2a9dd20a23](https://github.com/user-attachments/assets/8be2e91b-acee-4184-9a3f-e29088c002a9)

![380592071-ec6f1671-96e0-426c-a299-727d01f11e86](https://github.com/user-attachments/assets/7a0207b8-d653-4f53-93d0-763f836e73c5)

![380592147-bb471b3e-c7ee-47a6-ad7c-5a29916fe446](https://github.com/user-attachments/assets/0bb552d7-48ac-4350-810e-9c9170c63599)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
