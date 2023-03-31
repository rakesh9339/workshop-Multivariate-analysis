Developed by: Rakesh J.S
Regno: 212222230114
```

import pandas as pd

import numpy as np

import seaborn as sns

import matplotlib.pyplot as plt

import io

from google.colab import files

uploaded = files.upload()

dd = pd.read_csv(io.BytesIO(uploaded['FlightInformation.csv']))

print(dd)

# output
 #  Types of Bivariate Analysis:
 #(i) Numerical & Numerical

sns.scatterplot (dd['Date_of_Journey'],dd['Dep_Time'])
/home/sec/Downloads/Scrt1.png

#(ii) Numerical & Categorical

sns.barplot (x=dd['Duration'],y=dd['Price'])
/home/sec/Downloads/scrt2.png

sns.barplot(x=dd["Arrival_Time"],y=dd["Price"],data=dd)
/home/sec/Downloads/scrt3.png

states=dd.loc[:,["Duration","Price"]]

states=states.groupby(by=["Duration"]).sum().sort_values(by="Price")

sns.barplot(x=states.index,y="Price",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("Duration")

plt.ylabel=("Price")

plt.show()
/home/sec/Downloads/scrt4.png

# Multivariate Analysis

dd.corr()

data = np.random.randint(low = 1, high = 100, size = (10, 10))

print("The data to be plotted:\n")

print(data)

hm = sns.heatmap(data = data)

plt.show()

/home/sec/Downloads/scrt5.png
```
