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


### WHERE Command


The WHERE clause is used in SQL to filter records based on a specified condition. 

The WHERE clause is used to specify the conditions that the data must meet to be included in the result set.

In the SELECT statement, the WHERE clause is used to apply the filter to the data. Only the records that meet the specified condition are returned.

The WHERE clause is typically used with the SELECT, UPDATE, DELETE, and INSERT statements.
```
SELECT column_name(s) FROM table_name WHERE condition;
```

Here is an example:

`SELECT empId,name from EMPLOYEE where dept='Sales';`

This will fetch the employees working in the sales department.

### ORDER BY Command


The ORDER BY clause is used to sort the data retrieved by one or more columns. The columns are listed in the ORDER BY clause, and the optional ASC or DESC keyword is used to specify the sorting order (ascending or descending).

Here is an example:

`SELECT empId,name from EMPLOYEE ORDER BY empId ASC;`

This will fetch the employees sorted by employee Id in ascending order.

To sort in descending order:

`SELECT empId,name from EMPLOYEE ORDER BY empId DESC;`

This will fetch the employees sorted by employee Id in descending order.

You can also sort by multiple columns:

`SELECT empId,name,dept from EMPLOYEE ORDER BY dept ASC, empId DESC;`

This will fetch the employees sorted by department in ascending order and then by employee Id in descending order.

### UPDATE Statement in SQL

The UPDATE statement is used to modify the existing records in a table.

The UPDATE statement is used to update existing records in a table. It can be used to update one or more columns in a table.

The basic syntax of the UPDATE statement is as follows:

`UPDATE table_name SET column1=value1, column2=value2 WHERE condition;`

The UPDATE statement is typically used with the WHERE clause to specify which records to update. The WHERE clause can be used to specify the conditions that the records must meet to be updated.

For example:

`UPDATE EMPLOYEE SET salary=100000 WHERE dept='Sales';`

This will update the salary of all employees in the sales department to $100,000.

**Note:**

Remember it will update existing records only. Add salary in our emmployee table to use the above query.

`alter table EMPLOYEE add salary varchar(255);`

### DELETE Statement

The DELETE statement is used to delete records from a table.

The basic syntax of the DELETE statement is as follows:

`DELETE FROM table_name WHERE condition;`

The DELETE statement is typically used with the WHERE clause to specify which records to delete. The WHERE clause can be used to specify the conditions that the records must meet to be deleted.

For example:

`DELETE FROM EMPLOYEE WHERE empId='123';`

This will delete the employee with empId '123' from the EMPLOYEE table.

**Note:**

This will delete the records permanently. To delete records temporarily, you can use the TRUNCATE TABLE statement.

### LIMIT Statement

The LIMIT clause is used to limit the number of rows returned by a query.

The basic syntax of the LIMIT clause is as follows:
```
SELECT column_name(s)
FROM table_name
WHERE condition
LIMIT number;
```

For example,

`SELECT * FROM EMPLOYEE LIMIT 3;`

What if we want to select records 4-6 inclusively? We can use OFFSET command with limit to achieve this.

`SELECT * FROM EMPLOYEE LIMIT 3 OFFSET 3;`

### MIN Command

The MIN statement in SQL is used to find the minimum value in a set of values.

The basic syntax of the MIN statement is as follows:

`SELECT MIN(column_name) FROM table_name;`

For example:

`SELECT MIN(salary) FROM EMPLOYEE;`

This will return the minimum salary from the EMPLOYEE table.

### MAX Command

The MAX statement in SQL is used to find the maximum value in a set of values.

The basic syntax of the MAX statement is as follows:

`SELECT MAX(column_name) FROM table_name;`

For example:

`SELECT MAX(salary) FROM EMPLOYEE;`

This will return the maximum salary from the EMPLOYEE table.

### COUNT Statement

The COUNT statement in SQL is used to count the number of rows in a table that meet a specified condition. It is often used in combination with the WHERE clause to filter the results.

The basic syntax of the COUNT statement is as follows:

`SELECT COUNT(*) FROM table_name WHERE condition;`

For example:

`SELECT COUNT(*) FROM EMPLOYEE WHERE dept='Sales';`

This will return the number of employees in the sales department.

### AVG Statement

The AVG statement in SQL is used to calculate the average value in a set of values.

The basic syntax of the AVG statement is as follows:

`SELECT AVG(column_name) FROM table_name;`

For example:

`SELECT AVG(salary) FROM EMPLOYEE;`

