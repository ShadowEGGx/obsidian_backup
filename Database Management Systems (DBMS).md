# **MAIN SYLLABUS**
- Basic Introduction (2 tier, 3 tier, 3 schema/level of abstraction, Data Models)
- ER Model (Entity, Attribute, Relation)
- Basics of keys
- Normalisation (1NF, 2NF, 3NF, BCNF)
- Transaction Control and Concurrency 
- SQL (DDL, DML, DCL)
- Indexing


## What is Data?
**Data** is a collection of facts, statistics or information that can be recorded, processed and used for analysis. It serves as the raw input for generating useful insights or making decisions.

### Differences between Data and Information

| **Data**                                                                | **Information**                                            |
| :---------------------------------------------------------------------- | :--------------------------------------------------------- |
| Raw, unprocessed, unorganised facts or figures.                         | Processed, organised and interpreted data.                 |
| It is collected for potential usage analysis. Has no meaning by itself. | Provides insight, knowledge and context and has a meaning. |
| Example: `["John", "25", "1001"]`                                       | Example: `["Student ID 1001: John is 25 years old."]`      |
### What is a **Database System**?
A **Database System** is comprised of two things:
- Database
- Database Management System

### What is a **Database**?
A **Database** is referred to as a collection of data, that is stored in a computer system and is relevant to the enterprise.

What water is to a container, data is to a database.

A database has to be structured/organised to actually hold relevant meaning. 

A structured database is done through RDBMS (Relational DBMS) and is represented in a tabular form. E.g. Enterprise/Company/Institution Data.
An unstructured database is opposite of a structured Data. E.g. Webpages.

### What is a **Database Management System**?
A **Database Management System (DBMS)** is a software that manages a collection of interrelated data and provides tools to store, retrieve and control access to the database.

For example, MySQL, PostgreSQL, OracleDB are examples of DBMS programs. 
SQL stands for **Structured Query Language**.

#### Goals of using DBMS:
- **Efficient Data Storage and Retrieval**:  
    The primary goal of a DBMS is to enable convenient and efficient storage and retrieval of information.
    - **Example**: While shopping for a shirt on Amazon, users can sort and filter items by colour, size, type, or price, allowing for a personalised shopping experience.

- **Ensuring Data Security**:  
    A good DBMS ensures the security and integrity of stored information, restricting access based on user roles and permissions.
    - **Example**: On Amazon, customers can view and select shirts based on their preferences but cannot modify sensitive information like prices or stock levels. Only authorised users, such as administrators or sellers, can make such changes, ensuring the security of the DBMS.

## File Systems
A **file system** is a method of organizing, storing, and retrieving data on storage devices like hard drives, SSDs, or USB drives. It manages how data is structured into files and directories, providing a way to read, write, and manage the data efficiently. Examples include NTFS, FAT32, and ext4.

#### Key features of a File System
- **Storage Management**
- **Access Control**
- **Data Retrieval**
- **File Operations**

### File Systems vs DBMS

| Aspect         | File System                                                                                             | DBMS                                                           |
| -------------- | ------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------- |
| Purpose        | To manage files and folders in a storage device.                                                        | Manages structured data in a database.                         |
| Querying       | Requires manual data searching through the files                                                        | Provides fast searching with powerful query languages like SQL |
| Data integrity | No built-in mechanisms to ensure data integrity.                                                        | Ensures data integrity through constraints (e.g. primary keys) |
| Concurrency    | Limited support for concurrent access, i.e. a few number of users can access the file system at a time. | Handles multiple users accessing the database continuously.    |
| Security       | Basic file permissions (read, write, execute)                                                           | Advanced security features like user roles and encryption.     |
| Scalability    | Limited scalability for a large amounts of data.                                                        | Highly scalable to handle large and complex datasets.          |
**Meaning of Scalability:** The ability of a database to handle increasing amounts of data, numbers of users, and types of requests without sacrificing performance or availability.

## 2 Tier Architecture
![[Pasted image 20250107095716.png]]

