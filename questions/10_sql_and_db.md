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

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | No Answer                   |                 |
| **L2**    | Right Answer                |                 |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
---
<br/><br/>

## 2. What’s the difference between MSSQL and SQL lite 
### Answer
>SQL Server (MSSQL) and SQLite are both relational database management systems, but they have some key differences

> * **Scalability:** SQL Server is a full-fledged enterprise database system and can handle large amounts of data and concurrent users, while SQLite is designed for lighter-weight, embedded database applications.
> * **Complexity:** SQL Server has many advanced features such as user management, stored procedures, and triggers, making it a more complex system to use, while SQLite is simpler and easier to use.
> * **Cost:** SQL Server is a commercial product and requires a license, while SQLite is open source and free to use.
> * **Performance:** SQL Server is optimized for performance and can handle high-performance workloads, while SQLite is designed for smaller, lower-performance applications.
> * **Deployment:** SQL Server typically requires a dedicated server for deployment, while SQLite can be easily embedded within an application and deployed on a wide range of platforms.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | No Answer                   |                 |
| **L2**    | Right Answer                |                 |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
---
<br/><br/>

## 3. What is CAP theorem
### Answer
> The CAP theorem, also known as Brewer's theorem, states that it is impossible for a distributed system to simultaneously provide all three of the following guarantees: 
>>1. Consistency: all nodes in the system see the same data at the same time.
>>2. Availability: every request to the system receives a response, without guarantee that it contains the most recent version of the data. 
>>3. Partition tolerance: the system continues to function even when network partitions occur. 

>The CAP theorem states that a distributed system can only provide at most two of these guarantees at the same time. For example, a system that prioritizes consistency and partition tolerance may not be highly available, while a system that prioritizes availability and partition tolerance may not provide strong consistency guarantees. 
It's important to note that the CAP theorem is a theoretical concept, and that in practice, a distributed system might be able to achieve a good trade-off between the three guarantees depending on the use case and the specific implementation. 
The CAP theorem is often used to help guide the design and implementation of distributed systems, and can be a useful tool for understanding the trade-offs that must be made when building a distributed system. 

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | No Answer                   |                 |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
| **L3**    | Right Answer                |                 |
---
<br/><br/>

## 4. What are indexes. Describe types of indexes. Clustered unclustered 
### Answer
>Indexes are data structures that are used to improve the performance of queries in a relational database management system (RDBMS). They are used to quickly locate specific rows or sets of rows in a table based on the values in one or more columns. 

>There are two main types of indexes in RDBMS: 
* Clustered indexes: A clustered index determines the physical order of the data in a table. Each table can have only one clustered index, because the data rows themselves can be sorted and stored in only one order. The clustered index is usually created on the primary key column, because the primary key values are unique and are used to identify each row. 
* Non-clustered indexes: A non-clustered index does not determine the physical order of the data in a table, but it contains a pointer to the actual data rows. Each table can have multiple non-clustered indexes. Non-clustered indexes are often used to improve the performance of queries that retrieve data based on values in specific columns other than the primary key. 

>An index allows the database to find and retrieve specific rows much faster than scanning every row in a table. 
Indexes can be created on one or multiple columns of a table and can be created as unique or non-unique. In addition, indexes can be created on computed columns and can be filtered to include only certain rows. 
 
| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | No Answer                   |                 |
| **L2**    | Right Answer                |                 |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
---
<br/><br/>

## 5. What is stored procedure 
### Answer
>Stored procedures are pre-compiled, reusable scripts or blocks of code that are stored in a database and can be called by applications or other stored procedures. They are used to perform specific tasks or operations in a database and are executed on the server side. Stored procedures are commonly used to perform actions such as data validation, data manipulation, and complex queries that involve multiple tables or operations. 
>>Pros
* Improved performance: Stored procedures are pre-compiled, which means they are executed more quickly than ad-hoc queries. This is particularly true for complex or frequently used operations. 
* Security: Stored procedures can be set to execute with a specific level of privilege, which can help to secure the data in a database. 
* Reusability: Stored procedures can be called multiple times by different applications or other stored procedures, which helps to reduce development time and improve consistency. 
* Abstraction: Stored procedures can be used to abstract the underlying database structure from the application, which makes it easier to make changes to the database without affecting the application. 
* Easy to maintain: Stored procedures can be easily modified, tested and deployed, which makes it easier to maintain the database. 

>>Cons
* Limited portability: Stored procedures are specific to a particular RDBMS, which makes it harder to move the database to a different platform. 
* Difficulty in testing: Stored procedures can be difficult to test, especially when they involve multiple tables or complex operations. 
* Limited flexibility: Stored procedures are typically written in a specific programming language and are not as flexible as using an object-relational mapping (ORM) tool or other data access layer. 
* Difficult to debug: Stored procedures can be difficult to debug, especially when they are complex or have been written by someone else. 
* Limited scalability: Stored procedures can be less scalable than other data access methods, especially when they are used to perform complex queries or operations. 

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | No Answer                   |                 |
| **L2**    | Right Answer                |                 |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
---
<br/><br/>

## 6. What is join operation?
### Answer
>In SQL, a join is a way to combine data from two or more tables in a relational database based on a related column between them. The related column is often called the join key or join condition. The join operation creates a new table that combines the rows from the tables that participate in the join. The resulting table contains all the columns from both tables, but only the rows that match the join condition.

>There are several types of joins in SQL:

