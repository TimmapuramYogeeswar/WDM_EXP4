### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 03-08-2026
### AIM: To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
### Description:
<div align= "justify">Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, 
  application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. 
  This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, 
  or services to meet the specific needs and preferences of each cluster.</div>
  
### Procedure:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.

### Program:
```python
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

df = pd.read_csv("clustervisitor.csv")

X = df[['Age']]

kmeans = KMeans(n_clusters=3, random_state=42)

df['Cluster'] = kmeans.fit_predict(X)

print(df)

for i in range(3):
    print(f"\nCluster {i}")
    print(df[df['Cluster'] == i])

```
### Output:

<img width="864" height="548" alt="image" src="https://github.com/user-attachments/assets/d7956f5c-d370-472c-a7a1-d2aec64276d1" />

<img width="868" height="475" alt="image" src="https://github.com/user-attachments/assets/ec00e607-125a-4cdb-b0be-bdf3f8fab85a" />

<img width="873" height="209" alt="image" src="https://github.com/user-attachments/assets/e7525adc-94aa-4371-ae53-811eab3d91ae" />



### Visualization:
```python
import matplotlib.pyplot as plt

plt.figure(figsize=(8,5))

for i in range(3):
    cluster = df[df['Cluster'] == i]
    plt.scatter(cluster['Age'], cluster['Cluster'], label=f'Cluster {i}')

plt.scatter(
    kmeans.cluster_centers_,
    range(3),
    color='red',
    marker='X',
    s=200,
    label='Centroids'
)

plt.xlabel("Age")
plt.ylabel("Cluster")
plt.title("Visitor Segmentation using K-Means")
plt.legend()
plt.grid(True)
plt.show()
```
### Output:


<img width="869" height="465" alt="image" src="https://github.com/user-attachments/assets/a4dfb90d-bb43-4710-813d-79766507bb91" />



### Result:
Thus the code has been executed successfully.