This will return the average salary from the EMPLOYEE table.


### SUM Statement


The SUM statement in SQL is used to calculate the total sum of a set of values.

The basic syntax of the SUM statement is as follows:

`SELECT SUM(column_name) FROM table_name;`

For example:

`SELECT SUM(salary) FROM EMPLOYEE;`

This will return the total salary from the EMPLOYEE table.

### LIKE Operator

The LIKE operator in SQL is used to search for a specified pattern in a column.

The basic syntax of the LIKE operator is as follows:
```
SELECT column_name(s) FROM table_name WHERE column_name LIKE pattern;
```

The 'pattern' can include wildcards like '%' to represent zero or more characters, or '_' to represent a single character.

For example:
```
SELECT * FROM employees WHERE last_name LIKE 'Sm%';
```
This query will return all employees whose last names start with 'Sm'.

### IN Operator

The IN operator in SQL is used to select records where the value of one column is equal to any value in a list of values.

The basic syntax of the IN operator is as follows:

`SELECT column_name(s) FROM table_name WHERE column_name IN (value1, value2, ...);`

For example:

`SELECT * FROM employees WHERE department IN ('Sales', 'Finance', 'HR');`

This query will return all employees who work in the Sales, Finance, or HR department.

The IN operator can be very useful when you want to return records that match any value in a list of values.

### BETWEEN Operator

The BETWEEN operator in SQL is used to select records where the value of one column is within a range of values.

The basic syntax of the BETWEEN operator is as follows:

`SELECT column_name(s) FROM table_name WHERE column_name BETWEEN value1 AND value2;`

The BETWEEN operator can be used to select records where the value of a column is within a specific range of values. The range is specified by the two values that are placed between the BETWEEN operator.

For example:

`SELECT * FROM employees WHERE salary BETWEEN 30000 AND 60000;`

This query will return all employees whose salary is between $30,000 and $60,000.

### ALIASES in MySQL

An alias in SQL is a temporary name given to a table or column in a SQL statement. It allows you to refer to the table or column using a shorter or more meaningful name.

The basic syntax for creating an alias is as follows:

`SELECT column_name AS alias_name FROM table_name;`

For example:

`SELECT employee_id AS emp_id FROM employees;`

This query will return the employee_id column from the employees table, but it will be displayed as emp_id in the result set.

You can also use the AS keyword to create an alias for a column in a SELECT statement.

Note that aliases are only valid within the scope of a single SQL statement. They cannot be used in other SQL statements or subqueries.


### GROUP BY Statement in SQL

The GROUP BY statement in SQL is used to group rows that have the same values in one or more columns. The GROUP BY statement is often used with aggregate functions to group and summarize data.

The basic syntax of the GROUP BY statement is as follows:

`SELECT column_name, aggregate_function(column_name) FROM table_name GROUP BY column_name;`

For example:

`SELECT department, AVG(salary) FROM employees GROUP BY department;`

This query will return the average salary for each department in the employees table.

The GROUP BY statement groups the rows by the specified column(s). The aggregate function(s) (such as SUM, AVG, COUNT, etc.) are then applied to each group to calculate the desired summary information.

Note that when using the GROUP BY statement, all non-aggregated columns in the SELECT statement must either be included in the GROUP BY clause or be part of an aggregate function.


### HAVING clause in SQL

The HAVING clause is used in conjunction with the GROUP BY clause to specify conditions that the grouped data must meet. It is often used to filter the groups that are returned by the GROUP BY clause.

The basic syntax of the HAVING clause is as follows:

`SELECT column_name(s) FROM table_name GROUP BY column_name(s) HAVING condition;`

For example:

`SELECT department, AVG(salary) FROM employees GROUP BY department HAVING AVG(salary) > 50000;`

This query will return the average salary for each department in the employees table, but only the departments with an average salary greater than $50,000.

Note that the HAVING clause is used to specify conditions on the groups returned by the GROUP BY clause, while the WHERE clause is used to specify conditions on the individual rows in the table before they are grouped.

### EXISTS operator in SQL

The EXISTS operator is used in SQL to check if a subquery returns at least one row. It is used in the WHERE clause of a query and returns a Boolean value.

The basic syntax of the EXISTS operator is as follows:

`SELECT * FROM table_name WHERE EXISTS (subquery);`

For example:

`SELECT * FROM customers WHERE EXISTS (SELECT id FROM orders WHERE customer_id = customers.id);`