**Client** is a machine that connects to the Database server.
There is an API in client machine through JDBC and ODBC which helps to create connections to the database.

**2 Tier Architecture** is a client-server location model that is divided into two layers:
- *Client Tier*: The UI that interacts with the user.
- *Server Tier*: The database that stores and processes data.

### Components of a Two Tier Architecture
- **Client Tier (Presentation Layer)**:
    - Handles the user interface.
    - Sends requests to the server for data or services.
    - Example: A desktop application like a library management system.
- **Server Tier (Database Layer)**:
    - Manages data storage and retrieval.
    - Processes client requests and sends the results back.
    - Example: A database like MySQL or PostgreSQL.

### Working of a Two Tier Architecture
- The **client** sends a request (e.g., "Fetch all books from the library database").
- The **server** processes the request, retrieves the data, and sends the result back to the client.
- The client displays the data to the user.

### Advantages of 2-Tier Architecture
1. **Simplicity**: Easy to design and implement.
2. **Performance**: Faster communication as there’s a direct connection between client and server.
3. **Cost-Effective**: Suitable for small-scale applications due to fewer components.

### Disadvantages of a Two Tier Architecture System
- **Limited Scalability**: Not ideal for large-scale systems with many users.
- **High Coupling**: Changes in the database or business logic can directly affect the client.
- **Security Issues**: Direct client-server interaction may expose the database to risks.

### Example of 2-Tier Architecture
- **Application**: A small business inventory management system.
- **Client Tier**: Desktop software that allows employees to check inventory levels.
- **Server Tier**: A database storing inventory details.

## Three Tier Architecture System
![[Pasted image 20250107101230.png]]

**3-Tier Architecture** is a software design model that separates an application into three distinct layers:
1. **Presentation Tier (Client Layer)**
2. **Application Tier (Business Logic Layer)**
3. **Data Tier (Database Layer)**
A three tier system is more secure, scalable and maintainable.

### Components of 3-Tier Architecture:
1. **Presentation Tier (Client Layer)**:
    - The topmost layer, responsible for the user interface.
    - Interacts with users, collects input, and displays the output.
    - Examples: Web browsers, mobile apps, or desktop apps.
2. **Application Tier (Business Logic Layer)**:
    - The middle layer that processes user inputs and executes business logic.
    - Acts as a bridge between the presentation and data tiers.
    - Example: A server-side application or API processing user requests.
3. **Data Tier (Database Layer)**:
    - The bottom layer responsible for storing and retrieving data.
    - Includes databases and database management systems.
    - Example: SQL Server, MySQL, PostgreSQL.

### Working of 3-Tier Architecture:
1. **Presentation Tier**: The user interacts with the application through a graphical user interface (GUI).
2. **Application Tier**: The GUI sends user requests to the application layer, where the business logic is processed.
3. **Data Tier**: The application layer queries the database, retrieves the required data, and sends it back to the presentation layer for display.

### Advantages of 3-Tier Architecture:
1. **Scalability**: Each layer can be scaled independently.
2. **Maintainability**: Changes in one layer don’t impact others (low coupling).
3. **Security**: Sensitive data is protected by restricting direct access to the database.
4. **Flexibility**: Supports diverse platforms and devices through the presentation layer.
5. **Reusability**: The application and data layers can serve multiple presentation layers.

### Disadvantages of 3-Tier Architecture:
1. **Complexity**: More components make implementation and maintenance harder.
2. **Performance Overhead**: Communication between layers can add latency.

### Example of 3-Tier Architecture:
**E-commerce Application (e.g., Amazon):**
1. **Presentation Tier**: A web browser or mobile app where customers browse products.
2. **Application Tier**: The server processes product searches, pricing calculations, and order management.
3. **Data Tier**: The database stores product details, customer information, and order history.


## Schema
In the context of databases, a **schema** is the **structure** or **blueprint** that defines how data is organised, stored, and related in a database. It specifies the database's logical structure, including its tables, fields, data types, relationships, constraints, and other elements.

*In a line: Schema = Logical Representation of a Database*

