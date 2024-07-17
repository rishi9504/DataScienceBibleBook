# SQL FOR DATA SCIENCE 

## Introduction To SQL for Data Science
SQL plays an important role in the day-to-day tasks of a data scientist, In the recent 25 Data Seientist job postings on' Facebook; every job posting listed skills with SQL: In the 2020 Linkedin top 10 Startups from Indfa list. 7 have SQL as one of their Most Common Skill. This often underappreciated language is amongst the top skills required not just in India, but worldwide. As long as there is ‘data’ in data science, SQL will remain an important part of it.

While it may be four decades old, SQL remains relevant in the 21% century thanks to a number of key advantages that it offers over the alternatives.

Data Science is the study and analysis of data, inorder to analyze the data; we need to extract it from the database. This is where SQL comes inta the picture.

Many database platforms are modeled after SQL. This is because it has become & standard for, many database systems. As a matter of fact, modern big data systems like Hadoop, and Spark make use of SQL for maintaining relational database systems and processing structured data.
Note: The author hopes that describing the lstallation of any SQL editor won't be necessary and readers will be able to install and use one very easily. If the user faces any issues, we will add an appendix for installing and running commands. 

# Types of Databases
Depending upon the usage requirements, there are the following types of databases available in the market that are used normally. The most used database used by a data scientist is Relational and NoSQL database, but we will learn a little bit about all the others with a brief introduction.

## Centralized database:
A centralized database is a type of database architecture where all data is stored and managed from a single location, often-a mainframe or server, In this architecture, the database server is responsible for storing, managing, and providing access to the data, while the clients access the data through the network.

Centralized databases have several advantages, including:
* Data consistency: Since all data is stored in one place, it is easier to ensure that the data is consistent and up-todate.
* Simplified data management: With a single database, it is easier to manage and maintain data integrity, security, and backup and recovery.
* Reduced data redundancy: Centralfzed databases eliminate the need for redundant data storage, which can reduce storage costs and improve data efficiency,
* Improved data access: Centralized databases can provide faster data access and retrieval, as all data is stored in
ane location.
However, centralized databases also have some disadvantages, including:
+ Single point of faiure: If the database server goes down, all users lose access to the data,
+ Limited scalability: Centralized databases can be difficult to scale as the amount of data and the number of users
grows.
+ Security risks: Centralized databases can be vulperable to security risks, as a single breach could compromise all
data,
* Network dependency: Access to the Ceatralized database ix dependent on the network, which ¢an impact
performance and availability.

Overall, centralized databases are still widely used in various industries, but with the rise of cloud computing and distributed systems, decentralized and distributed database architectures are becoming more popular.

## Distributed database:
A distributed database is a type of database architecture in which data is distribured across multiple computers or nodes in a network. In this architecture, each node has its own copy of the database, and the nodes communicate with each other to ensure data consistency and synchronization:
Distributed databases have several advantages, including:
+ Improved scalability: Distributed databases can handle large amounts of data and users by distributing the
workload across multiple nodes,
+ Improved availability: With multiple copies of the database, if one node fails, the other nodes can continue to provide access to the data.
+ Improved performance: Distributed databases can provide fastee data access and retrieval by distributing the workload across multiple nodes,
+ Improved fault tolerance: Distributed databases can provide fault tolerance by replicating the data across multiple nodes, ensuring that data is available even if some nodes fail.
However, distributed databases also have some issues: 

+ Data consistency: Ensuring data consistency across multiple. nodes can be challenging. as updates to one node
must be synchronized with updates to other nodes.
+ Network latency: Network latency can impact the performance and availability of distributed databases,
- Security risks: Distributed databases can be vulnerable to secarity risks, as data is distributed across multiple
nodes,
+ Complex management; Distributed databases can be more complex to manage than centralized databases, as administrators must ensure data consisteney, synchronization, and security across multiple nodes,  

Overall, distributed databases are becoming more popular with the rise of cloud computing and big data applications, as they can provide improved scalability, availability, and performance. However, designing and managing a distributed database requires careful planning and expertise.
## Personal database
A personal database is a collection of data that is created and managed by an individual for personal use. Personal databases can be used to store and organize a wide range of information, such as contact information, notes, to-do lists, personal finances, and more.

