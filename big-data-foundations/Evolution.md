### C. EVOLUTION
Why did Hadoop and Spark become necessary in the first place?<br>
Don't memorize the names.<br>
Understand the historical problem.<br>

**Stage 1 — File systems** <br>
Originally:<br>
application<br>
      ↓<br>
files<br>
For example:<br>
customer.txt<br>
orders.csv<br>
employees.csv<br>
Simple.<br>

But then organizations started accumulating enormous quantities of files.<br>
**Problems:** <br>
difficult querying<br>
duplication<br>
consistency issues<br>
poor concurrent access<br>
difficult management<br>
So we needed something better.<br>

**Stage 2 — Databases** <br>
Enter databases.<br>
Application<br>
     ↓<br>
Database<br>
     ↓<br>
Tables<br>

Databases gave us:<br>

structured storage<br>
indexing<br>
querying<br>
transactions<br>
concurrency control<br>

Then came the relational model.

**Stage 3 — RDBMS**
Relational Database Management Systems organize information into related tables.<br>
Example:<br>
CUSTOMERS
---------
customer_id
name
city

ORDERS<br>
------<br>
order_id<br>
customer_id<br>
amount<br>
date<br>

And SQL lets us ask:<br>
SELECT ...<br>
FROM ...<br>
WHERE ...<br>
JOIN ...<br>
GROUP BY ...<br>

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
Operational databases<br>
        ↓<br>
      ETL/ELT<br>
        ↓<br>
 DATA WAREHOUSE<br>
        ↓<br>
 BI / Analytics<br>
 
 Example question:<br>
"What were our quarterly sales by region over the last five years?"<br>
This is very different from:<br>
"Create this customer's order."<br>
The first is analytical.<br>
The second is transactional.<br>
That distinction will matter enormously later:<br>
**OLTP<br>
vs<br>
OLAP<br>**

**Stage 5 — Distributed Systems**
Now comes the big shift.<br>
Instead of:<br>
ONE HUGE COMPUTER <br>
we use: <br>
        CLUSTER
 ┌──────┬──────┬──────┐
 │Node 1│Node 2│Node 3│
 └──────┴──────┴──────┘
 Data and computation can be distributed across multiple machines.<br>
 WHY?<br>
 Because one machine has limits.<br>
 If you need:<br>
 500 TB storage<br>
 you could try buying one gigantic machine.<br>
 But it may be:<br>
 expensive<br>
difficult to scale<br>
a single point of failure<br>
difficult to upgrade<br>
Instead:<br>
100 machines x 5 TB <br>
can provide distributed storage.<br>
This gives us the idea of:<br>
**Horizontal scaling** <br>
rather than simply buying a more powerful machine.<br>

**Stage 6 — Hadoop**
Hadoop emerged as a major open-source ecosystem for distributed storage and processing.<br>
The simplified architecture:<br>
                 HADOOP
                   │
        ┌──────────┴──────────┐
        ↓                     ↓
      HDFS                 MapReduce
   Distributed             Distributed
    Storage                Processing

 









