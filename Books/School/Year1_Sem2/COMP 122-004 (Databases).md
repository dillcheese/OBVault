---
lastSync: Thu Jan 30 2025 19:53:35 GMT-0500 (Eastern Standard Time)
tags:
  - school
created: 2025-01-08T10:41:51-05:00
aliases:
  - sem2
---
# COMP 122-004 (Databases)

3 Assignments (10% each)
1 Group Assignment (15%)
2 Tests (40% total, 20% each)
Weekly Quizzes (15% total)
2 day late policy

- Terms

Schema: A database schema defines how data is organized within a relational database


**Class 1 and 2 (1/9/2025)**
A database is a shared, integrated computer structure that stores a collection of the following:
− End-user data – that is, raw facts of interest to the end user
− Metadata, or data about data, through which the end-user data is integrated and managed
-Metadata describes the data characteristics and the set of relationships that links the data found within the database

A database management system (DBMS) is a collection of programs that manages the database structure and controls access to the data stored in the database.
A DBMS provides the following advantages:
− Improved data sharing
− Improved data security
− Better data integration
− Minimized data inconsistency
− Improved data access
− Improved decision making
− Increased end-user productivity

Types of databases
A single-user database supports one user at a time
− A desktop database is single-user database on a personal computer
• A multiuser database supports multiple users at the same time
− A workgroup database supports a small number of users or a specific department
− An enterprise database supports many users across many departments
• Classification by location
− A centralized database supports data located at a single site
− A distributed database supports data distributed across different sites
− A cloud database is created and maintained using cloud data services

- Classification by data type
− General-purpose databases contain a wide variety of data used in multiple disciplines
− Discipline-specific databases contain data focused on specific subject areas
− An operational database is designed to support a company’s day-to-day operations
− An analytical database stores historical data and business metrics used exclusively for tactical or strategic decision making and is comprised of two main components:
-The data warehouse stores data in a format optimized for decision support
-Online analytical processing (OLAP) is a set of tools for retrieving, processing, and modeling data from the data warehouse

Business intelligence describes a comprehensive approach to capture and process business data to generate information that support decision making
• Databases can be classified to reflect the degree to which the data is structured
− Unstructured data exists in its original (raw) state
− Structured data is the result of formatting unstructured data to facilitate storage and use
− Semistructured data has already been processed to some extent
• Extensible Markup Language (XML) is a language used to represent data elements in textual format
− An XML database supports the storage and management of unstructured XML data

**Class 3 and 4 (1/16/2025)**
- Data Model Basic Building Blocks (1 of 2)
• An entity is a person, place, thing, concept, or event about which data will be collected and stored
• An attribute is a characteristic of an entity
• A relationship describes an association among entities
• The following are three different types of relationships:
− One-to-many (1:M or 1..*) relationship
− Many-to-many (M:N or *..*) relationship
− One-to-one (1:1 or 1..1) relationship

- A constraint is a restriction placed on the data
− Constraints help ensure data integrity
• Constraints are normally expressed in the form of rules:
− An employee’s salary must have values that are between 6,000 and 350,000
− A student’s GPA must be between 0.00 and 4.00
− Each class must have one and only one teacher

- Naming Conventions
• Entity names should be descriptive of the objects in the business environment and use technology that is familiar to the users
• An attribute name should also be descriptive of the data represented
• It is good practice to prefix the name of an attribute with the name or abbreviation of the entity in which it occurs
− For example, in the CUSTOMER entity, customer’s credit limit may be called CUS_CREDIT_LIMIT
• A proper naming convention can help make your model self-documenting

- Hierarchical and Network Models (1 of 2)
• The hierarchical model was developed in the 1960s to manage large amounts of data for complex manufacturing projects
− The hierarchical structure contains levels, or segments
• A segment is the equivalent of a file system’s record type
• A higher layer is perceived as the parent of the segment directly beneath it, which is called the child
• The network model was created to represent complex data relationships more effectively than the hierarchical model, to improve database performance, and to impose a database standard

