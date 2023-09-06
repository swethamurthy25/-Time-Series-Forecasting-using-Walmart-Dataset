# Code Implementation and Results

### Reading the Walmart dataset:

```python
# Reading the Walmart dataset and displaying the first 10 rows
import pandas as pd
import numpy as np
walmart_sales = pd.read_csv('C:/Users/sweth/Desktop/ASU_IT/Fall 2022/IFT 512 - Advanced Big data Analysis/Project/walmart-sales-dataset-of-45stores.csv')
walmart_sales.head(10)
```

![image](https://github.com/swethamurthy25/-Time-Series-Forecasting-using-Walmart-Dataset/assets/112581595/0fb759b6-fda3-4a29-a4b4-0b35879a9c19)

_____________________________________________________________________________________________________________________________________________________________


### Defining the basic function and metadata – to identify data frame shape and duplicate rows

```python
# Define Basic Functions
def get_metadata(dataframe):
    print("\nBASIC INFORMATION\n")
    print(dataframe.info())
    print("=" * 100)
    print("STATISTICAL INFORMATION")
    display(dataframe.describe(include='all'))
    print("=" * 100)
    print("Dataframe Shape\n", dataframe.shape)
    print("=" * 100)
    print("Number of Duplicate Rows\n", dataframe.duplicated().sum())
    print("=" * 100)
    print("NULL Values Check")
    for col in dataframe.columns:
        print(col, dataframe[col].isnull().sum())
    print("=" * 100)
    print("Sample Data")
    display(dataframe.head(3))
    print("=" * 100)
```

![image](https://github.com/swethamurthy25/-Time-Series-Forecasting-using-Walmart-Dataset/assets/112581595/a9502500-d954-4f3a-ae17-1165ddd08dbf)

```python
get_metadata(walmart_sales)
```

![image](https://github.com/swethamurthy25/-Time-Series-Forecasting-using-Walmart-Dataset/assets/112581595/fbe8bf32-1e54-479c-98d0-e1a2bc1a9b65)

![image](https://github.com/swethamurthy25/-Time-Series-Forecasting-using-Walmart-Dataset/assets/112581595/58308196-8de8-4f55-8f07-b17af96176b9)

![image](https://github.com/swethamurthy25/-Time-Series-Forecasting-using-Walmart-Dataset/assets/112581595/8d79e7e9-5257-4f89-84b4-ab12b93b5545)



_____________________________________________________________________________________________________________________________________________________________

## Value Distribution using seaborn and matplotlib

Here Each of the columns and its values is distributed in the form of a graph.

```python
# Value Distribution 
import seaborn as sns
import matplotlib.pyplot as plt
import warnings
warnings.filterwarnings('ignore')
pd.set_option('display.float_format', lambda x: '%.3f' % x)
walmart_sales.plot(subplots=True, grid=True, figsize=(15,15))
```

![image](https://github.com/swethamurthy25/-Time-Series-Forecasting-using-Walmart-Dataset/assets/112581595/65e8e21e-8451-4392-9ba3-edee4f0952fa)

![image](https://github.com/swethamurthy25/-Time-Series-Forecasting-using-Walmart-Dataset/assets/112581595/9726b7ad-06fe-4fc6-9386-e508fd5a2c41)

![image](https://github.com/swethamurthy25/-Time-Series-Forecasting-using-Walmart-Dataset/assets/112581595/6f99acc6-9809-41f8-a8b6-1693461088d8)

________________________________________________________________________________________________________________________________________________________________

## Displaying all the 45 stores of Walmart and its weekly sales distribution

Here the x-axis of the graph contains the store details from 1 to 45 and the y-axis of the graph contains the weekly sales details.

```python
# Display stores and their weekly sales
fig, ax = plt.subplots(figsize=(20,5))
sns.barplot(data=walmart_sales, x="Store", y="Weekly_Sales", hue="Holiday_Flag", ax=ax, palette = "viridis")
```

![image](https://github.com/swethamurthy25/-Time-Series-Forecasting-using-Walmart-Dataset/assets/112581595/0dfc7a4d-21fb-4769-9b1b-01bc3fe4c1a6)

______________________________________________________________________________________________________________________________________________________________


