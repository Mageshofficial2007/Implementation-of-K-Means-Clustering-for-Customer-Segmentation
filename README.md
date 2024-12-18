# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import pandas and matplotlib.pyplot

2.Read the dataset and transform it

3.Import KMeans and fit the data in the model

4.Plot the Cluster graph 
  

## Program:
```

Program to implement the K Means Clustering for Customer Segmentation.
Developed by: MAGESH BOOPATHI.M
RegisterNumber:  24900855
```

```python
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("C:/Users/LENOVO/Downloads/Mall_Customers.csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = [] #Within-Cluster Sum of Square
#It is the sum of squared distance between each point & the centroid in a cluster.

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
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
![Screenshot 2024-12-18 210823](https://github.com/user-attachments/assets/ebccd506-a072-48fb-a7d0-294fb99e40ed)
![Screenshot 2024-12-18 211129](https://github.com/user-attachments/assets/31dd5e94-a74f-475c-9b5a-db324a9df1a6)

![Screenshot 2024-12-18 211141](https://github.com/user-attachments/assets/55ef7fdd-1b7f-4731-bc7c-5c9b5b86aeef)

![Screenshot 2024-12-18 211155](https://github.com/user-attachments/assets/ff16e6d4-839f-40e1-8ec7-0e29517c4a8b)
![Screenshot 2024-12-18 211206](https://github.com/user-attachments/assets/b01df95d-b455-4bbe-9bf7-326c655eea50)
![Screenshot 2024-12-18 211221](https://github.com/user-attachments/assets/848d827b-923a-42da-9b1e-2bf30ec0c1b5)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
