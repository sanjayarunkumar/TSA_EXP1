## Devloped by: Sreevalsan V
## Register Number: 212223240158
##  Date: 25-02-2025

# Ex.No: 01A PLOT A TIME SERIES DATA


# AIM:
To Develop a python program to Plot a time series data with respect to time.

# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Convert date column into datetime datatype and set it as index.
4. Resamples all the sales in a day using sum() and plot the Total sales per day
5. Add the necessary details to the plot and display the graph.

# PROGRAM:
```py

from matplotlib import pyplot as plt
import pandas as pd

df=pd.read_csv("/content/test.csv")

df.head()

df['date']=pd.to_datetime(df['date'])

df.dtypes

df.set_index('date',inplace=True)

df_resampled = df['onpromotion'].resample('D').sum()
df_resampled.plot(kind='line',label='Total Sales', color='black')
plt.title('Time Series Plot of the sales on different days of a month')
plt.xlabel('Day')
plt.ylabel('Total sales per day')
plt.legend()
plt.grid(True)
plt.show()
```

# OUTPUT:

![alt text](image.png)

# RESULT:
Thus we have created the python code for plotting the time series of given data.
