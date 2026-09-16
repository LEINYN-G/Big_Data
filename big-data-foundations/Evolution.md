### C. EVOLUTION
Why did Hadoop and Spark become necessary in the first place?<br>
Don't memorize the names.<br>
Understand the historical problem.<br>

**Stage 1 — File systems** <br>
Originally:<br>
```text
application
      ↓
files
```
For example:<br>
```text
customer.txt
orders.csv
employees.csv
Simple.
```
But then organizations started accumulating enormous quantities of files.<br>
**Problems:** <br>
-> Difficult Querying<br>
-> Duplication<br>
-> Consistency issues<br>
-> Poor concurrent access<br>
-> Difficult management<br>
So we needed something better.<br>

**Stage 2 — Databases** <br>
```text
Enter databases.
Application
     ↓
Database
     ↓
Tables
```

Databases gave us:<br>

-> structured storage<br>
-> indexing<br>
-> querying<br>
-> transactions<br>
-> concurrency control<br>

Then came the relational model.

**Stage 3 — RDBMS**
Relational Database Management Systems organize information into related tables.<br>
Example:<br>
```text
CUSTOMERS
---------
customer_id
name
city
```

```text
ORDERS
------
order_id
customer_id
amount
date
```

And SQL lets us ask:<br>
```text
SELECT ...
FROM ...
WHERE ...
JOIN ...
GROUP BY ...
```
But then data became:<br>
Larger<br>
+ <br>
Faster<br>
+ <br>
more diverse<br>
and organizations needed analytical systems.<br>

**Stage 4 — Data Warehouses**
A data warehouse is optimized primarily for analytical workloads.<br>
Think:<br>
```text
Operational databases
        ↓
      ETL/ELT
        ↓
 DATA WAREHOUSE
        ↓
 BI / Analytics
```
 
 Example question:<br>
"What were our quarterly sales by region over the last five years?"<br>
This is very different from:<br>
"Create this customer's order."<br>
The first is analytical.<br>
The second is transactional.<br>
That distinction will matter enormously later:<br>
```text
**OLTP
vs
OLAP**
```

**Stage 5 — Distributed Systems**
Now comes the big shift.<br>
Instead of:<br>
ONE HUGE COMPUTER <br>
we use: <br>
```text
        CLUSTER
 ┌──────┬──────┬──────┐
 │Node 1│Node 2│Node 3│
 └──────┴──────┴──────┘
 ```
 Data and computation can be distributed across multiple machines.<br>
 WHY?<br>
 Because one machine has limits.<br>
 If you need:<br>
 500 TB storage<br>
 you could try buying one gigantic machine.<br>
 But it may be:<br>
 ```text
 expensive
difficult to scale
a single point of failure
difficult to upgrade
```
Instead:<br>
100 machines x 5 TB <br>
can provide distributed storage.<br>
This gives us the idea of:<br>
**Horizontal scaling** <br>
rather than simply buying a more powerful machine.<br>

**Stage 6 — Hadoop**
Hadoop emerged as a major open-source ecosystem for distributed storage and processing.<br>
The simplified architecture:<br>
 ```text
       HADOOP
          │
  ┌───────┴───────┐
  ↓               ↓
 HDFS         MapReduce
(Distributed  (Distributed
  Storage)     Processing)
```
**HDFS**
Think:<br>
"How can I store enormous datasets across many machines?"<br>

MapReduce<br>
Think:<br>
"How can I process enormous datasets across many machines?"<br>

**Stage 7 — Spark**
Then came Apache Spark, which made large-scale data processing much more flexible and generally much faster for many workloads than traditional disk-heavy MapReduce approaches.<br>
Conceptually:<br>
```text
                 SPARK
                   │
        ┌──────────┼──────────┐
        ↓          ↓          ↓
      SQL       MLlib      Streaming
        │          │          │
        └──────────┼──────────┘
                   ↓
             Distributed
              Processing
```
We'll eventually actually use Spark—not merely memorize its definition.<br>
For example:
```py
df.groupBy("city").avg("salary")
```
and understand what is happening underneath.<br>


 









