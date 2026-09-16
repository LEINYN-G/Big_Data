## Objective
What data is being generated, what form does it take, how much is being generated, how quickly does it arrive, 
how trustworthy is it, what value can we extract, and what kind of infrastructure is required to handle it?

## A. FOUNDATION

-> We'll begin with five deceptively simple concepts:

Data
  ↓
Dataset
  ↓
Observation
  ↓
Variable
  ↓
Feature

These words are often used interchangeably by beginners, but they aren't exactly the same.

# 1. Data
At the most basic level: 
Data is recorded informateion about entities, events, measurements, or observations.

Imagine a food-delivery company.

Every time somebody orders food, the system may record:


| Order ID | Customer | Restaurant | Distance | Order Value | Delivery Time | Payment | Rating |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 78291 | C102 | R45 | 4.7 km | ₹630 | 31 min | UPI | 4 |

That's data.
But notice something important:
Data isn't necessarily numbers.
It can be:
42
"Delhi"
"UPI"
4.7
true
2026-09-15 13:45
[image]
[audio]
[video]
This becomes extremely important when we reach data types and Big Data variety.

## 2. Dataset
A dataset is a collection of related data organized for a particular purpose.


| Order ID | Distance | Value | Delivery Time | Rating |
| :--- | :--- | :--- | :--- | :--- |
| 1001 | 2.4 km | ₹450 | 24 min | 5 |
| 1002 | 7.1 km | ₹820 | 43 min | 3 |
| 1003 | 1.8 km | ₹320 | 19 min | 5 |
| 1004 | 5.5 km | ₹710 | 37 min | 4 |

This entire table is a *dataset*.
you could save it as:
order.csv
or
orders.parquet
or store it in:
PostgreSQL
MySQL
MongoDB
Data Warehouse
Data Lake

And that already gives us our first connection between data science and data engineering.

## 3. Observation
An *observation* is one individual record/entity/event in a dataset.
In our example:
1001 | 2.4 | 450 | 24 | 5
is one observation.
So:
| Structure |
| :--- |
| **Dataset** |
| ├── Observation 1 |
| ├── Observation 2 |
| ├── Observation 3 |
| └── Observation 4 |

If you have:
1,000,000 orders
you potentially have:
1,000,000 observations
This distinction becomes incredibly important later when we talk about:

| Topic |
| :--- |
| **Sampling** |
| **Train/test splits** |
| **Statistical inference** |
| **Distributed processing** |
| **Data imbalance** |
| **Outliers** |

### 4. Variable

A variable represents a characteristic that can take different values across observations.

| variables |
| :--- |
| Distance |
| Order Value |
| Delivery Time |
| Rating |
| Payment Method |

for example:

| Observation | Delivery Time (min) |
| :--- | :--- |
| Observation 1 | 24 |
| Observation 2 | 43 |
| Observation 3 | 19 |
| Observation 4 | 37 |

The variable is:
Delivery Time
The value changes from observation to observation.

### 5. Feature

Now we reach an important Data Science distinction.

A feature is an input variable used by a model to make a prediction or perform some analytical task.

Suppose our goal is:
### Predict whether a food delivery will arrive late.
We might have:
Distance
Weather
Traffic
Restaurant preparation time
Time of day
Number of active delivery partners
-> These can become features.
Out target could be:
Late = 0/1
So conceptually:


| **FEATURES** | <ul><li>Distance</li><li>Traffic</li><li>Weather</li><li>Restaurant Prep Time</li><li>Time of Day</li></ul> |
|<li> **↓** </li> | <li>**MACHINE LEARNING MODEL**</li>|
| <li>**Output**</li> | <li>**TARGET**</li> | <ul><li>Late?</li></ul> |











