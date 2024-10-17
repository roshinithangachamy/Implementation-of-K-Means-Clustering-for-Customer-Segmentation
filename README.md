# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1.Start
2.Data Preparation: Load and explore customer data.
3.Determine Optimal Clusters: Use the Elbow Method to find the best number of clusters.
4.Apply K Means Clustering: Perform clustering on customer data.
Visualize Segmented Customers: Plot clustered data to visualize customer segments.
5.End 

## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: T.Roshini
RegisterNumber: 212223230175


import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data
data.head()
from sklearn.cluster import KMeans
wcss=[]
for i in range(1,11):
    Kmeans=KMeans(n_clusters=i,init="k-means++")
    Kmeans.fit(data.iloc[:,3:])
    wcss.append(Kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred=km.predict(data.iloc[:,3:])
y_pred
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
df0.head()
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")

```

## Output:

Data:

![image](https://github.com/user-attachments/assets/4c839c6c-4557-4e1d-99d6-0dd646f5815c)

Head:

![image](https://github.com/user-attachments/assets/cac81080-f8da-4ad8-9580-7778f6408f3f)

![image](https://github.com/user-attachments/assets/2693595e-3883-4e4b-b9ce-603c070f24b0)

Elbow Method:

![download](https://github.com/user-attachments/assets/dcc49c06-904a-4169-839d-01efa0b211ad)

![image](https://github.com/user-attachments/assets/a500478c-864c-4345-b26d-d0e108c3db23)

Y Predict:

![image](https://github.com/user-attachments/assets/1f6779f4-eb00-4124-95bf-ab64db3fe961)

df0.head:

![image](https://github.com/user-attachments/assets/ffad03f0-06c4-4fe1-80c8-916261a93d45)

Customer Segments:

![image](https://github.com/user-attachments/assets/2a7fc9aa-0a99-4e45-bf07-2525dfc53d1a)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