This query will return all the rows in the customers table where there is at least one corresponding row in the orders table for that customer.

Note that the EXISTS operator does not return the actual rows from the subquery, it only checks if the subquery returns any rows. 

The opposite of the EXISTS operator is NOT EXISTS, which is used to check if a subquery does not return any rows. The syntax is the same, but with the NOT keyword added before EXISTS. 

For example:

`SELECT * FROM customers WHERE NOT EXISTS (SELECT id FROM orders WHERE customer_id = customers.id);`

This query will return all the rows in the customers table where there are no corresponding rows in the orders table for that customer.

### ANY operator in SQL

The ANY operator is used in SQL to return a Boolean value if any of the subquery values meet the condition.

The basic syntax of the ANY operator is as follows:

`SELECT * FROM table_name WHERE condition ANY (subquery);`

For example:

`SELECT * FROM customers WHERE salary > ANY (SELECT salary FROM employees);`

This query will return all the rows in the customers table where the salary is greater than any of the salaries in the employees table.

Note that the ANY operator is similar to the EXISTS operator, but it returns a Boolean value if any of the subquery values meet the condition, while the EXISTS operator returns a Boolean value if any rows are returned by the subquery.

### ALL operator in SQL

The ALL operator is used in SQL to return a Boolean value if all of the subquery values meet the condition.

The basic syntax of the ALL operator is as follows:

`SELECT * FROM table_name WHERE condition ALL (subquery);`

For example:

`SELECT * FROM customers WHERE salary > ALL (SELECT salary FROM employees);`

This query will return all the rows in the customers table where the salary is greater than all of the salaries in the employees table.

Note that the ALL operator is similar to the ANY operator, but it returns a Boolean value if all of the subquery values meet the condition, while the ANY operator returns a Boolean value if any rows are returned by the subquery.


### CASE Statement in SQL

The CASE statement is used to conditionally evaluate an expression and return a result based on the conditions.

The basic syntax of the CASE statement is as follows:
```
CASE
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    WHEN condition3 THEN result3
END    
```

For example:
```
-- 
```

### IS NULL & IS NOT NULL Operator
A field with a NULL value is a field with no value. If a fiekd in a table is optional, it is possible to insert a new record or update a record without adding a value to this field. Then, the field will be saved with a NULL value,

Note: A NULL value is different from a zero value or a field that contains spaces. A field with a NULL value is one that has been left blank during recond creation.

This not possible to test for NULL values with comapirison operators, such as =, <, or >, We will have to use the IS NULL and IS NOT NULL operators instead. :

IS NULL Syntax:
```
SELECT column_pames.
FROM table_name
WHERE column_name IS NULL;
```
IS NOT NULL Syntax
```
SELECT column_pames
FROM table_name
WHERE column_name IS NOT NULL;
```
Example:
```
SELECT CustomerName, ContactName, Address
FROM Customers
WHERE Address IS NULL; 
```

### Introduction to SQL Joins