- Hierarchical and Network Models (2 of 2)
• The following database concepts that emerged with the network model are still used by modern data models:
− The schema is the conceptual organization of the entire database as viewed by the database administrator
− The subschema defines the portion of the database “seen” by the application programs that produce the desired information from the data within the database
− The *data manipulation language (DML)* defines the environment in which data can be managed and is used to work with the data in the database
− A schema *data definition language (DDL)* enables the database administrator to define the schema components

- The Relational Model (1 of 4)
• The relational model’s foundation is a mathematical concept known as a relation
− A relation is a two-dimensional structure composed of intersecting rows and columns
− Each row in a relation is called a tuple and each column represents an attribute
• The relational data model is implemented through a very sophisticated relational database management system (RDBMS)
− The RDBMS performs the same basic functions provided by the hierarchical and network DBMS systems
• The RDBMS manages all of the details, while the users sees a collection of tables in which the data is stored

- The Relational Model (4 of 4)
• Any SQL-based relational database application involves the following three parts:
− The end user interface – the interface allows the end user to interact with the data
− A collection of tables stored in the database – the tables “present” the data to the end user in a way that is easy to understand
− SQL engine – the SQL engine executes all queries or data requests

- The Entity Relationship Model (1 of 3)
• Complex design activities require conceptual simplicity to yield successful results
• Database designers prefer to use a graphical tool in which entities and their relationships are pictured
− The entity relationship (ER) model (ERM) was developed to do just that
• The relational data model and ERM combined to provide the foundation for tightly structured database design
• An entity relationship diagram (ERD) uses graphical representations to model database components

- The Entity Relationship Model (2 of 3)
• The ER model is based on the following components:
− Entity – an entity is represented in the ERD by a rectangle (entity box)
− Attributes – each entity consists of a set of attributes that describes particular characteristics of the entity
− Relationships – relationships describe associations among data
• The following are three ER notations:
− Chen notation
− Crow’s Foot notation
− Class diagram notation (part of the Unified Modeling Language (UML))

- The Object-Oriented Model (1 of 3)
• In the object-oriented data model (OODM), both data and its relationship are contained in a single structure known as an object
− The OODM is the basis for the object-oriented database management system (OODBMS)
− The OODM is said to be a semantic data model because semantic indicates meaning
• The OODM is based on the following components:
− An object is an abstraction of a real-world entity
− Attributes describe the properties of an object

- The Object-Oriented Model (2 of 3)
The OODM is based on the following components (continued):
− A class is a collection of similar objects with shared structure and behavior
 A class’s method represents a real-world action such as finding a selected PERSON’s name, changing a PERSON’s name, or printing a PERSON’s address
− The class hierarchy resembles an upside-down tree where each class has only one parent
− Inheritance is the ability of an object within the class hierarchy to inherit the attributes and methods of the classes above it
− Object-oriented data models are typically depicted using Unified Modeling Language (UML) class diagrams

- Emerging Data Models: Big Data and NoSQL (1 of 3)
• Internet of Things (IoT) is a web of Internet-connected devices exchanging and collecting data
− The IoT has accelerated the rate of data growth so that about 2.5 quintillion bytes of data are created daily
• Big Data refers to a movement to find new and better ways to manage large amounts of web- and sensor-generated data and derive business insight from it
• A basic characteristic of Big Data databases can be described as volume, velocity, and variety, or the 3 Vs

- Emerging Data Models: Big Data and NoSQL (2 of 3)
• Some of the most frequently used Big Data technologies are Hadoop and NoSQL databases:
− Hadoop is a Java-based, open-source, high-speed, fault-tolerant distributed storage and computational framework
− Hadoop Distributed File System (HDFS) is a highly distributed, fault-tolerant file storage system designed to manage large amounts of data at high speeds
− MapReduce is an open-source application programming interface (API) that provides fast data analytics services
− NoSQL is a large-scale distributed database system that stores structured and unstructured data in efficient ways

- Emerging Data Models: Big Data and NoSQL (3 of 3)
• NoSQL databases have the following general characteristics:
− They are not based on the relational model and SQL
− They support highly distributed database architectures
− They provide high scalability, high availability, and fault tolerance
− They support very large amounts of sparse data
− They are geared toward performance rather than transaction consistency

*Logical independence* exists when you can change the internal model without affecting the conceptual model.