Personal databases can be created using a variety of tools and technologies, ranging from simple spreadsheet prograns like Microsoft Excel or Google Sheets to more sophisticated dutabase management systems like Microsoft Access or MySQL. Some individuals may even choose to create their own custom database systems using programming languages like Python or Java.

The benefits of a personal database include the ability to quickly and easily access and organize information, as well as the ability to analvze and extract insights from data. Personal databases can also be customized to suit individual needs and preferences, allowing individuals to ereate a system that works best for them.

However, there are also potential drawbacks to using a personal database, For example, maintaining a personal database can be time-consuming, and there is a risk of data loss or corruption if proper backups are not maintained.

Additionally, some individuals may lack the technical skills or knowledge required to create and maintain a personal database, which can be a barrier to entry.

Owerall, the decision o use a personal database depends on an individual’s specific needs and preferences, as well as their level of technical expertise. 

## End-user database

An end-user database is a database system that is designed and created by an end-user, typically a non-technical person, for their own personal or business use: End-user databases are intended to be uscd by individuals who may not have the technical skills or knowledge required to create a custom database system from seratch.

End-user databases are typically created using user-friendly, software tools that do not require knowledge of programming or database design concepts. These tools can include Microsoft Access, Google Sheets, or other software programs that provide an intuitive interface for creating and managing databases.

End-user databases can be used for a variety of purposes, such as managing customer information, tracking inventory, or keeping track of personal finances, They are typically smaller in scale and less complex than enterprise level databases, but they can still be powerful tools for organizing and managing data.

One of the benefits of end-user databases is that they allow: individuals to quickly and casily create a custom databases system without the need for extensive technical knowledge or experience.

However, there are also some potential drawbacks to using end-user databases. For example, they may not be as scalable or robust as enterprisefevel databases, and there may be limitations on the amount of data that can be stored and analyzed.

Overall, end-user databases are a useful tool for individualt and small businesses who need to manage and organize data but do net have the resources or expertise to create a custom database system from scratch.

## Commercial database

A commercial database is a database management system that is developed and sold by a commercial software vendor. Commercial databases are designed to meet the needs of large organizations and businesses that require high levels of reliability, scalability, and security.

Commercial databases can be used for a variety of purposes, such as managing customer information, tracking inventory, and analyzing business data, They typically affer advanced features and capabilities such as transaction processing, data warchousing, and business intelligence tools.

Some of the most popular commercial databases include Oracle, Microsoft SQL Server, IBM DB2, and MySQL Enterprise. These databases are used by a wide range of organizations, from small businesses to large corporations, and are often integrated with other software systems and applications.

One of the key benefits of commercial databases is that they are developed and supported by professional software vendors, which ensures a high level of quality and reliability. Commercial databases are also typically welldocumented and offer extensive suppert and training resources.

However, there are also some potential drawbacks to using commercial databases. For example, they can be expensive to purchase and license, and may require specialized hardware and software to run- effectively.

Additionally, they may not be as customizable as open-source or custom-built databases, which can be a limitation for organizations with specific needs or requirements.

Overall, commercial databases are a powerful tool for managing and analyzing data, and are a popular choice for organizations that require a high level of reliability and scalability.

## NoSQL database
A NoSQL database is a type of database management system that is designed fo store and retrieve data in a way that differs from traditional refational databases, Unlike relational databases, NoSQL databases do not use tables, rows, and columns to store data. Instead, they use flexible data models that allow for unstructured and semistructured data to be stored and processed. 

NoSQL databases are often used for large-scale, distributed systems that require high levels of scalability and availability. They are also commonly used for web and mobile applications, where fast access to data is critical.

There are several different types of NoSQL databases, including:

+ Document databases - store data in JSON or BSON format, allowing for flexible and scalable data models.
+ Key-value databases - store data in a simple key-value format, making them ideal for caching and storing session
data.
+ Column-family databases - store dasa in column families, which allows for fast data retrieval and analysis.
 + Graph datsbases: Store data in nodes and edges, making then ideal for storing and ‘processing complex relationships between data elements. 

