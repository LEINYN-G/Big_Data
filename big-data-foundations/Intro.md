## Objective
What data is being generated?<br> What form does it take?<br> How much is being generated?<br> How quickly does it arrive?<br>
How trustworthy is it?<br> What value can we extract?<br> What kind of infrastructure is required to handle it?

## A. FOUNDATION

-> We'll begin with five deceptively simple concepts:

Data<br>
  ↓ <br>
Dataset<br>
  ↓ <br>
Observation<br>
  ↓ <br>
Variable<br>
  ↓ <br>
Feature<br>

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
PostgreSQL<br>
MySQL<br>
MongoDB<br>
Data Warehouse<br>
Data Lake<br>

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
1,000,000 observations<br>
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

The variable is:<br>
Delivery Time<br>
The value changes from observation to observation.

### 5. Feature

Now we reach an important Data Science distinction.

**A feature is an input variable used by a model to make a prediction or perform some analytical task.** <br>

Suppose our goal is:
### Predict whether a food delivery will arrive late.
We might have:<br>
Distance<br>
Weather<br>
Traffic<br>
Restaurant preparation time<br>
Time of day<br>
Number of active delivery partners<br>
-> These can become features.<br>
Out target could be:<br>
Late = 0/1<br>
So conceptually:


| **FEATURES** | <ul><li>Distance</li><li>Traffic</li><li>Weather</li><li>Restaurant Prep Time</li><li>Time of Day</li></ul>
<li> ↓ </li><li> MACHINE LEARNING MODEL </li><li>TARGET</li>
<li>Late?</li>
Very important:
Variable ≠ always feature.<br>
### A variable becomes a feature in the context of a particular modeling problem.
For example:<br>
Customer ID<br>
is a variable<br>
But it might be useless--or even harmful--as a predictive feature.

🔥 A real-world exercise
Let's make this practical immediately.
Imagine you are building a system for an employment platform.
Suppose you collect:

| Candidate Fields |
| :--- |
| Candidate ID |
| Age |
| Degree |
| Branch |
| CGPA |
| Skills |
| Projects |
| Internships |
| Location |
| Expected Salary |
| Years of Experience |
| Applied Job |
| Interview Score |
| Hired |

Now classify them.

## Dataset
The complete collection of candidate records.

## Observation
One candidate/application record.

## Variables
Age, CGPA, branch, skills, etc.

## Features
Depends on what you're predicting.
If:
Target = Hired
then:
| Selection Criteria |
| :--- |
| CGPA |
| Skills |
| Projects |
| Internships |
| Experience |
| Interview Score |

could potentially be feartures.<br>
But be careful.<br>
### If the model is supposed to predict whether someone will be hired before the interview, then:<br>
*Interview Score* 
**would create data leakage.<br>
why?<br>
Because you're using information that wouldn't be available at prediction time.
"would this information legitimately exist at the moment my system makes its prediction?"**
well, this is called real world ML. -_-

Now we're moving to our central idea i.e.
### BIG DATA CONCEPT
A common conceptual framework describes Big Data using the Vs:

| Big Data Characteristics |
| :--- |
| Volume |
| Velocity |
| Variety |
| Veracity |
| Value |

Sometimes you'll also encounter additional Vs such as:
Variability
Visualization

But your syllabus uses the classic five, so we'll master those first.
1. Volume
Volume = how much data exists.
Imagine a small restaurant.
It might generate:
100 order/day

The real question becomes:  
**How do i store, process, search, replicate, and analyze massive amounts of data efficiently?**

That's where distributed systems become imprtant.

### 2. Velocity

Velocity = how quickly data is generated, transmitted, and/or needs to be processed.
Compare:
Batch<br>
Sales data -> collect all day -> Process at midnight
versus:
Sensor
 ↓
Event
 ↓
Network
 ↓
Processing system
 ↓
Decision

Imagine a stock-trading system.<br>
If data arrives milliseconds apart, processing it tomorrow is useless.<br>

Similarly:

| Use Case |
| :--- |
| Fraud detection |
| Network intrusion detection |
| Autonomous vehicles |
| IoT monitoring |
| Real-time recommendation |
can require low-latency processing.<br>
This eventually leads us toward technologies such as:
| kafka |
| Spark Streaming |
| Flink |
| kinesis |

### 3. Variety
This one is particularly important.<br>
Real-world data isn't always:<br>
ID | Age | Salary
you might have:<br>
**Structured**

ID | Age | Salary

**Semi-structured**
```json
{
  "customer_id": 102,
  "name": "Alex",
  "skills": ["Python", "SQL"]
}
```
**Unstructured
image<br>
video<br>
audio<br>
PDF<br>
email<br>
social-media post<br>
Now imagine an autonomous vehicle.
It could process:
camera images<br>
LiDAR<br>
GPS<br>
radar<br>
vehicle telemetry<br>
maps<br>
audio<br>
weather data<br>
That is variety.<br>

### 4. Veracity
This is one of the most important concepts for becoming a serious data scientist.<br>
**Veracity=how trustworthy/reliable the data is.**

Real-world systems contain:<br>

missing values<br>
duplicate records<br>
incorrect measurements<br>
inconsistent formats<br>
sensor errors<br>
fraudulent data<br>
human input errors<br>
stale information<br>
So:<br>
**Big Data isn't automatically useful simply because it's big.**<br>
you can have:<br>
10 TB of garbage<br>
and it is still garbage.<br>
This leads directly to your **Data Quality** section later.<br>

### 5. Value
The ultimate question:<br>
Can we derive useful decisions, insights, predictions, or actions from the data?<br>
Suppose an e-commerce company has<br>
100 TB of customer data<br>
but doesn't know what itself isn't valuable.<br>

But suppose analysis reveals:<br>
Customers who view product X twice within 24 hours are highly likely to purchase product Y.<br>
Now you can potentially build:<br>
Recommendation system<br>
       ↓
Personalized recommendations<br>
       ↓
Higher conversion<br>
       ↓
Business value<br>
That's **Value**

**The Big Data mental model**

```text
                BIG DATA
                    │
       ┌────────────┼────────────┐
       ↓            ↓            ↓
    VOLUME       VELOCITY      VARIETY
       │            │            │
    How much?   How fast?    What forms?
       │            │            │
       └────────────┼────────────┘
                    ↓
                 VERACITY
                    │
              Can we trust it?
                    ↓
                  VALUE
                    │
              Can we use it?
```
A better way to think about it is:<br>
**Data whose scale, speed, diversity, or complexity creates challenges that traditional data-processing approaches struggle to handle efficiently.** <br>

### C. EVOLUTION
So exactly **Why did Hadoop and Spark become necessary in the first palce?** <br>
Don't memorize the names. <br>
Understand the historical problem.<br>
Stage 1 — File systems <br>
Originally: <br>
application <br>
    ↓ <br>
files <br>

e.g. <br>
customers.txt, orders.csv, employees.csv <br>
Simple.<br>
But then organizations started accumulating enormous quantities of files.<br>
Problems:<br>

difficult querying<br>
duplication<br>
consistency issues<br>
poor concurrent access<br>
difficult management<br>

So we needed something better.










