##Retail Price Predictor
**This Jupyter notebook is a Retail Price Predictor experiment.**
The data scientist wants to use a grocery item's name, store name, and city to guess its price.


**📦 Part 1: Bringing In the Tools & Looking at the Lego Pieces**

Before building anything, we need to gather our tools (libraries) and unpack our dataset.
• import pandas as pd: Pandas is like Excel inside Python. ( We use it to build data tables called "DataFrames" to hold our grocery information.)
• import numpy as np: NumPy is a super-fast math calculator. ( It helps with complex array operations and handling empty spaces (NaN).)
• import matplotlib.pyplot as plt & import seaborn as sns: These are the art supplies. ( They allow us to draw charts, plots, and maps.)
• df = pd.read_csv(...): This opens the data file (global_retail.csv) so the computer can read it.

### What did the Data Scientist find?

By running df.info(), df.describe(), and looking for missing values, they noticed the data was very messy:
• Columns like brand and country_code were 100% empty (missing).
• The category column was 93.3% empty.
• There were 20 different currencies (like EUR, USD, INR), making prices hard to compare directly because 1 Euro does not equal 1 Indian Rupee.

### 🧹 Part 2: The Big Clean-Up (Data Preprocessing)

A robot brain cannot learn from broken data. The data scientist fixed the mess with these operations:
1. Throwing away the trash (df.drop(...)): They completely deleted the brand and country_code columns because they were entirely empty.
                                           They also dropped price_is_discounted because every single row was False (useless information).
3. Fixing Dates (pd.to_datetime): The date column was saved as text.
                                  They converted it into a real calendar date format so they could extract the day and month.
5. Filling in the blanks (.fillna()): If an item was missing a name but had a product code, they looked up other items with the same code to patch the missing names.
6. Narrowing Focus (The EUR Filter): To keep things fair, they created a separate dataset called df_eur containing only items priced in Euros (EUR).
                                     This stopped the currency confusion.