### Example:
**Student Database Schema**:

| Table Name: `Students` |
| ---------------------- |
| **Column Name**        |
| `Student_ID`           |
| `Name`                 |
| `Age`                  |
| `Department`           |

- This schema defines a table named `Students` with its structure and constraints.

### Three Tier Schema Architecture/Three level of Abstraction
![[Pasted image 20250108114424.png]]

The **Three Schema Architecture** system is a framework for designing and organising database systems. It separates the database system into three distinct layers:
- **Internal Schema (Physical Level)**: 
	- Describes how data is physically stored in the database.
	- Includes details about storage structures (e.g., indexes, file organisation) and access methods.
	- Example: Data blocks, file systems, and physical pointers.
- **Conceptual Schema (Logical Level)**:
	- Describes the structure of the entire database as a whole, abstracted from the physical storage.
	- Focuses on defining entities, relationships, constraints, and data types.
	- Example: Tables, fields, relationships, and constraints like primary and foreign keys.
- **External Schema (View Level)**:
	- Represents how data is presented to individual users or applications.
	- Provides multiple views of the database tailored to the needs of different users.
	- Example: A payroll system may provide separate views for HR staff, finance staff, and employees.

This separation helps in achieving **data abstraction**, enabling users to interact the database without worrying about how data is physically stored or managed.

**Data Abstraction:** Hiding unnecessary details from the end user to make the accessing of data easy and secure.

## Data Independence
**Data Independence** is a property of a DBMS, by which we can change the *database schema* at one level of the database system without changing the database schema at the next higher level.

### Types of Data Independence
There are **two** types of Data Independence:
1. **Logical Data Independence**
	- Changing the logical schema without changing the external schema.
	- Used to keep the external schema separate from the logical schema.
	- *For example*, it is possible to add or delete new entities, attributes to the conceptual schema without making any changes to the external schema.
2. **Physical Data Independence**
	- Making changes to the physical schema without changing the logical schema.
	- If the storage size of the DBMS server is changed, it will not affect the conceptual structure of the database.
	- *For example*, if the location of the database is changed from C: drive to D: drive, no changes will be reflected on the conceptual schema.

## Data Models in DBMS
A **data model** in DBMS is the concept of tools that are developed to summarise the description of the database. Data models provide us with a transparent picture of data which helps us in creating an actual database.

### Types of Database Models
1. **Conceptual Data Model:**
	- It describes the database at a very high level and is useful to understand the needs of requirements of the database.
	- *Example:* ER (Entity Relationship) Model.
2. **Representational Data Model:**
	- This type of data model is used to represent only the logical part of the database and does not represent the structure of the database.
	- *Example:* Relational Model.
3. **Physical Data Model:**
	- Used to practically implement relational data model.
	- All data in the database is stored physically on a secondary storage.
	- It is stored in the form of files, records and other data structures.
4. **Hierarchical Data Model**
	- Organizes data in a tree-like structure.
	- Data is represented as parent-child relationships.
	- *Example*: File systems where folders (parent) contain files (children).
5. **Network Data Model**
	- Organises data as a graph structure, with records connected with links.
	- Allows many-to-many relationships
	- *Example:* Social media networks where an user is connected with many friends.

## Entity-Relationship (ER) Model
The **ER Model** is a conceptual model that is used to describe the structure and relationships between data in a database. It helps in visually representing the logical structure of a database and provides a blueprint for creating a database schema.
[ER Model was introduced by Peter Chen in 1976]

### Components of an ER Model
![[Pasted image 20250109201049.png]]

#### Entity
An Entity may be an *object with a physical existence* – a particular person, car, house, or employee – or it may be an *object with a conceptual existence* – a company, a job, or a university course.

##### Entity Set
An Entity is an object of Entity Type and a ==set of all entities is called an entity set==. For Example, `E1` is an entity having Entity Type `Student` and the set of all students is called Entity Set. In ER diagram, Entity Type is represented as:
![[Pasted image 20250109201739.png]]

