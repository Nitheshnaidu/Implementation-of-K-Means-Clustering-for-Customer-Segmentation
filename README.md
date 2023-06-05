# Implementation of K-Means Clustering for Customer Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## EQUIPMENTS REQUIRED:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## ALGORITHM:
1. Import the necessary packages using import statement.
2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3. Import KMeans and use for loop to cluster the data.
4. Predict the cluster and plot data graphs.
5. Print the outputs and end the program.

## PROGRAM:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: A.NITHISH
Register Number: 212220040103 
*/
```

```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")

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
plt.xlabel("No. of Clusters")
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
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="yellow",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="pink",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="purple",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## OUTPUT:
#### Data.head() value :

![image](https://github.com/vishnudorigundla/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94175324/96cd8e44-f496-4b88-8873-54df932c3d6e)

#### Data.info() value :

![image](https://github.com/vishnudorigundla/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94175324/6ec08183-36fc-4daf-b9c2-85a25cba3f88)

#### Null values :

![image](https://github.com/vishnudorigundla/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94175324/4972fd18-b621-465b-b1cb-5f9d8ccfc583)

#### Fit & append method for KMeans :

![image](https://github.com/vishnudorigundla/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94175324/d40e12b7-31fc-4ae8-a1a0-e0e956931839)

#### Pyplot graph for Elbow method :

![image](https://github.com/vishnudorigundla/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94175324/3391b805-be02-4e0d-b6f1-59a608a385c3)

#### Number of clusters in KMeans :

![image](https://github.com/vishnudorigundla/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94175324/5c1a43ca-466f-442e-8488-03381cea8d59)

#### y_pred values :

![image](https://github.com/vishnudorigundla/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94175324/e0f7247d-ccf8-4442-9620-c61f0dc44b0a)

#### Customer segments graph :

![image](https://github.com/vishnudorigundla/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94175324/464757e3-2078-4837-a244-e04333736243)


## RESULT:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
