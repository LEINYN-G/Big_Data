## Big Data Introduction
Big Data requires new tools for processing and analysis of a large volume of data.<br>
For example, unstructured, NoSQL (not only SQL) data or Hadoop compatible system data.

Following are selected key terms and their meanings, 
which are essential to understand the topics discussed in this chapter:

1. __Application__: Means application software or a collection of software components.<br>
                    For example,<br>
                    software for acquiring, storing, visualizing and analyzing data.<br>
                    An application performs a group of coordinated activities, functions and tasks.

2.__Application Programming Interface (API)__: Refers to a software component which enables a user to<br>
                                               access an application, service or software that runs on a local or <br>
                                               remote computing platform. An API initiates running of the application on<br>
                                               receiving the message(s) from the user-end. An API sends the user-end<br>
                                               messages to the other-end software. The other-end software sends responses<br>
                                               or messages to the API and the user.

3.__Data Model__: Refers to a map or schema, which represents the inherent properties of the data.<br>
                  The map shows groupings of the data elements, such as records or tables, and their associations.<br>
                  A model does not depend on software using that data.

4.__Data Repository__: It refers to a collection of data. A data-seeking program relies upon the data repository for<br>
                       reporting. The examples of repositories are database, flat file and spreadsheet.<br>
                       [Repository in English means a group which can be relied upon to look for required things, such as<br>
                       special information or knowledge. For example, a repository of paintings by various artists.]

5.__Data Store__: It refers to a data repository of a set of objects. Data store is a general concept for data<br>
                  repositories,such as database, relational database, flat file, spreadsheet, mail server, web server<br>
                  and directory services. The objects in data store model are instances of the classes which the<br>
                  database schemas define. A data store may consist of multiple schemas or may consist of data in only<br>
                  one schema. Example of only one scheme for a data store is a relational database.

### Distributed Data Store refers to a data store distributed over multiple nodes. Apache Cassandra is one example of a distributed data store.

6.__Database (DB)__: It refers to a grouping of tables for the collection of data. A table ensures a systematic<br>
                     way for accessing, updating and managing data. A database pertains to the applications, which<br>
                     access them. A database is a repository for querying the required information for analytics,<br>
                     processes, intelligence and knowledge discovery. The databases can be distributed across a<br>
                     network consisting of servers and data warehouses.

7.__Table__: It refers to a presentation which consists of row fields and column fields. The values at the fields<br>
             can be number, date, hyperlink, image, object or text of a document.

8.__Flat File__: It means a file in which data cannot be picked from in between and must be read from the beginning<br>
                 to be interpreted. A file consisting of a single-table file is called a flat file. An example of a<br>
                 flat file is a csv (comma-separated value) file. A flat file is also a data repository.

9.__Flat File Database__: Refers to a database in which each record is in a separate row unrelated to each other.<br>
                          CSV File refers to a file with comma-separated values. For example, CS101<br>
                          , "Theory of Computations", 7.8 when a student's grade is 7.8 in subject code CS101 and<br>
                          subject "Theory of Computations".

10.__Name-Value Pair__: Refers to constructs used in which a field consists of name and the corresponding value after<br>
                        that. For example, a name value pair is date, ""Oct. 20, 2018"", chocolates_sold, 178;

11.__Key-Value Pair__: Refers to a construct used in which a field is the key, which pairs with the corresponding<br>
                       value or values after the key. For example, consider a tabular record, ""Oct. 20, 2018""";<br>
                       """chocolates_sold'"", 178. The date is the primary key for finding the date of the record<br>
                       and chocolates_sold is the secondary key for finding the number of chocolates sold.

### Hash Key-Value Pair refers to the construct in which a hash function computes a key for indexing and search, and distributing the entries (key/value pairs) across an array of slots (also called buckets).

12.__Spreadsheet__: Refers to the recording of data in fields within rows and columns. A field means a specific column<br>
                    of a row used for recording information. The values in fields associates a program,<br>
                    such as Microsoft Excel 2013. An example of a spreadsheet application is accounting.<br>
                    The application manages, analyzes and enables new values either directly or using formulae which<br>
                    contain the relationships of a field with cells and rows. Examples of functions are SUMIF and<br>
                    COUNTIF, delete duplicate entries, sort using multiple keys,filter single or multiple columns,<br>
                    create a filter using filtering criteria or rules for multi-fields, and create top-n lists<br>
                    for values or percentages.