[We can represent the entity set in ER Diagram but can’t represent entity in ER Diagram because entity is row and column in the relation and ER Diagram is graphical representation of data.]

##### Types of Entity
There are two types of entities:
###### Strong Entity
A **Strong Entity** is a type of entity that has a *key attribute*. A strong entity doesn't depend on any other entity in the schema. It has a primary key, that helps in identifying it uniquely, and it is represented by a *rectangle*. These are called *Strong Entity Types*.

###### Weak Entity
A **weak entity** is an entity that cannot exist without the help of a related strong entity. It typically doesn't have a primary key of its own, and relies on the primary key of the related entity. It is represented by *double rectangles*.

**The relationship between the weak entity type and its identifying strong entity type is called identifying relationship and it is represented by a double diamond.**

**Example:**
Suppose, a company stores a `Dependants` (Spouse, Children) data for its `Employees`. Now, the dependants can't exist without the employee. So Dependent will be a **Weak Entity Type** and Employee will be Identifying Entity type for Dependent, which means it is **Strong Entity Type**.
![[Pasted image 20250109203636.png]]

#### Attributes
**Attributes** are the properties that define the entity type. For example, `Roll_No`, `Name`, `DOB`, `Age`, `Address`, and `Mobile_No` are the attributes that define entity type `Student`. In ER diagram, the attribute is represented by an *oval*. 

##### Types of Attributes
###### Key Attribute
The attribute which **uniquely identifies** each entity in the entity set. 
For example `RollNo` is unique for each student in a `Student` database. In ER Diagram, the key attribute is represented by an *oval with an underline*.
![[Pasted image 20250109204658.png]]

###### Composite Attribute
An attribute **composed of many other attributes** is called a composite attribute.
For example, the `Address` attribute in the `Student` database may consist of the following attributes like `StreetNo`, `City`, `State`, `Country`, etc.
![[Pasted image 20250109204858.png]]

###### Multi-valued Attribute
An attribute consisting of **more than one value** for a given entity.
For example, `Phone_No` can be more than one for a given student. In ER Diagram, it is represented by a *double oval*.

###### Derived Attribute
An attribute that can be **derived from other attributes** of the entity type.
For example, the `Age` of a student can be derived from their `DOB`. In ER Diagram, the derived attribute is represented by a *dashed oval*.

**DIAGRAM TO SHOW ATTRIBUTES FOR A `Student` ENTITY TYPE**
![[Pasted image 20250109205426.png]]

#### Relationship Type, Relationship Set, Cardinality
##### Relationship Type
In DBMS, a **relationship type** represents the **association** between entity types. 
For example, `Enrolled in` is a relationship type that exists between entity types `Student` and `Course`. In ER Diagrams, the relationship type is represented by a *diamond connecting the entities with lines*.
![[Pasted image 20250109205911.png]]

##### Relationship Set
A set of relationships of the same type is called a **relationship set**. 
The following relationship depicts S1 enrolled as C2, S2 enrolled as C1 and S3 as registered in C3. (*S - student; E = enrolled in; C = course*)
![[Pasted image 20250109210306.png]]

###### Degree in a Relationship Set
The number of different entity sets participating in a relationship set is called the degree of the relationship set.
1. **Unary Relationship**: When there is only ONE entity set participating in a relation.
   *Example:* A person is married to only one person.
   ![[Pasted image 20250109210542.png]]
2. **Binary Relationship**: When there are TWO entities' set participating in a relationship.
   *Example:* A student enrolled to a course.
   ![[Pasted image 20250109210912.png]]
3. **Ternary Relationship:** When there are three entities' set participating in a relationship.
4. **N-ary relationship:** When there are *n* entities' set participating in a relationship.

##### Cardinality
The number of times an entity of an entity set participates in a relationship set is known as **cardinality**. Cardinality can be of different types: 
1. **One-to-One:** When each entity in each entity set can take part only once in the relationship.
   *Example:* A Surgeon is head by the Head of Department.
   ![[Pasted image 20250109211626.png]]![[Pasted image 20250109211950.png]]
