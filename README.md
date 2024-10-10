# EX8-Implementation of Hierarchical Clustering using linkage methods
## DATE:
## AIM:
To implement Hierarchical Clustering using single and complete linkage method

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Compute the distance between every pair of data points,resulting in a distance matrix.
2. Assign each data point to its own individual cluster.
3. Using a linkage criterion,find the two closest cluster and merge them.
4. Visualize the hierarchical clustering as a dendrogram.
## Program:
```

Program to implement Hierarchical Clustering using single and complete linkage method
Developed by: K DEEKSHITHA
RegisterNumber:  2305002005


import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from scipy.cluster.hierarchy import dendrogram, linkage,fcluster
from sklearn.preprocessing import StandardScaler
df = pd.read_csv("/content/Hclus_EX8.csv")
df.head()
x = df[['StudentID','Marks']].values
x
z=linkage(x,method='complete')
plt.figure(figsize=(5,2))
plt.title("Dendogram for student segmentation")
labels=range(1,len(df)+1)
dendrogram(z,labels=labels)
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()
max_cluster=2
clusters=fcluster(z,max_cluster,criterion='maxclust')
clusters
plt.figure(figsize=(5,2))
plt.scatter(x[:,0],x[:,1],c=clusters,cmap='rainbow',s=100)
plt.title("Student segmented(Hierarchical clustering)")
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()
z=linkage(x,method='single')
plt.figure(figsize=(5,2))
plt.title("Dendogram for student segmentation")
labels=range(1,len(df)+1)
dendrogram(z,labels=labels)
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()



```

## Output:
![image](https://github.com/user-attachments/assets/2522ce0b-0e6d-440a-b9e5-7d3270187ae1)
![image](https://github.com/user-attachments/assets/9f2c81a7-18b8-40cc-b70c-fe270fc07611)
![image](https://github.com/user-attachments/assets/70039f13-045f-4521-80f2-1ab5dc610a09)
![image](https://github.com/user-attachments/assets/2f154a90-f1a6-4ff0-bcf2-02b2406f60f2)

## Result:
Thus the implementation of Hierarchical Clustering using single and complete linkage method in python programming and verified successfully.
