#EX.NO:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR
+
+STEP 6: Use zscore of to remove outliers

# Coding and Output
           import pandas as pd
           import numpy as np
           import matplotlib.pyplot as plt
           from scipy import stats
from google.colab import files
uploaded = files.upload()
import pandas as pd

df = pd.read_csv("SAMPLEIDS (6) (2).csv")df.head()
![image](Screenshot 2026-03-15 162305.png)
df.info()
df.describe()
![image](Screenshot 2026-03-15 191557.png)
df.isnull().sum()
![image](Screenshot 2026-03-15 191607..png)
df.drop_duplicates(inplace=True)
z = np.abs(stats.zscore(df.select_dtypes(include=[np.number])))
print(z)
![image](Screenshot 2026-03-15 191619.png)
df_clean.to_csv("cleaned_data.csv", index=False)
df.head()
![image](Screenshot 2026-03-15 191632.png)
df.shape
![image](
df.columns
![image](Screenshot 2026-03-15 191642.png)
import matplotlib.pyplot as plt

plt.boxplot(df.select_dtypes(include=[np.number]))
plt.show()
![image](Screenshot 2026-03-15 191711.png)
from scipy import stats
import numpy as np

z = np.abs(stats.zscore(df.select_dtypes(include=[np.number])))
print(z)
![image](Screenshot 2026-03-15 191722.png)
df_clean.shape
![image](Screenshot 2026-03-15 191732.png)
# Result
         The following data cleaning has been done successfully