**Class 5 and 6 (1/23/2025)**
• Define database terms
• Identify the purpose of a database management system (DBMS)
• Explain database design using entity-relationship models and normalization
• Explain the purpose of a Structured Query Language (SQL)
• Understand how this textbook’s topics are sequenced and how the two sample databases are used

Database – logical structure to store data
Database management system (DBMS) – software used to create and interact with the database

- Systems Development Life Cycle (SDLC)
• Systems investigation – understanding the problem
• Systems analysis – understanding the solution
• Systems design – creating the logical and physical components
• Systems implementation – placing completed system into operation
• Systems maintenance and review – evaluating the implemented system

- Entity-Relationship Model (E-R Model)
• Used to depict the relationship that exists among entities
• The following relationships can be included in an E-R model:
– One-to-one (Each occurrence of data in one entity is represented by only one occurrence of data in the other entity)
– One-to-many (Each occurrence of data in one entity can be represented by many occurrences of the data in the other entity)(*Example:* A class has only one instructor, but each instructor can teach many classes)
– Many-to-many (Data can have multiple occurrences in both entities)(*Example:* A student can take many classes, and each class is composed of many students)

- Database Normalization
• Determines required tables and columns for each table
• Multistep process
• Used to reduce or control data redundancy
Data redundancy – refers to having the same data in different places within a database
Data anomalies – refers to data inconsistencies (old phone number, address etc.)

- First-Normal Form (1NF)
• Primary key is identified
• Repeating groups are eliminated 
• For example in a DB with books the ISBN and Author columns together can create a composite primary key
*Composite Primary Key*
• More than one column is required to uniquely identify a row
• Can lead to partial dependency – a column is only dependent on a portion of the primary key

- Second-Normal Form (2NF)
• Partial dependency must be eliminated
– Break the composite primary key into two parts, each part representing a separate table

- Third-Normal Form (3NF)
•  Transitive Dependencies (Publisher contact name) have been removed

- Summary of Normalization Steps
• 1NF: eliminate repeating groups, identify the primary key
• 2NF: table is in 1NF, and partial dependencies are eliminated
• 3NF: table is in 2NF, and transitive dependencies are eliminated

- Relating Tables within the Database
• Once tables are normalized, make certain tables are linked
• Tables are linked through a common field
• A common field is usually a primary key in one table and a foreign key in the other table

- Lookup Table
• Common reference for descriptive data tablesr eferenced in a foreign key

- Summary
• A DBMS is used to create and maintain a database
• A database is composed of a group of interrelated tables
• A file is a group of related records; a file is also called a table in the physical database
• A record is a group of related fields regarding one specific entity; a record is also called a row
• A record is considered unnormalized if it contains repeating groups

• A record is in first-normal form (1NF) if no repeating groups exist and it has a primary key
• Second-normal form (2NF) is achieved if the record is in 1NF and has no partial dependencies
• After a record is in 2NF and all transitive dependencies have been removed, then it is in third-normal form (3NF), which is generally sufficient for most databases
• A primary key is used to uniquely identify each record

• A common field is used to join data contained in different tables
• A foreign key is a common field that exists between two tables but is also a primary key in one of the tables
• A lookup table is a common term for a table referenced in a foreign key
• A Structured Query Language (SQL) is a data sublanguage that navigates the data stored within a database’s tables

- Lab Stuff

**Class 7 and 8 (1/30/2025)**
- Table Creation and Management

Table and column names:
– Can contain a maximum 30 characters – no blank spaces
– Must begin with a letter
– Can contain numbers, underscore (______), and number sign (#)
– Must be unique
– No reserved words are allowed

Column definition list must be enclosed in parentheses
• Datatype must be specified for each column
• Maximum of 1,000 columns

ALTER TABLE…DROP COLUMN Command
• Can only reference one column per execution
• Deletion is permanent
• Cannot delete last remaining column in a table

ALTER TABLE…SET UNUSED Command
• Once marked for deletion, a column cannot be restored
• Storage space is freed at a later time

ALTER TABLE…DROP UNUSED Command
• Frees up storage space from columns previously marked as unused

Truncating a Table
• TRUNCATE TABLE command – rows are deleted
• Structure of table remains

Deleting a Table
• DROP TABLE command – table structure and contents are deleted