NoSQL databases offer several advantages over traditional relational databases. They are highly scalable, able to handle large amounts of data and high levels of traffic. They are also highly available, with built-in replication and failover capabilities. In addition, NoSQL databases are often more flexible and faster than relational databases, making them well-suited for modern web and mobile applications. 

However, there are also some potential drawbacks to using NoSQL databases. They can be more complex to manage and maintain than traditional relational databases, and may require specialized skills and expertise. In addition, they may not be as well-suited for applications that require strong consistency and transaction support,which are features typically found in relational databases.

## Operational database

An operational database is a type of database that is designed to support the day-to-day operations of an organization. It's also known as a transactional database, as it is optimized for handling transactions, which are individual actions that modify the data stored in the database.

Operationial databases are typically used for applications such as e-commerce, inventory management, and order processing, where real-time access to up-to-date information is critical, They are designed to handle Large volumes of transactions efficiently and reliably, while also ensuring data integrity and consistency.

One of the key features of operational databases is support for ACID transactions, which stands for Atomicity, Consistency, Isolation, and Durability, This means that transactions are executed in an all-or-nothing manner, ensuring that the database remaining consistent and reliable even in the face of failures or errors.

Operational databases can be implemented using a variety of technologies, including relational databases, NoSQL databases, and in-memory databases. Some of the most populir commercial operational databases include Oracle Database, Microsoft SQL Server, and IBM DB2. 

Overall, operational databases are a critical component of modern business operations, providing the real-time data access and transactional support needed to keep organizations running smoothly and efficiently.

## Relational database

A relational database is a type of database management system (DBMS) that is based on the relational model of data. In a relational database, data is organized into one or more tables, cach of which consists of rows and columns. Each row in a table represents a single record or instance of a particular entity, while each column represents a specific attribute or property of that entity. For example, a table of customers might include columns such as “name”,  “address”, and “phone number”, with each row represeating a single customer.

Relational databases are designed to allow for efficient storage, retrieval, and management of large amounts of structured data. They are widely used in a variety of applications, including banking, healtheare, and e-commerce.

One of the key advantages of relational databases is the ability to use SQL (Structured Query Language) to query and manipulate the data stored in the database. SQL is a powerful and flexible language that allows for complex queries and data manipulation operations, such as filtering, sorting, and aggregating data.

Relational databases also offer several other advantages, including:
+ Data consistency and integrity: The relational model ensures that data is stored in a consistent and standardized
way, and that constraints are enforced to ensure data integrity.
+ Scalability: Relational databases can handle large amounts of data, and can be scaled up or down as needed to
accommodate changing data volumes.
+ Security: Relational databases offer robust security features, such as access control and encryption, to protect sensitive data from unauthorized access.

However, there are also some potential drawbacks to using relational databases. They can be complex to design and manage, and may not be wellsuited for applications that require flexible or unstructured data models. In addition, they may not be as well-suited for applications that require high levels of scalability and performance, such as big data analytics or real-time data processing.

## Cloud database

A cloud database is a type of database that is hosted and accessed through a cloud computing platform or service. Cloud databases can be either relational or NoSQL databases and are designed to provide scalability, flexibility, and cost-effectiveness by eliminating the need for organizations to maintain their own physical database infrastructure.

Some of the key benefits of cloud databases include:

+ Scalability: Cloud databases can scale up or down as needed to accommodate changes in data volume, user demand, or other factors.
+ Accessibility: Cloud databases can be accessed from snywhere with an internet connection, making them particularly useful for distributed teams or remote workers.
+ Cost-effectiveness: Cloud databases eliminate the need [for organizations to invest in their own physical infrastructure, reducing hardware, maintenance, and staffing costs.
+ Security: Cloud databases often come with built-in security features, such as encryption and access control, to protect sensitive data from unauthorized access.

There are also some potential drawbacks to using cloud databases, such as concerns around data privacy and security, as well as the risk of vendor lock-in. Additionally, performance and reliability can be affected by factors such as internet connectivity and cloud provider uptime. 

Some popular cloud database platforms and services include Amazon Web Services (AWS) Relutional Database Service (RDS), Google Cloud SQL, and Microsoft Azure SQL Database.


## Object-oriented database

An object-oriented database (OODB) is 2 type of database that uses object-oriented programming concepts to store and manage data, Unlike traditional relational databases, which store data in tables with fixed schemas, objectorfented databases store data as objects with flexible and dynamic schemas, In an object-oriented database, data is organized into objects, which are instances of classes or types defined in the database schema. Each object has its own unigue identity, state, and behavior, and can be manipulated through methods and messages.

Some of the key benefits of object-oriented databases include:
+ Flexibility: Object-oriented databases can store data of varying complexity and structure, making them wellsuited for managing complex and evolving data models.
+ Efficiency: Object-oriented databases can provide faster access to data than relational databases, since objects can
be accessed directly rather than through complex joins.
+ Reusability: Object-oriented databases allow objects to be reused and extended across different applications,
reducing the need for redundant code and improving software development productivity.
+ Scalahility: Object-oriented databases can scale horizontally by adding more servers, making them well-suited for
applications with high concurrency and throughput requirements; 

There are also some potential drawbacks to using object-oriented databases, such as the need for specialized programming skills, the potential for performance and scalability issues with large datasets, and the lack of standardization across different OODB vendors.

Some popular ehject-oriented database systems include ObjectStore, GemStone/3, and dbdo.

## Graph database
A graph database is a type of database that uses graph theory to store, organize, and query data. In a graph database, data is represented as nodes (also called vertices) and edges (also called relationships), which are used to model and represent the relationships between data entities.

Graph databases are particularly well-suited for data that has complex relationships and strictures, such as social networks, recommendation engines, and supply chain management.

Some of the key benefits of graph datahases include:
+ Flexibility: Graph databases can model and store data of varying complexity and structure, making them wellsuited for managing complex and evolving data models.
+ Performance: Graph databases can provide faster access to data than relational databases, especially for queries that involve complex relationships and teaversals,
+ Scalability: Graph databases can scale horizontally by adding more servers, making them well-suited for applications with high concurrency and throughput requirements.
+ Insights: Graph databases can provide valuable insights and visualizations of complex relationships and patterns
in the data, which can be used for analytics, business intelligence, and machine learning. 

There are also some potential drawbacks to using graph databases, such as the need for specialized programming skills, the complexity of querying data with many relationships, and the potential for performance and scalability issues with large datasets.

Some popular graph database systems include Neo4j, Amazon Neptune, and Microsoft Azure Cosmos DB.

#### What is a Query?

In the context of databases, a query is a request for information from a database. It is a way of asking the database it reteieve speeific data based on certain conditions or criteria.

Queries can take different forms depending on the type of database and the programming language used to interact with it. In general, a query involves specifying what data to retrieve, which tables or collections to search, and what conditions or filters to apply.

For example, a query in SQL (Structured Query Language) might look like this:

`SELECT name, age, city FROM customers WHERE age > 30;`

This query is asking the database to retrieve the name, age, and city of all customers where the age is greater than 30. The database would then return a result set that matches the criteria specified in the query.

Queries can be used for a variery of purposes; such as gencrating reports, performing analysis, and updating or deleting data. Well-crafted queries can help improve the performance and efficiency of database operations, as they allow you to retrieve only the data you need, and avoid unnecessary processing and resource usage.

#### What is SQL?

SQL is a standard language for storing, manipulating, and retrieving data in databases. SQL stands for Struetured Query Language. SQL lets you access and manipulates databases. SQL became a standard of the American National Standards Institute (ANSI) in 1986 and of the International Organfzation for Standardization {IS0} in 1987.

#### Types Of SQL KEYS
##### Primary Key
A primary key is a column or set of columns in a database table that uniquely identifies each row or record in the table. The primary key is used to-enforce data integrity and ensure that each tow in the table is unique and
identifiable.
A primary key can be a single column or a combination of columns in the table, and it must have the following
properties:
1. Uniqueness: Each value in the primary Key column or columns must be unique and cannot be repeated.
2. Non-nullability: The value in the primary key column or columns cannot be null or empty.
3. Immutability: The value in the primary key column or columns should not change over time.

The primary key is used to identify and retrieve specific rows in the table, and it can also be used as a foreign key in other tables to establish relationships between tables.
It is a best practice to choose a primary key that is simple, numeric, and does not change frequently to ensure efficient indexing and searching. Examples of primary keys include unique identifier columns, such as a customer ID, order ID, or product ID.

##### Foreign Key
A foreign key is a column or et of columns in a database table that refers to the primary key of another table. The foreign key establishes a relationship between two tables, and it is used to maintain referential integrity and enforce data constraints.

When a foreign key is defined in a table, it refers o the primary key of another table, called the referenced table.
The foreign key column contains values that match the primary key values of the referenced table, ensuring that each value in the foreign key column is valid and refers to an existing row in the referenced table.

The use of foreign keys ensures that the data in the tables is consistent and accurate. When a record is deleted or updated in the referenced table, the corresponding records fn the table containing the foreign key are also deleted or updated automatically, preventing orphaned or invalid data.

For example, consider a database with two tables: Customers and Orders.
The Customers table has a primary key column called CustomerID, and the Orders rable has a foreign key column called CustomerID that refers to the  CustomerlD column in the Customers table. This establishes a refationship between the two tables, where each order is associated with a specific customer.

Foreign keys are an essential component of database design and are used o maintain data integrity and consistency in relational databases.

##### Composite Key
A composite key, also known as a composite primary key, is a combination of two or more columns in a database table that is used to uniquely identify ecach row in the table. Unlike a simple primary kev that consists of a single column, a composite key is made up of multiple columns.

In a composite key, each column in the key contributes to the uniqueness of the key. That is, the combination of values in all the columns must be unique for each row in the table, The columns that make up the composite key can be of any data type, such as integers, strings, or dates.

Composite keys are used when a single column cannot uniquely identify each row in a table. For example, consider a table that stores data about studeats, where the combination of the student’s name and date of birth uniquely identifies each student. In this case, the name and date of birth columns could be combined to form a  composite key for the table.

Composite keys are also used in many-to-many relationships between tables, where the key is composed of foreign keys from two or more tables. In such cases, the composite key is used to enforce the relationship between the tables and ensure data integrity.

While composite keys can be useful in certain situations, they can also be more complex to work with than simple primary keys, and they can make queries and indexing more difficult, As a best practice, it is recommended to use simple primary keys wherever possible and to use composite keys only when necessary to ensure data integrity. 

##### Super Key

In a relational database, a super key is 4 set of one or more columns in a table that uniquely identifies each row in that table. A super key can be thought of as a superset of a primary key, meaning that it includes all of the columns that make up the primary key, as well as additional columns that are not strictly necessary for uniqueness.

For example, consider a table that stores information about employees, with columns for EmployeelD, FirstName, LastName, and Email. The combination of EmployeelD and Email is & super key for this table, as it uniquely identifies each row, even though only EmploveelD is strictly necessary for uniqueness. 

Similarly, the combination of FirstName and LastName is also a super key for this table. Super keys are useful for database design and optimization, as they provide a way to identify potential candidate keys and determine which key should be used as the primary key for a table. They also provide a way to ensure data integrity and eliminate duplicate records.

It is worth noting that not all super keys are suitable for use as primary keys, 4s some may be too complex or inefficient for use in indexing and querying. Primary keys are typically chosen based on their simplicity, efficiency, and suitability for use in indexing and querying.

##### Alternate Key

An alternate key, also known as a candidate key, is a set of one or more columns in a database table that can be used-to uniquely identify each row in the table. Like a primary key, an alternate key is a candidate for use as the unique identifier for a table, but it is not necessarily chosen as the primary key.

In a well-designed relational database, each table should have at least one candidate key, and usually several candidate keys. The primary key is chosen from among the candidate keys based on factors such as simplicity, stability, and efficiency.

For example, in a table that stores information about customers, a candidate key might be the combination of the
customer’s email address and phone number. This combination of columns is unigue for each customer and can be used as a unigue identifier for the table.

However, it may not be the best choice for a primary key, as email addresses and phone numbers can change over time, which would require updating all related records. Alternate keys are important for data integrity and normalization in a database. By identifving all the candidate keys for a table, a database designer can ensure that data is stored efficiently and without duplication and that each row in the table is uniquely identifiable. 



#### Introduction To SQL Commands
Structured Query Language as we know is a query language that can be used to perform certain operations on any existing database to to create a new database and then performing the operations.

SQL uses certain commands like Create, Drop, lnsert, etc to carry out the required tasks. These SQL commands are mainly categorized into four categories:

1. DDL - Data Definition Language 
2. DQL - Data Query Language 
3. DML — Data Manipulation Language 
4. DCL - Data Control Language 


### DDL - Data Definition Language
Data Definition Language (DDL) is a subset of SQL (Structured Query Language) that is used to create and modify the structure of database objects such as tables, indexes, and views. It is used to define and manage the schema or logical structure of a database.

DDL includes commands such as CREATE, ALTER, and DROP, which are used to create, modify, and delete
database objects. These commands are used to define the data types, constraints, relationships, and other properties
of the abjects,

Some common DDL commands include:
* CREATE: This command is used to create new database objects such as tables, indexes, and views.
* ALTER: This command is used to modify the structure of existing database objects. For example, vou can use
ALTER to add or remove columns from a table, or to change the data type of a column.
* DROP: This command is used to delete database objects such as tables, indexes, and views.
* TRUNCATE: This command is used to remove all data from a table, while leaving the structure of the table intact.
* COMMENT: This command is used to add comments to database ohjects such as tables, columns, and views. 

DDL commands are typically executed by database administrators, developers, or other users with appropriate permissions to modify the structure of the database. It is important to use DDL commands carefully, as they can have a significant impact on the data stored in the database. 


### DQL - Data Query Language
Data Query Language (DQL) is a subset of SQL (Structured Query Language ) used to retrieve data from a database. It is used to query the contents of tables and views in a database, and to retrieve specific data based on various criteria.

DQL commands include SELECT, which is used to retrieve data from one or more tables or views in a database. The SELECT command can be used with various clauses, such as WHERE, GROUP BY, and ORDER BY, to filter, group, and sort the data retrieved from the database.

Some commuon DQL commands inchede:
+ SELECT: This command is used 1o retrieve data from one or more tables or views in a database. It can be used with various clauses, such as WHERE, GROUP BY, and ORDER BY, to filter, group, and sort the data retrieved from the database.
+ FROM: This clause is used to specify the table or view from which to retrieve data.
+ WHERE: This clayse is used to specify the conditions that the data retrieved must meet. For example, vou can use WHERE to retrieve all rows where a certain column equals a specific value.
* GROUP BY: This clause is used to group the data retrieved hy one or more columns.
* HAVING: This clause is used to specify conditions that the grouped data must meet. For example, you can use HAVING to retrieve all groups where the sum of a certain column is greater than a specific value,
+ ORDER BY: This clause is used to sort the data retrieved by one oF more columns.

DQL commands are used by developers and data analysts to retrieve data from a database and to generate reports and analysis based on the retrieved data. It is important to use DQL commands carefully, as incorrect or inefficient queries can have a significant impact on the performance of the database. 


### DML — Data Manipulation Language
Data Manipulation Language (DML) is a subset of SQL (Structured Query Language ) used to manipulate the data stored in a database. It is used to add, update, and delete data in the database, as well as to retrieve data from the database.

DML commands include INSERT. UPDATE, and DELETE, which are used to add, modify, and remove data from the database. DML commands can also be used in conjunction with DQL commands (such as SELECT) 10 retrieve and modify data in the database.

Some common DML commands include:
*  INSERT: This command is used to add new data to a table in the database, You specify the table name and the values 16 be inserted into the table,
* UPDATE: This command is used to modify existing data in a table in the database, You specify the table name, the columns 10 he updated, and the pew values for those columns.
* DELETE: This command is used to remove data from a table in the database, You specify the table name and the conditions that the dats must meet to be deleted.
* SELECT: This command is used to retrieve data from a table in the database, You specify the columns fo be retrieved and any conditions that the data must meet.

DML commands are used by developers, database administrators, and other users with appropriate permissions to add, modify, and remove data in the database. It is important to use DML commands carefully, as they can have a significant impact on the data stored in the database.

### DCL - Data Control Language

Data Control Language (DCL) is a subset of SQL (Structured Query Language) used ta control access to the data stored in a database. It is used to grant and revoke permissions to access the data, as well as to define and manage roles and users.

DCL commands include GRANT and REVOKE, which are used to grant and revoke permissions to access the data in the database, DCL comminds can alsa be used in conjunction with DQL and DML commands to restrict or grant access to specific tables and data within the database.

Some common DCL commarnds include:
* GRANT: This command is used to grant specific perniissions to vsers or roles in the database. You specify the type of permission (such as SELECT, INSERT, UPDATE, or lJ}iLE‘l‘E,\f the object (such as a table or view), and the user or role to which the permission is granted.
* REVOKE: This command is used to revoke specific permissions from users or roles in the database. You specify the type of permission, the object, and the user or role from which the permission is revoked.

DCL commands are used by database administrators and other users with appropriate permissions to control aceess to the data in the database. It is important to use DCL commands carefully, as granting too many permissions can lead to security vulnerabilities, while revoking too many permissions can lead to restricted access and limited functionality. 

### Data Types in SQL

In MySQL, there are various data types that can be used to define the type of data that can be stored in a column of a table. Some common data types in MySQL include:

Numeric:
* INT (integer)
* DECIMAL (fixed-point)
* FLOAT (floating-point)

String:
* CHAR (fixed-length string)
* VARCHAR (variable-length string)
* TEXT (variable-length string with a maximum length)

Date and Time:
* DATE (date in 'YYYY-MM-DD' format)
* TIME (time in 'HH:MM:SS' format)
* DATETIME (date and time in 'YYYY-MM-DD HH:MM:SS' format)

Boolean:
* BOOL or BOOLEAN (Boolean value)

Others:
* BLOB (binary large object)
* JSON (JSON data)

These are just a few examples of data types available in MySQL. The choice of data type depends on the nature of the data that needs to be stored in the database.





##### Comments in MySQL

In MySQL, you can add comments in SQL queries using -- for single-line comments or /* */ for multi-line comments. Here are examples of both:

Single-line comment:

```SELECT * FROM users; -- This is a single-line comment```

Multi Line Comment:
```
/*
This is a multi-line comment
It can span over multiple lines
*/
SELECT * FROM orders;
```



### SQL Commands
Now let us go through the SQL commands one by one to get a better understanding of them. Make sure to run them in your computer to get a better understanding. Or you can try any online compiler to test out the commands and play around with them. I use [OneCompiler](https://onecompiler.com/mysql) for trying out the commands.


##### Creating Databases
The CREATE DATABASE is used to create a new database. Make sure you have admin privilege before creating any database. 

Use SHOW DATABASE command to show all the databases you have.
Syntax : CREATE DATABASE table_name;
Example: `CREATE DATABASE testdb:` also `show database` to test if the database is created successfully.

##### Deleting Databases (DROP)
The DROP DATABASE is used to drop a new database. Make sure you have admin privilege before dropping(deleting) any database. 

Use SHOW DATABASE command to show all the databases you have.
Syntax : DROP DATABASE table_name;
Example: `DROP DATABASE testdb:` also `show database` to test if the database is deleted successfully.


##### Creating SQL Tables
The CREATE TABLE is used to create a new table. Make sure you have admin privilege before creating table in the database.
Syntax: `CREATE TABLE table_name;`
Example: `CREATE TABLE testTable;`

Creating table employee with create command:
```
-- create
CREATE TABLE EMPLOYEE (
  empId INTEGER PRIMARY KEY,
  name TEXT NOT NULL,
  dept TEXT NOT NULL
);
```

##### Deleting SQL Tables
The DROP TABLE is used to delete a  table. Make sure you have admin privilege before deleting table in the database.
Syntax: `DROP TABLE table_name;`
Example: `DROP TABLE testTable;`

Be careful before deleting any table. Deleting the table will result in complete loss of the data.

##### Truncate SQL Tables
The TRUNCATE TABLE is used to delete data inside a table. Make sure you have admin privilege before truncating table in the database.
Syntax: `TRUNCATE TABLE table_name;`
Example: `TRUNCATE TABLE testTable;`

Be careful before deleting data in any table. 

##### Altering data in SQL Tables

The ALTER keyword is used as part of the Data Definition Language (DDL) to modify existing database objects like tables, views, or databases.

For example, you can use ALTER TABLE to add, modify, or drop columns in a table, change the data type of a column, add constraints, or rename a table.

Here is an example of using ALTER TABLE to add a new column to an existing table: 

```ALTER TABLE users
ADD COLUMN email VARCHAR(255);
```
We can use DROP and MODIFY in place of ADD for dropping and modifiying column name.

### Primary Key
A primary key is a column or set of columns in a table that uniquely identifies each row or record in the table. The primary key is used to enforce data integrity and ensure that each row in the table is unique and identifiable.

Here is an example of creating a table with a primary key:

CREATE TABLE person (
    id INT PRIMARY KEY,
    name VARCHAR(255),
    address VARCHAR(255)
);
In this statement:

* CREATE TABLE person creates a new table named person.
* id INT PRIMARY KEY defines the id column as the primary key of the table.
* name VARCHAR(255) defines the name column as a variable-length string with a maximum length of 255 characters.
* address VARCHAR(255) defines the address column as a variable-length string with a maximum length of 255 characters.

After executing this statement, the person table will be created with the specified columns and primary key

### Foreign Key

In SQL, a foreign key is a constraint that establishes a relationship between two tables. It ensures the referential integrity of the data by enforcing a link between the data in two tables.

Here is an example of using a foreign key in SQL:

Let's say we have two tables: orders and customers. Each order in the orders table belongs to a specific customer in the customers table. We can create a foreign key constraint on the customer_id column in the orders table to reference the id column in the customers table.

Here is how you can create these tables and define the foreign key relationship:
```
CREATE TABLE customers (
    id INT PRIMARY KEY,
    name VARCHAR(255)
);

CREATE TABLE orders (
    id INT PRIMARY KEY,
    order_number VARCHAR(10),
    customer_id INT,
    FOREIGN KEY (customer_id) 
    REFERENCES customers(id)
);
```
In this example:

* The customers table has columns id and name, with id as the primary key.
* The orders table has columns id, order_number, and customer_id, with id as the primary key.
* The customer_id column in the orders table is a foreign key that references the id column in the customers table. This ensures that every customer_id in the orders table must exist in the id column of the customers table.

By using foreign keys, you can maintain the integrity of the data and establish relationships between tables in a database.

### INSERT INTO command

We will use the create table command here first to create the table we want to add data to. And then we will add data using the INSERT INTO command.
```
-- create
CREATE TABLE EMPLOYEE (
  empId INTEGER PRIMARY KEY,
  name TEXT NOT NULL,
  dept TEXT NOT NULL
);

-- insert
INSERT INTO EMPLOYEE (empId, name, dept) VALUES (0001, 'Clark', 'Sales');
INSERT INTO EMPLOYEE (empId, name, dept) VALUES (0002, 'Dave', 'Accounting');
INSERT INTO EMPLOYEE (empId, name, dept) VALUES (0003, 'Ava', 'Sales');
```
If you are adding values for all the columns of the table, you do not need to specify the column names in the SQL query. However, make sure the order of the values is in the same order as the columns in the table.

**Insert Data Only in Specified Columns**
It is also possible to only insert data in specific columns.We need to specify the columns and data associated with it.
```
INSERT INTO EMPLOYEE (empId, name) VALUES (0003, 'Ava');
```
**Insert Multiple Rows**

It is also possible to insert multiple rows in one statement.

To insert multiple rows of data, we use the same INSERT INTO statement, but with multiple values:
```
INSERT INTO EMPLOYEE (empId, name, dept) VALUES
    (0004, 'Lily', 'Marketing'),
    (0005, 'Fin', 'Sales'),
    (0006, 'Ken', 'Accounting'),
    (0007, 'Raj', 'IT');
```

### SELECT Command

The SELECT command is used to retrieve data from one or more tables in the database.

The basic syntax of the SELECT command is as follows:

`SELECT column_name(s) FROM table_name;`

To select all column name from a table, we provide * after the select keyword.

`select * from table_name`

To fetch employee Id and name from the above employee table we will simply query:

`SELECT empId,name from EMPLOYEE;`

To fetch all data from the employee table we will use:

`select * from EMPLOYEES;`


