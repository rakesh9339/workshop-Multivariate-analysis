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


 #  Types of Bivariate Analysis:
 #(i) Numerical & Numerical

sns.scatterplot (dd['Date_of_Journey'],dd['Dep_Time'])
![image](https://user-images.githubusercontent.com/121115650/229035020-a55890c1-bbaf-4c59-9a4e-6105416b18ff.png)

#(ii) Numerical & Categorical

sns.barplot (x=dd['Duration'],y=dd['Price'])
![image](https://user-images.githubusercontent.com/121115650/229035490-3744d2dd-cefc-4917-96db-81448a88f784.png)

sns.barplot(x=dd["Arrival_Time"],y=dd["Price"],data=dd)
![image](https://user-images.githubusercontent.com/121115650/229035632-70d61306-94b5-4480-a4a6-72f14fbc5086.png)

states=dd.loc[:,["Duration","Price"]]

states=states.groupby(by=["Duration"]).sum().sort_values(by="Price")

sns.barplot(x=states.index,y="Price",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("Duration")

plt.ylabel=("Price")

plt.show()
![image](https://user-images.githubusercontent.com/121115650/229035719-93329faf-c0bc-47b3-8f3a-446460ed6f90.png)

# Multivariate Analysis

dd.corr()

data = np.random.randint(low = 1, high = 100, size = (10, 10))

print("The data to be plotted:\n")

print(data)

hm = sns.heatmap(data = data)

plt.show()

![image](https://user-images.githubusercontent.com/121115650/229035897-c78812ac-7868-4d1d-834f-accdaf040c64.png)
