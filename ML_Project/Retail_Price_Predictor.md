# Retail Price Predictor

This Jupyter notebook is a Retail Price Predictor experiment. The data scientist wants to use a grocery item's name, store name, and city to guess its price.

---

## 📦 Part 1: Bringing In the Tools & Looking at the Lego Pieces

Before building anything, we need to gather our tools (libraries) and unpack our dataset.

* `import pandas as pd`: Pandas is like Excel inside Python. We use it to build data tables called "DataFrames" to hold our grocery information.
* `import numpy as np`: NumPy is a super-fast math calculator. It helps with complex array operations and handling empty spaces (`NaN`).
* `import matplotlib.pyplot as plt` & `import seaborn as sns`: These are the art supplies. They allow us to draw charts, plots, and maps.
* `df = pd.read_csv(...)`: This opens the data file (`global_retail.csv`) so the computer can read it.

### What did the Data Scientist find?

By running `df.info()`, `df.describe()`, and looking for missing values, they noticed the data was very messy:

* Columns like `brand` and `country_code` were 100% empty (missing).
* The `category` column was 93.3% empty.
* There were 20 different currencies (like EUR, USD, INR), making prices hard to compare directly because 1 Euro does not equal 1 Indian Rupee.

---

---
## 🧹 Part 2: The Big Clean-Up (Data Preprocessing)

A robot brain cannot learn from broken data. The data scientist fixed the mess with these operations:

1. **Throwing away the trash** `(df.drop(...))`: They completely deleted the brand and country_code columns because they were entirely empty. They also dropped price_is_discounted because every single row was False (useless information).
2. **Fixing Dates** `(pd.to_datetime)`: The date column was saved as text. They converted it into a real calendar date format so they could extract the day and month.
3. **Filling in the blanks** `(.fillna())`: If an item was missing a name but had a product code, they looked up other items with the same code to patch the missing names.
4. **Narrowing Focus** `(The EUR Filter)`: To keep things fair, they created a separate dataset called `df_eur` containing only items priced in Euros (EUR). This stopped the currency confusion.

## 🤖 Part 3: Teaching the Robot Brains (Machine Learning)

The scientist tried three different types of machine learning algorithms to predict prices.

1. The Neighbor Matcher **(KNN - K-Nearest Neighbors)**

• How it works: To guess the price of a new apple, KNN looks at the (K) closest matching items it already knows about (e.g., 3 or 5 other apples) and takes their average price.
• The Text Problem & TF-IDF: Computers only understand numbers, not words. The scientist used TfidfVectorizer to convert text ("Orient. Salat 200g") into mathematical scores based on how unique the words are.
• Location Trick **(OneHotEncoder)**: This converts categorical store names and cities into a grid of binary 0s and 1s so the model can process location math.

2. The Line Drawer **(Linear Regression)**

• How it works: It tries to draw a straight line of best fit through the data. For example, as words get fancier or stores get more expensive, the price goes up steadily.

3. The Strict Teachers **(Ridge and Lasso Regression)**

• How it works: Standard Linear Regression can overthink things **(called overfitting)**. Ridge and Lasso are smarter variations that add a penalty parameter **(alpha)** to keep the model's coefficients small and realistic. Lasso can even completely ignore useless words by shrinking their importance to zero.


## 📊 Part 4: Scoring the Models (How well did they do?)

To see if the brain is smart, we check three vital math metrics:
• MAE (Mean Absolute Error): The average dollar amount the computer was off by. Lower is better.
• RMSE (Root Mean Squared Error): Similar to MAE, but it heavily punishes the computer for making massive, wild guesses. Lower is better.
• `(R^{2})` Score (R-squared): The grade of the model (from \(-\infty \) to \(1\)). A score of \(1\) is a perfect exam; a score below \(0\) means the model is worse than just blindly guessing the average price every time.


| Model Experiment | MAE (Error) | $R^{2}$ Score (Grade) | Who Won? |
| :--- | :--- | :--- | :--- |
| **Baseline** (Blindly guessing average) | 1.2812 | Below 0 | Failing Grade |
| **First KNN** (Plain) | 1.3205 | -0.0729 | Terrible (Worse than guessing) |
| **Tuned KNN + TF-IDF** Text Processing | 0.9785 | 0.0710 | Best KNN (Off by less than a Euro) |
| **Linear Regression** | 1.0206 | 0.3693 | Decent Grade |
| **Ridge Regression** (alpha=0.1) | 0.9826 | **0.4132** | 🏆 **Ultimate Winner!** Best balance of low error and high grade. |


## 🧠 Critical Concepts & Formulas MUST Remember

If you want to recreate this experiment or pass a data science test, memorize these fundamental pillars:

### 1. The Outlier Detector: IQR (Interquartile Range) Formula

How do you mathematically prove a price is a weird outlier (like a €5,030 potato)? You use the formula executed in cell `[47]`:

$$
\text{IQR} = Q3 - Q1
$$
$$
\text{Upper Bound} = Q3 + (1.5 \times \text{IQR})
$$
$$
\text{Lower Bound} = Q1 - (1.5 \times \text{IQR})
$$

Any data point higher than the **Upper Bound** or lower than the **Lower Bound** is flagged as an outlier.

### 2. The Grouped Validation Rule (`GroupKFold`)

*   **Never mix validation groups:** If you split your data randomly, the model might see "Pampers Diapers T4" in training and then try to predict "Pampers Diapers T4" in testing. That is cheating (**Data Leakage**).
*   **The Method:** Use `GroupKFold` or `GroupShuffleSplit` on the `product_code` column. This forces the computer to test its skills only on completely unseen products, proving it actually learned how to price things rather than just memorising them.

### 3. The Automation Pipeline (`Pipeline`)

*   **Stop isolated steps:** Instead of cleaning text, encoding locations, and running regressions in isolated, messy steps, bind them together.
*   **The Solution:** Use Scikit-Learn’s `Pipeline` and `ColumnTransformer`. It packages your entire data assembly line into a single object (`pipeline.fit()` and `pipeline.predict()`).


---

