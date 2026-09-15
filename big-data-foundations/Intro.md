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
Dataset
│
├── Observation 1
├── Observation 2
├── Observation 3
└── Observation 4
If you have:
1,000,000 orders
you potentially have:
1,000,000 observations
This distinction becomes incredibly important later when we talk about:





