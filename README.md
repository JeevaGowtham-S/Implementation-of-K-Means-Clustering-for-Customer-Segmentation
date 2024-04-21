# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:

To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:

1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1. Import the necessary packages.
2. Read the given csv file and display the few contents of the data.
3. Import KMeans and use for loop to calculate the within cluster sum of squares the data.
4. Plot the wcss for each iteration, also known as the elbow method plot.
5. Predict the clusters and plot them.

## Program:

Program to implement the K Means Clustering for Customer Segmentation.

Developed by: JEEVAGOWTHAM S
RegisterNumber: 212222230053

```python
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers (1).csv")

data.head()

data.info()
data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
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

## data.head():
![image](https://github.com/JeevaGowtham-S/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118042624/c795d00c-14e1-4c19-8177-005fed2083b8)

## data.info():
![image](https://github.com/JeevaGowtham-S/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118042624/32ea65eb-00ba-48dd-a7ec-69ca8a77775e)


## NULL VALUES:
![image](https://github.com/JeevaGowtham-S/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118042624/5bfb0e9e-d6ae-4bf7-b9aa-64718b6ffb0c)


## ELBOW GRAPH:
![image](https://github.com/JeevaGowtham-S/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118042624/69f7166c-c381-4d1c-bb90-0ba4cf05d65d)

## CLUSTER FORMATION:
![image](https://github.com/JeevaGowtham-S/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118042624/9fcdea4e-5d7a-42b0-935e-96ec5067d7c3)

## PREDICICTED VALUE:
![image](https://github.com/JeevaGowtham-S/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118042624/e79a5080-d08c-4c71-a236-5661e0440483)


## FINAL GRAPH(D/O):
![image](https://github.com/JeevaGowtham-S/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118042624/392b5441-4449-45db-a0c6-9df5d3006cc9)


## Result:

Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
