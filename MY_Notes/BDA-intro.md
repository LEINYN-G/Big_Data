## Big Data Introduction
Big Data requires new tools for processing and analysis of a large volume of data.<br>
For example, unstructured, NoSQL (not only SQL) data or Hadoop compatible system data.

Following are selected key terms and their meanings, 
which are essential to understand the topics discussed in this chapter:

1. __Application__: Means application software or a collection of software components. For example, software for<br>
                    acquiring, storing, visualizing and analyzing data. An application performs a group of coordinated<br>
                    activities, functions and tasks.

2. __Application Programming Interface (API)__: Refers to a software component which enables a user to access an<br>
                                                application, service or software that runs on a local or remote computing<br>
                                                platform. An API initiates running of the application on receiving the<br>
                                                message(s) from the user-end. An API sends the user-end messages to the<br>
                                                other-end software. The other-end software sends responses or messages to<br>
                                                the API and the user.

3. __Data Model__: Refers to a map or schema, which represents the inherent properties of the data. The map shows<br>
                   groupings of the data elements, such as records or tables, and their associations. A model does<br>
                   not depend on software using that data.

4. __Data Repository__: It refers to a collection of data. A data-seeking program relies upon the data repository for<br>
                       reporting. The examples of repositories are database, flat file and spreadsheet.<br>
                       [Repository in English means a group which can be relied upon to look for required things, such as<br>
                       special information or knowledge. For example, a repository of paintings by various artists.]

5. __Data Store__: It refers to a data repository of a set of objects. Data store is a general concept for data<br>
                  repositories,such as database, relational database, flat file, spreadsheet, mail server, web server<br>
                  and directory services. The objects in data store model are instances of the classes which the<br>
                  database schemas define. A data store may consist of multiple schemas or may consist of data in only<br>
                  one schema. Example of only one scheme for a data store is a relational database.

### Distributed Data Store refers to a data store distributed over multiple nodes. Apache Cassandra is one example of a distributed data store.

6. __Database (DB)__: It refers to a grouping of tables for the collection of data. A table ensures a systematic<br>
                     way for accessing, updating and managing data. A database pertains to the applications, which<br>
                     access them. A database is a repository for querying the required information for analytics,<br>
                     processes, intelligence and knowledge discovery. The databases can be distributed across a<br>
                     network consisting of servers and data warehouses.

7. __Table__: It refers to a presentation which consists of row fields and column fields. The values at the fields<br>
             can be number, date, hyperlink, image, object or text of a document.

8. __Flat File__: It means a file in which data cannot be picked from in between and must be read from the beginning<br>
                 to be interpreted. A file consisting of a single-table file is called a flat file. An example of a<br>
                 flat file is a csv (comma-separated value) file. A flat file is also a data repository.

9. __Flat File Database__: Refers to a database in which each record is in a separate row unrelated to each other.<br>
                          CSV File refers to a file with comma-separated values. For example, CS101<br>
                          , "Theory of Computations", 7.8 when a student's grade is 7.8 in subject code CS101 and<br>
                          subject "Theory of Computations".

10. __Name-Value Pair__: Refers to constructs used in which a field consists of name and the corresponding value after<br>
                        that. For example, a name value pair is date, ""Oct. 20, 2018"", chocolates_sold, 178;

11. __Key-Value Pair__: Refers to a construct used in which a field is the key, which pairs with the corresponding<br>
                       value or values after the key. For example, consider a tabular record, ""Oct. 20, 2018""";<br>
                       """chocolates_sold'"", 178. The date is the primary key for finding the date of the record<br>
                       and chocolates_sold is the secondary key for finding the number of chocolates sold.

#### Hash Key-Value Pair refers to the construct in which a hash function computes a key for indexing and search, and distributing the entries (key/value pairs) across an array of slots (also called buckets).

12. __Spreadsheet__: Refers to the recording of data in fields within rows and columns. A field means a specific column<br>
                    of a row used for recording information. The values in fields associates a program,<br>
                    such as Microsoft Excel 2013. An example of a spreadsheet application is accounting.<br>
                    The application manages, analyzes and enables new values either directly or using formulae which<br>
                    contain the relationships of a field with cells and rows. Examples of functions are SUMIF and<br>
                    COUNTIF, delete duplicate entries, sort using multiple keys,filter single or multiple columns,<br>
                    create a filter using filtering criteria or rules for multi-fields, and create top-n lists<br>
                    for values or percentages.
    
13. __Stream Analytics__: Refers to a method of computing continuously, i.e, even while events take place flows through<br>
                          the system.
    
14. __Database Maintenance (DBM)__: Refers to a set of tasks which improves a database. DBM uses function for<br>
                                    improving performance (such as by query planning and optimization), freeing-up<br>
                                    storage space, update internal statistics, checking data errors and hardware faults.
    
15. __Database Administration (DBA)__: Refers to the function of managing and maintaining Database Managemen system.<br>
                                       Software regularly a database administering personnel has many responsibilities,<br>
                                       such as installation, configuration, database design, implementation, upgrading,<br>
                                       evaluation of database features, reliable backup and recovery methods for the dtabase.
    
16. __DBMS__: Refers to a software system which contains a set of program especially designed for creation and management<br>
              of data stored in a database. Transactions can be performed with database/RDBMS.


17.__Relational Database Management System (RDBMS)__: Refers to a software system used for creation relational databases<br>
and management of data which are stored in a relational database. RDBMS functions perform the transactions on the<br>
 relational database.Examples of RDBMS are MvSOL. PostGreSOL(Oracle database created using PL/SQL) and Microsoft<br>
 SQL server using T-SQL.

18.__Transaction (trans+action)__: means two interrelated sets of operations, actions or instructions. A transaction is a set of actions which accesses, changes, updates, appends or deletes various data. A command "connect enables transfers between DBMS software and a database. The database in return connects the DBMS. AD example of this is query transfer from a system to a database. The database in return transfers the answer of the query.

19.__SQL__: Stands for Structured Query Language. It is a language used for schema creation and schent modifications,<br>
            data-access control, creating an SQL client and creating an SQL server for a database. It is language<br>
            for managing relational databases, and viewing, querying and changing<br>
            (update, insert, append er delete)databases.

20.__Database Connection__: Refers a function DB_connect open which an application calls to connect to enable the access<br>
                            to the DBMS. The application calls the function DB_connect close () to disable the access.

21.__Database Connectivity (DBC)__: Refers to a standard application programming interface (API), which provides<br>
                                    connectivity for accessing the DBMSs. A DBC design is independent of the DB system<br>
                                    and 05 used. An application written using a DBC can therefore perform operations<br>
                                    or actions at both the client and the DB server end. Little changes in code suffice<br>
                                    for accessing the data. Two examples of DBCs are Oper Database Connectivity (ODBC)<br>
                                    and Java Database Connectivity (JDBC).

22.__Database Connectivity Driver__: Refers to a translation layer which resides between an application using the<br>
                                     application and the DBMS. The application uses DBC functions through a DBC driver<br>
                                     manager with which it is linked. A DBC driver manager manages the drivers associated<br>
                                     with the DBMSs. The DBC driver sends the queries to a DBMS. Drivers exist for many<br>
                                     data sources and all major DBMSS.

#### DB2 is IBM RDBMS. DB2 has many features. For example, triggers, stored procedures and dynamic bitmapped indexing for number of application types, such as traditional host-based applications, client server-based applications and business intelligence applications.

23.__Data Warehouse__: Refers to sharable data, data stores and databases in an enterprise. It consists of<br>
                       integrated, subject oriented (such as finance, human resources and business) and non-volatile<br>
                       data stores, which update regularly.
