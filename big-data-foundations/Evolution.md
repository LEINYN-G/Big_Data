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






