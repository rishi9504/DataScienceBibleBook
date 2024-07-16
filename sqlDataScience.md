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

### What is a Query?

In the context of databases, a query is a request for information from a database. It is a way of asking the database it reteieve speeific data based on certain conditions or criteria.

Queries can take different forms depending on the type of database and the programming language used to interact with it. In general, a query involves specifying what data to retrieve, which tables or collections to search, and what conditions or filters to apply.

For example, a query in SQL (Structured Query Language) might look like this:

`SELECT name, age, city FROM customers WHERE age > 30;`

This query is asking the database to retrieve the name, age, and city of all customers where the age is greater than 30. The database would then return a result set that matches the criteria specified in the query.

Queries can be used for a variery of purposes; such as gencrating reports, performing analysis, and updating or deleting data. Well-crafted queries can help improve the performance and efficiency of database operations, as they allow you to retrieve only the data you need, and avoid unnecessary processing and resource usage.

What is SQL?

SQL is a standard language for storing, manipulating, and retrieving data in databases. SQL stands for Struetured Query Language. SQL lets you access and manipulates databases. SQL became a standard of the American National Standards Institute (ANSI) in 1986 and of the International Organfzation for Standardization {IS0} in 1987, 

