<h1 align="center"> SQL and Databases </h1>
<br/><br/>

## 1. What are key differences between relational and non relational databases 
### Answer
>1. Data Model: RDBs use a relational model, which organizes data into tables with rows and columns, and uses relationships to connect data across multiple tables. NoSQL databases, on the other hand, use a variety of data models such as key-value, document, graph, and column-family. Each of these models is optimized for different types of data and use cases. 

>2. Schemas: RDBs use a fixed schema, which means that the structure of the data must be defined in advance and can't be changed easily. NoSQL databases, in contrast, are often schema-less, which allows for more flexible and dynamic data models. 

>3. Queries: RDBs use a structured query language (SQL) to retrieve and manipulate data. NoSQL databases use a variety of query languages and often provide more flexible querying options. 
Performance: RDBs are generally better suited for complex queries and transactions, and can handle high concurrency. NoSQL databases, on the other hand, are optimized for high performance and scalability, and can handle large amounts of unstructured data.

>4. Data Integrity: RDBs provide ACID (Atomicity, Consistency, Isolation, Durability) transaction, which ensures that data is stored and retrieved reliably and consistently. NoSQL databases often provide a weaker form of data integrity, and focus on availability and partition tolerance. 

>5. Data Distribution: RDBs can be distributed across multiple servers, but it requires a lot of effort and configuration to achieve. NoSQL databases are designed for distributed data, and can be easily partitioned across multiple nodes. 

>6. Handling Large Volume of Data: RDBs can handle large volume of data but it requires a lot of effort to scale them horizontally. NoSQL databases are designed to handle large volume of data with minimal overhead. 


| **Level** | **Expectaions** |
|-----------|-------------|
| **L1**    | bad         |
| **L2**    | Ok          |
| **L3**    | Good        |
---

## 1. What is CAP theorem
### Answer
> The CAP theorem, also known as Brewer's theorem, states that it is impossible for a distributed system to simultaneously provide all three of the following guarantees: 
>>1. Consistency: all nodes in the system see the same data at the same time.
>>2. Availability: every request to the system receives a response, without guarantee that it contains the most recent version of the data. 
>>3. Partition tolerance: the system continues to function even when network partitions occur. 

>The CAP theorem states that a distributed system can only provide at most two of these guarantees at the same time. For example, a system that prioritizes consistency and partition tolerance may not be highly available, while a system that prioritizes availability and partition tolerance may not provide strong consistency guarantees. 
It's important to note that the CAP theorem is a theoretical concept, and that in practice, a distributed system might be able to achieve a good trade-off between the three guarantees depending on the use case and the specific implementation. 
The CAP theorem is often used to help guide the design and implementation of distributed systems, and can be a useful tool for understanding the trade-offs that must be made when building a distributed system. 

| **Level** | **Expectaions** |
|-----------|-------------|
| **L1**    | bad         |
| **L2**    | Ok          |
| **L3**    | Good        |
---


## 1. What are indexes. Describe types of indexes. Clustered unclustered 
### Answer
>Indexes are data structures that are used to improve the performance of queries in a relational database management system (RDBMS). They are used to quickly locate specific rows or sets of rows in a table based on the values in one or more columns. 

There are two main types of indexes in RDBMS: 
>>1. Clustered indexes: A clustered index determines the physical order of the data in a table. Each table can have only one clustered index, because the data rows themselves can be sorted and stored in only one order. The clustered index is usually created on the primary key column, because the primary key values are unique and are used to identify each row. 
>>2. Non-clustered indexes: A non-clustered index does not determine the physical order of the data in a table, but it contains a pointer to the actual data rows. Each table can have multiple non-clustered indexes. Non-clustered indexes are often used to improve the performance of queries that retrieve data based on values in specific columns other than the primary key. 

>An index allows the database to find and retrieve specific rows much faster than scanning every row in a table. 
Indexes can be created on one or multiple columns of a table and can be created as unique or non-unique. In addition, indexes can be created on computed columns and can be filtered to include only certain rows. 
 
| **Level** | **Expectaions** |
|-----------|-------------|
| **L1**    | bad         |
| **L2**    | Ok          |
| **L3**    | Good        |
---


## 1. What is stored procedure 
### Answer
>Stored procedures are pre-compiled, reusable scripts or blocks of code that are stored in a database and can be called by applications or other stored procedures. They are used to perform specific tasks or operations in a database and are executed on the server side. Stored procedures are commonly used to perform actions such as data validation, data manipulation, and complex queries that involve multiple tables or operations. 
>>Pros
1. Improved performance: Stored procedures are pre-compiled, which means they are executed more quickly than ad-hoc queries. This is particularly true for complex or frequently used operations. 
2. Security: Stored procedures can be set to execute with a specific level of privilege, which can help to secure the data in a database. 
3. Reusability: Stored procedures can be called multiple times by different applications or other stored procedures, which helps to reduce development time and improve consistency. 
4. Abstraction: Stored procedures can be used to abstract the underlying database structure from the application, which makes it easier to make changes to the database without affecting the application. 
5. Easy to maintain: Stored procedures can be easily modified, tested and deployed, which makes it easier to maintain the database. 

>>Cons
1. Limited portability: Stored procedures are specific to a particular RDBMS, which makes it harder to move the database to a different platform. 
2. Difficulty in testing: Stored procedures can be difficult to test, especially when they involve multiple tables or complex operations. 
3. Limited flexibility: Stored procedures are typically written in a specific programming language and are not as flexible as using an object-relational mapping (ORM) tool or other data access layer. 
4. Difficult to debug: Stored procedures can be difficult to debug, especially when they are complex or have been written by someone else. 
5. Limited scalability: Stored procedures can be less scalable than other data access methods, especially when they are used to perform complex queries or operations. 

| **Level** | **Expectaions** |
|-----------|-------------|
| **L1**    | bad         |
| **L2**    | Ok          |
| **L3**    | Good        |
---


## 1. What is join 
### Answer