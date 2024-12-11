<img src="../assets/nosql.png" alt="Alt Text" width="400">

# NoSQL Databases Tutorial for Beginners

Learn the fundamentals of NoSQL databases, their types, and how to interact with them effectively.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Objectives](#objectives)
- [Prerequisites](#prerequisites)
- [Steps](#steps)
  - [Understanding NoSQL](#understanding-nosql)
  - [Document-Oriented: MongoDB](#document-oriented-mongodb)
  - [Key-Value Store: Redis](#key-value-store-redis)
  - [Wide-Column Store: Cassandra](#wide-column-store-cassandra)
  - [Graph Database: Neo4j](#graph-database-neo4j)
- [Best Practices](#best-practices)
- [Notes](#notes)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

NoSQL databases provide a mechanism for storage and retrieval of data that is modeled in means other than the tabular relations used in relational databases. They are widely used for large datasets and real-time applications.

<br>

## **Objectives**

By the end of this tutorial, you will:

- Understand the basic concepts of NoSQL databases and their types.
- Learn how to perform basic operations in different NoSQL database systems.
- Be able to choose the right NoSQL database for specific use cases.

<br>

## **Prerequisites**

To follow this tutorial, you should:

- Have basic knowledge of databases and data modeling.
- Have access to a computer where NoSQL databases can be installed.
- Be familiar with command-line operations.

<br>

## **Steps**

### **Understanding NoSQL**

#### What is NoSQL?

NoSQL databases are non-tabular databases that store data differently than relational tables. They are often used for large data sets and real-time web applications.

#### Types of NoSQL Databases

1. **Document-Oriented**: Stores data in documents similar to JSON (e.g., MongoDB, CouchDB).
2. **Key-Value Stores**: Data is stored as key-value pairs (e.g., Redis, DynamoDB).
3. **Wide-Column Stores**: Stores data in tables, rows, and dynamic columns (e.g., Cassandra, HBase).
4. **Graph Databases**: Uses graph structures for semantic queries (e.g., Neo4j, ArangoDB).

<br>

### **Document-Oriented: MongoDB**

| Command                       | Description                                                 | Example                                     |
|-------------------------------|-------------------------------------------------------------|---------------------------------------------|
| `use [database_name]`         | Switches to the specified database or creates it if it doesn’t exist. | `use mydb`                                  |
| `db.[collection].insert()`    | Inserts a document into the specified collection.          | `db.mydb.insert({name: "Alice", age: 30})` |
| `db.[collection].find()`      | Queries documents in a collection.                        | `db.mydb.find({name: "Alice"})`           |

<br>

### **Key-Value Store: Redis**

| Command       | Description                       | Example              |
|---------------|-----------------------------------|----------------------|
| `SET [key]`   | Sets a value for the specified key. | `SET mykey "Hello"` |
| `GET [key]`   | Retrieves the value of the key.   | `GET mykey`          |

<br>

### **Wide-Column Store: Cassandra**

| Command                          | Description                                         | Example                                                                                 |
|----------------------------------|-----------------------------------------------------|-----------------------------------------------------------------------------------------|
| `CREATE KEYSPACE`                | Creates a keyspace with replication configuration. | `CREATE KEYSPACE mykeyspace WITH replication = {'class':'SimpleStrategy', 'replication_factor' : 3};` |
| `CREATE TABLE`                   | Creates a table within a keyspace.                 | `CREATE TABLE mykeyspace.mytable (id UUID PRIMARY KEY, name text, age int);`           |

<br>

### **Graph Database: Neo4j**

| Command                             | Description                                      | Example                                                                 |
|-------------------------------------|--------------------------------------------------|-------------------------------------------------------------------------|
| `CREATE`                            | Creates a node with properties.                  | `CREATE (n:Person {name: 'Alice', age: 30})`                            |
| `MATCH ... CREATE`                  | Creates a relationship between existing nodes.   | `MATCH (a:Person), (b:Person) WHERE a.name = 'Alice' AND b.name = 'Bob' CREATE (a)-[r:KNOWS]->(b)` |

<br>

## **Best Practices**

- **Understand the Data Model**: Choose the NoSQL database that best fits your data model and query patterns.
- **Scalability**: Plan for scalability from the beginning.
- **Data Consistency**: Understand the consistency models of your NoSQL database.

<br>

## **Notes**

- **Pro Tip**: Document-oriented databases are flexible with schema changes.
- **Warning**: Ensure proper backups, as NoSQL databases can handle large-scale data with complex queries that might overwrite or alter data unexpectedly.

<br>

## **Resources**

- [MongoDB Documentation](https://www.mongodb.com/docs)
- [Redis Documentation](https://redis.io/documentation)
- [Apache Cassandra Documentation](https://cassandra.apache.org/doc/latest/)
- [Neo4j Documentation](https://neo4j.com/docs/)

<br>

## **Contribution**

Your contributions are highly encouraged to enhance this guide:

- Fork the repository.
- Create a new branch:

    ```bash
    git checkout -b my-awesome-feature
    ```

- Make your valuable changes.
- Commit your changes:

    ```bash
    git commit -am 'Added some amazing features'
    ```

- Push to the branch:

    ```bash
    git push origin my-awesome-feature
    ```

- Create a new Pull Request targeting the `Notes` directory.

Contributions are welcome! Feel free to open issues, suggest enhancements, or submit pull requests to improve this guide.

<br>

## **Author**

- **Raphael Chookagian** | [GitHub Profile](https://github.com/cesar-group)

## **Date of Latest Revision**

- 12/10/2024

## **License**

- This guide is provided as-is without any warranties. Users are advised to review and understand the guide before executing any commands.

- This project is licensed under the MIT License. See the LICENSE file for details.