A JOIN clause is used 1o combine rows from two or mere tables, based on a related column between them. There are 4 different types of SQL joins:
+ SQL INNER JOIN (sometimes called simple join)
* SQLLEFT OUTER JOIN (sometimes called LEFT JOINY
* SQL RIGHT OUTER FOIN (sometimes called RIGHT JOIN)
+ SQL FULL QUTER JOIN (sometimes called FULL JOIN) 

### Joining Across Multiple Databases
SQL Server allows you to join tables from different databases as long as those databases are on the same server. The join syntax is the same; the only difference is that you must fully qualify table names.

Let’s suppose you have two databases on the same server - Db and Db2. Db1 has a table called Clients with a column Clientld and Db2 has a table called Messages with a colurn Clientld (lets leave aside why those tables are in differcnt databases ).

Now, to perform a join on the above-mentioned tables you will be using this query:

```
select * from Db1.dbo.Clients c join Db2.dbo Messages on c.Clientld = m.Clientld;
```
### Joining Table to Itself


Also known as self join, we join table from itself.
Syntax
```
SELECT column_name(s)
FROM tablel T1, tablel T2
WHERE condition; 
```
T1and T2 are different table aliases for the same table.
Example
```
SELECT A.CustomerName AS CustomerNamel,
B.CustomerName AS CustomerName2, A.City
FROM Customers A, Customers B
WHERE A.CustomerlD = B.CustomerlD
AND A.City = B.City
ORDER BY A.City;
```
### Joining Across Multiple SQL Tables
An SQL query can JOIN multiple tables. For each new table an extra JOIN condition is added. Multi-Table JOINs
work with SELECT, UPDATE, and DELETE queries.
Example:
```
SELECT Orders.OrderlD, Customers.CustomerName, Shippers.ShipperName
FROM (Orders INNER JOIN Customers ON Orders.CustomerID = Customers. CustomerID)
INNER JOIN Shippers ON Orders.ShipperID = Shippers.ShipperID); 
```

Left and Right Joins
The LEFT JOIN keyword returns all records from the left table (table1), and the matching records from the right table (table2), The result is O records from the right side, if there is no match.

Syntax
```
SELECT column_name{s)
FROM tablel
LEFT JOIN table2
ON tablel.column_name = table2 column_name:
```
Note: In some databases LEFT JOIN is called LEFT OUTER JOIN.
Example:
```
SELECT Customers,CustomerName, Orders.OrderID
FROM Customers
LEFT JOIN Orders ON Customers.CustomerlD = Ordérs. CustomerID
ORDER BY Customers.CustomerNames
```
The RIGHT JOIN keyword returns all records from the right table (table2), and the matching records from the left table (table1). The result is 0 records from the left side, if there is no match.

Syntax
```
SELECT column_name{s)
FROM table1
RIGHT JOIN table2
ON tablel.column_name = table2.column_name;
```
Note: Tn some databases RIGHT JOIN is called RIGHT OUTER JOIN.

Example
```
SELECT Orders.OrderlD, Employees LastName, Employees FirstName 
FROM Orders
RIGHT JOIN Employees ON Orders EmployeelD = Employees Employeel D
ORDER BY Orders.OrderlD; 
```


### Window Functions

Window functions perform a calculation across a set of rows that are related to the current row. They are often used to calculate aggregated values based on a range of rows.

```
function(expression|column) OVER(
	[ PARTITION BY expr_list optional]
    [ ORDER BY order_list optional]
)
```
A window function is a function that operates on a set of rows that are related to the current row. The OVER keyword is used to specify the window over which the function operates.

The PARTITION BY clause is used to partition the rows into groups. The ORDER BY clause is used to order the rows within each group.

The expression|column is the function or column that is being applied to the window.

Here's an example of how this code might be used:
```
SELECT column1, sum(column2) OVER(PARTITION BY column1 ORDER BY column3) AS running_sum
FROM table_name

```

This query calculates the running sum of column2 for each value of column1, ordered by column3.

Let's understand it by creating a new table,inserting some data and then apply window functions to see how we can use them.

```
CREATE TABLE student_score (
  student_id SERIAL PRIMARY KEY,
  student_name VARCHAR(30),
  dep_name VARCHAR(40),
  score INT
);

INSERT INTO student_score VALUES (1, 'Ibrahim', 'Computer Science', 80);
INSERT INTO student_score VALUES (2, 'Taiwo', 'Microbiology', 76);
INSERT INTO student_score VALUES (3, 'Nurain', 'Biochemistry', 80);
INSERT INTO student_score VALUES (4, 'Joel', 'Computer Science', 90);
INSERT INTO student_score VALUES (5, 'Mustapha', 'Industrial Chemistry', 78);
INSERT INTO student_score VALUES (6, 'Muritadoh', 'Biochemistry', 85);
INSERT INTO student_score VALUES (7, 'Yusuf', 'Biochemistry', 70);
INSERT INTO student_score VALUES (8, 'Habeebah', 'Microbiology', 80);
INSERT INTO student_score VALUES (9, 'Tomiwa', 'Microbiology', 65);
INSERT INTO student_score VALUES (10, 'Gbadebo', 'Computer Science', 80);
INSERT INTO student_score VALUES (11, 'Tolu', 'Computer Science', 67);
```

Run the above code to create a new table first.

Let's say if we want to compare the minimum score and maximum score from all the records in the table we created earlier. You can do that using a window function as shown below.  

Remember that not specifying a partition clause in the OVER clause will cause all the windows to span through the entire dataset.
```
SELECT 
	*,
	MAX(score) OVER() AS maximum_score,
	MIN(score) OVER() AS minimum_score
	
FROM student_score;

```

Also, note that the above query can be also achieved using subqueries like this:
```
SELECT *,
	(SELECT MAX(score) FROM student_score) AS maximum_score,
	(SELECT MIN(score) FROM student_score) AS minimum_score
FROM student_score;
```

**Run both the queries and check the result.**

### How to Use the ROW_NUMBER Function
You use ROW_NUMBER() to assign serial numbers to records in a window. Say we want to assign serial numbers to the records in a partition. For example, we want to add row numbers to the dataset based on their names in alphabetical order. You can do that using the following code:
```
SELECT
	*,
	ROW_NUMBER() OVER(ORDER BY student_name) AS name_serial_number
FROM student_score;
```

### How to Use the RANK Function

RANK(), as the name implies, lets you rank observations in a window but with gaps. Let's see what this means:
```
SELECT
	*,
	RANK()OVER(PARTITION BY dep_name ORDER BY score DESC)	
FROM student_score;
```

As you can see in the above code, the result set was partitioned into different windows based on the department column. Then we used the ORDER BY clause to sort the student records based on their score in descending order in each partition. After that, we applied the RANK function.

### How to Use the DENSE_RANK Function
DENSE_RANK is similar to RANK except that it ranks observations in a window without gaps.
```
SELECT
	*,
	DENSE_RANK()OVER(PARTITION BY dep_name ORDER BY score DESC)	
FROM student_score;
```

### How to Use the LAG Function
LAG is used to return the offset row before the current row within a window. By default it returns the previous row before the current row.

You typically use LAG when you want to compare the value of a previous row with the current row. It's commonly applied in time-series analysis. For example:
```
SELECT
	*,
	LAG(score) OVER(PARTITION BY dep_name ORDER BY score)	
FROM student_score;
```

### How to Use the Frame Clause in ORDER BY
Now you've learned some common window functions you might work with on a daily basis. So let's move on to learning another key concept related to the ORDER BY clause called the frame clause.

A frame clause, as the name implies, provides the frame (that is, the set of rows in a window) on which the function is to be applied. You use it to provide the offset of rows to be included or calculated with the current row (that is, the rows before or after the current row – the SQL engine process row one after the other).

Now before we look into how to specify a frame clause, let's look at some of the frame clause's assumptions:

1. First, a frame clause does not apply to ranking functions. The ranking function only ranks the observation in the window based on the ORDER BY clause.
2. When using an aggregate window function, you may not include the ORDER BY clause. But when you use the ORDER BY clause, it's a best practice to specify the frame clause for accurate results. What this means is say you want to use an aggregate window function and you want to also order the observations in that window by a column. It's best practice is to specify a frame clause so that you will get an accurate result. But if you are not ordering the observations in the window when using an aggregate function, you don't need to specify a frame clause.


You can specify a frame clause using two things – ROWS and RANGE. But in this part you will learn how to use the ROWS keyword since it is commonly used to specify a frame clause. 

The ROWS clause defines the frame in terms of the physical offset rows from the current rows. That is, it is used to specify the rows that will be used in conjunction with the current row for calculation.  

For example the following frame clause ROWS BETWEEN 1 PRECEDING AND 1 FOLLOWING defines a frame that includes the current row, 1 row preceding it and 1 row following it.

Let's look at the keywords that you can use in conjunction with the ROWS clause:

1. N PRECEDING is a keyword you use to specify the N rows that will be included in the calculation along with the current row. For example 3 PRECEDING means 3 rows preceding the current row.
2. N FOLLOWING works like N PRECEDING excepts that it works in an opposite manner. N FOLLOWING specifies the numbers of row after the current row.
3. UNBOUNDED PRECEDING means all rows before the current row.
4.  UNBOUNDED FOLLOWING means all rows after the current row.
5. CURRENT ROW is used to specify the current row.

For example, let's look at the below frame clause:

ROWS BETWEEN 2 PRECEDING AND CURRENT ROW will use less than or equal to 2 rows before the current row, along with the current row for the calculation.

**Frame clause example**

Let's look at an example. Say for instance you want to get the cumulative sum of all the student scores. You can do that by using a frame clause.

So first, to be able to do this, you need to first know the types of keywords you will specify in the frame clause.

Since you want to sum up all rows before the current row and the current row itself, you can use the UNBOUNDED PRECEDING keyword. Remember that this gets all rows before the current row and also uses the current row itself.

So the code to achieve that task is shown below:
```
SELECT
	*,
	SUM(score)OVER(ORDER BY student_id ROWS
     BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW)
     AS cummulative_sum
FROM student_score
```

Let's break down the window function code:
```
SUM(score)OVER(ORDER BY student_id ROWS 
BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW)
 AS cummulative_sum
```
Firstly in the OVER() clause, we sort the entire window – which is the whole dataset – using the student id.

Then we specify the frame clause which is ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW. This is all rows before the current row and the current row will be used for calculation.

### Introduction to Triggers
A trigger is a special type of stored procedure that automatically runs when an event occurs in the database server.

DML trigggers runs when a user tries to modify data through a data manipulation language (DML) eveat. DML events like INSERT, UPDATE, or DELETE statements on a table or view.

DML triggers are frequently used for enforcing business rules and data integrity. SQL Server provides declarative referential integrity (DRI) through the ALTER TABLE and 'CREATE TABLE statements.However, DRI doesn't provide cross-database referential integrity. Referential integrity refers to the rules about the relationships between the primary and foreign keys of tables. To enforce referential integrity, use the PRIMARY KEY and FOREIGN KEY constraints in ALTER TABLE and CREATE TABLE. 

**BEFORE Insert Triggers**

MySQL BEFORE INSERT triggers are automatically fieed before an losert event occurs on the table. The following illustrates the basic syatax of creating a MySQL BEFORE INSERT trigger:
```
CREATE TRIGGER trigger_name
BEFORE INSERT
ON table_name FOR EACH ROW
trigger_body;
```

In this syntax:
First, specify the name of the trigger that you want to create in the CREATE TRIGGER clause. Second, use the BEFORE INSERT clause to specify the time to imvoke the trigger. Third, specify the name of the table that the trigger is associated with after the ON keyword. Finally, specify the trigger body which continuing one or more SQL statements that execute when the trigger is invoked.

Note that ina BEFORE INSERT trigger, you can access and change the NEW values. However, you cannot access
the OLD values because OLD values obviously do not exist.

**AFTER Insert Trigger**
MySQL AFTER INSERT triggers are automatically invoked after an insert event oceurs on the table. The following shows the basic syntax of creating a MySQL AFTER INSERT trigger:
```
CREATE TRIGGER trigger_name
AFTER INSERT
ON table_name FOR EACH ROW
trigger_body
```

In this syntax:
* First, specify the name of the trigger that you want to create after the CREATE TRIGGER keywords.
* Second, use the AFTER INSERT clause to specify the time to invoke the trigger.
* Third, specify the name of the table on which you want to create the trigger after the ON keyword.
* Finally. specify the trigger body which consists of one or more statements that execute when the trigger is
inveked. 

**DROP Triggers**

The DROP TRIGGER statement deletes a trigger from the database, Here is the basic svntax of the DROP TRIGGER statement:

DROP TRIGGER | IF EXISTS | | schema_name. Trigger_name;

In this syntax:
* First, specify the name of the frigger that vou want to drop after the DROP TRIGGER kevwords,
+ Second, specify the name of the schema to which the trigger belongs. §f you skip the schema name, the statement will drop the trigger in the current database.
+ Third, use the IF EXISTS option o conditionally drops the trigger if the trigger exists, The IF EXISTS clause is optional.

If you drop a trigger that does not exist without using the 1F EXISTS clause, MySQL issues an error. However. if you use the IF EXISTS clause, MySQL issues a NOTE instead,

The DROP TRIGGER requires the TRIGGER privilege for the table associated with the trigger.

Note that if you drop a table, MySQL will automatically drop all triggers associated with the table.

### SQL Stored Procedure
A stored procedure is a set of Structured Query Language (SQL) statements with an assigned name, which is stored in a relational database managgement system (RDBMS) as a group, so it can be reused and shared by multiple programs.

Stored procedures can access or modify data in a database, but it is not tied to a specific database or object, which offers a number of advantages.
Stored procedures provide some crucial benefits, which are: 
* Reusable: As mentioned, multiple users and applications can easily use and reuse stored procedures by merely calling it.
* Easy to modify: You can quickly change the statenents in a stored procedure as and when you want to, with the help of the ALTER TABLE command.
* Security: Stored procedures allow you to enhance the security of an application or a datasbase by restricting the users from direct access to the table.
* Low neswork traffic: The server-only passes the procedure name instead of the whole query, reducing network traffic.
* Inereases performance: Upon the first use, a plan for the stored procedure is created and stored in the buffer pool for quick execution for the next time.

### Create a Stored Procedure
Creating a stored procedure in SQL is ax easy as it sounds. We use CREATE PROCEDURE to create a stored procedure.

Syntax
```
CREATE PROCEDURE procedure_name
AS
sql_statement
GO: 
```