# Introduction to MongoDB

MongoDB is a popular NoSQL database designed for scalability, flexibility, and performance. This tutorial explores its key features, installation process, and how to perform basic operations like creating, reading, updating, and deleting documents.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Objectives](#objectives)
- [Prerequisites](#prerequisites)
- [Steps](#steps)
  - [Key Features of MongoDB](#key-features-of-mongodb)
  - [Installing MongoDB](#installing-mongodb)
  - [Performing CRUD Operations](#performing-crud-operations)
- [Notes](#notes)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

MongoDB is a document-oriented database that uses JSON-like documents with dynamic schemas. It is widely used in modern application development due to its ability to handle large amounts of unstructured data.

<br>

## **Objectives**

By the end of this tutorial, you will:

- Understand the key features of MongoDB.
- Learn how to install MongoDB on your system.
- Perform basic CRUD operations on a MongoDB database.

<br>

## **Prerequisites**

To follow this tutorial, you should:

- Have a basic understanding of databases and NoSQL concepts.
- Be familiar with the command line and terminal.
- Have administrative privileges to install software on your system.

<br>

## **Steps**

### **Key Features of MongoDB**

MongoDB offers several unique features that make it a preferred choice for many developers:

| Feature                     | Description                                                                 |
|-----------------------------|-----------------------------------------------------------------------------|
| **Schema Flexibility**      | Allows dynamic, schema-less document structures for versatile data storage. |
| **Scalability**             | Supports horizontal scaling through sharding.                              |
| **High Performance**        | Optimized for high read and write throughput.                              |
| **Rich Query Language**     | Provides powerful query capabilities using a JSON-like syntax.             |

<br>

### **Installing MongoDB**

Follow these steps to install MongoDB on your system:

1. **Update the Package Database** (for Debian-based systems):

   ```bash
   sudo apt update
   ```

2. **Install MongoDB**:

   ```bash
   sudo apt install -y mongodb
   ```

3. **Start the MongoDB Service**:

   ```bash
   sudo systemctl start mongodb
   ```

4. **Verify Installation**:

   ```bash
   mongo --version
   ```

<br>

### **Performing CRUD Operations**

Here are the basic CRUD operations you can perform with MongoDB:

#### **Create Documents**

Insert a document into a collection:

```bash
use myDatabase

db.myCollection.insert({ name: "John Doe", age: 30, city: "New York" })
```

#### **Read Documents**

Retrieve documents from a collection:

```bash
db.myCollection.find()
```

#### **Update Documents**

Update an existing document:

```bash
db.myCollection.update(
  { name: "John Doe" },
  { $set: { age: 31 } }
)
```

#### **Delete Documents**

Remove a document from a collection:

```bash
db.myCollection.remove({ name: "John Doe" })
```

<br>

## **Notes**

- MongoDB uses collections instead of tables and documents instead of rows, making it highly flexible.
- Ensure proper indexing for faster query performance.
- Always back up your database before performing major updates or deletions.

<br>

## **Resources**

- [MongoDB Documentation](https://www.mongodb.com/docs/): Official guide and references.
- [MongoDB University](https://university.mongodb.com/): Free courses to deepen your MongoDB knowledge.

<br>

## **Contribution**

Your contributions can enhance this tutorial:

- Fork the repository.
- Create a new branch:

  ```bash
  git checkout -b my-awesome-feature
  ```

- Make your changes.
- Commit your changes:

  ```bash
  git commit -am 'Improved MongoDB tutorial'
  ```

- Push to the branch:

  ```bash
  git push origin my-awesome-feature
  ```

- Create a new Pull Request targeting the Notes directory.

Contributions are welcome! Feel free to open issues, suggest enhancements, or submit pull requests to improve the script.

<br>

## **Author**

- **Raphael Chookagian** | [GitHub Profile](https://github.com/cesar-group)

## **Date of Latest Revision**

- 12/12/2024

## **License**

- This script is provided as-is without any warranties. Users are advised to review and understand the script before executing it.

- This project is licensed under the MIT License. See the LICENSE file for details.