>`INNER JOIN`: This is the most common type of join. It returns only the rows that have matching values in both tables.
```SQL
SELECT *
FROM orders
JOIN customers
ON orders.customer_id = customers.customer_id;
```
>LEFT JOIN (or LEFT OUTER JOIN): This type of join returns all the rows from the left table (the first table in the join clause), and the matching rows from the right table. If there is no match, the result will contain NULL values in the columns of the right table.
```SQL
SELECT *
FROM orders
LEFT JOIN customers
ON orders.customer_id = customers.customer_id;
```
>RIGHT JOIN (or RIGHT OUTER JOIN): This type of join is similar to the LEFT JOIN, but it returns all the rows from the right table and the matching rows from the left table.
```SQL
SELECT *
FROM orders
RIGHT JOIN customers
ON orders.customer_id = customers.customer_id;
```
>FULL JOIN (or FULL OUTER JOIN): This type of join returns all the rows from both tables, and the matching rows. If there is no match, the result will contain NULL values in the columns of the non-matching table.
```SQL
SELECT *
FROM orders
FULL JOIN customers
ON orders.customer_id = customers.customer_id;
```
>In summary, joins allow you to combine data from multiple tables in a relational database based on a related column, and return the result in a single table. Different types of joins return different sets of data, depending on whether there is a match or not.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | In Depth Knowledge          |                 |
---
<br/><br/>

## 7. Are you familiar with NoSQL databases? Can you mention some of them
### Answer
>There are several types of NoSQL databases, including:

* **Document databases**, which store data in semi-structured format, such as JSON or BSON. Examples include **MongoDB** and **Couchbase**.
* **Key-value databases**, which store data as a collection of key-value pairs. Examples include **Redis** and **Riak**.
* **Column-family databases**, which store data in a column-based format, rather than a row-based format. Examples include **Apache Cassandra** and **Hbase**.
* **Graph databases**, which store data in a graph format, with nodes and edges representing data entities and relationships. Examples include **Neo4j** and **TigerGraph**.
* O**bject-oriented databases**, which store data in an object-oriented format, with each object having its own unique identity and behavior. Examples include **ZODB** and **ObjectDB**.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Not familiar                |                 |
| **L2**    | Probably know couple of them |                 |
| **L3**    | Can mention main types. Have some experience with working with them |                 |
---
<br/><br/>

## 8. What is transaction and how it works?
### Answer
>

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | No Answer                   |                 |
| **L2**    | Right Answer                |                 |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
---
<br/><br/>

## 9. How to use MongoDB in C#
### Answer
>Install the MongoDB.Driver for C#: You can install the MongoDB driver for C# using NuGet Package Manager.
```C#
using MongoDB.Driver;

// Connect to the database
var client = new MongoClient("mongodb://localhost:27017");
var database = client.GetDatabase("test");

// Define the model
public class Book
{
    public ObjectId Id { get; set; }
    public string Title { get; set; }
    public string Author { get; set; }
}

// Perform CRUD operations
var collection = database.GetCollection<Book>("books");

// Insert a document
var book = new Book { Title = "MongoDB Basics", Author = "John Doe" };
await collection.InsertOneAsync(book);

// Find a document
var filter = Builders<Book>.Filter.Eq("Author", "John Doe");
var result = await collection.Find(filter).ToListAsync();

// Update a document
var update = Builders<Book>.Update.Set("Title", "MongoDB Advanced");
await collection.UpdateOneAsync(filter, update);

// Delete a document
await collection.DeleteOneAsync(filter);
```

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Don't know                  |                 |
| **L2**    | Probably know a bit         |                 |
| **L3**    | Full answer                 |                 |
---
<br/><br/>

## 9. Are you familiar with DynamoDb. What are pros and cons of using it?
### Answer
>Amazon DynamoDB is a fully managed NoSQL database service provided by Amazon Web Services (AWS). It is a document-oriented database that is designed for scalability and high performance. <br\ >
>DynamoDB is a key-value database, which means that data is stored as key-value pairs, where the key is a unique identifier for each item and the value is the data itself. The keys are used to quickly look up items in the database, and the values can be any data type, including complex data structures such as lists and maps.

>Some of the key benefits of using DynamoDB include:

> * **Scalability:** DynamoDB is designed to scale automatically and handle large amounts of data and traffic, making it a good choice for applications with unpredictable workloads.

> * **High performance:** DynamoDB provides fast and predictable performance, with single-digit millisecond latencies for read and write operations.

> * **Flexibility:** DynamoDB supports flexible data modeling, and allows you to store and retrieve any amount of data, at any time, without any prior knowledge of the data model.

> * **Global reach:** DynamoDB is a fully managed service that is available globally, so you can use it to store and retrieve data from anywhere in the world.

Some of the potential drawbacks of using DynamoDB include:

> * **Cost:** DynamoDB can be more expensive than other NoSQL databases, especially for high-volume, high-write workloads.

> * **Lack of control:** Because DynamoDB is a fully managed service, you have limited control over the underlying infrastructure, which can be a drawback for some users.

> * **Complexity:** DynamoDB has a complex data model, which can make it difficult to learn and use, especially for users who are used to more traditional relational databases.

Overall, DynamoDB is a good choice for applications that require high scalability, high performance, and flexible data modeling, and are willing to trade off some control and complexity for the benefits of a fully managed service.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Don't know                  |                 |
| **L2**    | Probably know a bit         |                 |
| **L3**    | Full answer                 |                 |
---
<br/><br/>

# TODO: Add questions about other types of databases