2. **One-to-Many:** In one-to-many mapping as well where each entity can be related to more than one entity and the total number of tables that can be used in this is 2.
   *Example:* One surgeon department has many surgeons.
   ![[Pasted image 20250109211727.png]]![[Pasted image 20250109212009.png]]
3. **Many-to-One:** When entities in one entity set can take part only once in the relationship set and entities in other entity sets can take part more than once in the relationship set.
   *Example:* Many patients are treated by one doctor.
   ![[Pasted image 20250109211805.png]]![[Pasted image 20250109212025.png]]
4. **Many-to-Many:** Many instances of one entity are related to many instances of another entity.
   *Example:* Many doctors treat many different diseases.
   ![[Pasted image 20250109211846.png]]![[Pasted image 20250109212034.png]]


## Keys
In DBMS, **keys** are *attributes* (or sets of attributes) used to uniquely identify rows (*tuples*) in a table. They play a crucial role in ensuring data integrity and establishing relationships between tables in a relational database. 

### Types of Keys
1. **Primary Key**
	- Uniquely identifies each **record** in a table.
	- A table can have only **one primary key**.
	- Attributes forming the primary key cannot contain `NULL` values.
	- Example: In a `Students` table, the `Student_ID` could be a primary key.
2. **Candidate Key**:
	- A set of attributes (*columns*) that can uniquely identify a record.
	- A table can have **multiple candidate keys**.
	- One of the candidate keys is chosen as the primary key.
	- Example: `Student_ID` and `Email` in a `Students` table could both serve as candidate keys.
3. **Foreign Key**
	- An attribute (or set of attributes) in one table that references the primary key of another table.
	- Used to establish relationships between tables, i.e. maintains the referential integrity.
	- Example: In an `Enrollments` table, `Student_ID` can be a foreign key referencing the `Student_ID` in the `Students` table.
4. **Super Key**
	- It is a combination of all possible attributes which can **uniquely identify two tuples** in a table.
	- *Super set* of any *candidate key* is *super key*.
	- Example: In a `Students` table, the super keys can be the `StudentID` and `Email`.

***Question*:** Consider the following datasets. Analyse them.

| Roll No. | Name | Address |
| -------- | ---- | ------- |
| 1        | A    | Mumbai  |
| 2        | B    | Delhi   |
| 3        | A    | Chennai |
Referenced Table

| Course ID | Course ID  | Roll No. |
| --------- | ---------- | -------- |
| C1        | DBMS       | 1        |
| C2        | Networking | 2        |
Referencing Table

***Answer:*** 
Referenced Table
	1. **Insert** - No violation (*no problems occur when we add another data*)
	2. **Delete** - May cause violation (*there may be a data which exists in the referencing table. E.g., we cannot delete Roll No. 1.*)
		Solution: 
			- On delete cascade (*i.e. if there is a data which has been already referenced as a foreign key, no deletion will occur.*)
			- On delete set null (*i.e. sets the data in the referencing table as NULL. Cannot use this method when foreign key acts as the primary key.*)
			- On delete no action
	3. **Update** - May cause violation (*cannot randomly change any primary key data*)

Referencing Table (*last stop*)
	1. **Insert** - May cause violation
	2. **Delete** - No violation
	3. **Update** - May cause violation

***Question:*** 
Let $R_1(\text{a, b, c})$ & $R_2(\text{x, y, z})$ be two relations in which 'a' is foreign key in $R_1$ that refers to primary key of $R_2$. Consider 4 options: (a) Insert into $R_1$; (b) Insert into $R_2$; (c) Delete from $R_1$; (d) Delete from $R_2$.
Which is correct regarding referential integrity:
1. (a) and (b) will cause violation.
2. (b) and (c) will cause violation.
3. (c) and (d) will cause violation.
4. **(d) and (a) will cause violation.** *Correct answer*

##### Super Key Calculations
###### How to determine the number of super keys in a dataset?
***1. Question***
Given that, R(A1, A2, A3, ... An) then how many candidate keys are possible?

