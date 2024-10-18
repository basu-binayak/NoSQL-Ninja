# NoSQL-Ninja
NoSQL-Ninja is your go-to repository for mastering MongoDB and NoSQL databases. Discover practical examples, best practices, and tips to efficiently manage data in a flexible, schema-less environment. Whether you're a beginner or looking to sharpen your skills, this repository provides the resources you need to become a NoSQL expert!

## Understanding How MongoDB Works

MongoDB is a NoSQL database designed to store and manage large volumes of unstructured or semi-structured data. Unlike traditional relational databases that use tables and rows, MongoDB uses a flexible data model based on documents.

### Key Concepts

1. **Database**: 
   - In MongoDB, a database is a container for collections. Each database can hold multiple collections and is identified by a unique name. You can think of a database as a high-level structure that organizes your data.

2. **Collections**: 
   - Collections are analogous to tables in relational databases. Each collection contains a group of documents that share similar characteristics. However, collections do not enforce a fixed schema, allowing documents within the same collection to have different fields.

3. **Documents**: 
   - Documents are the basic units of data in MongoDB, represented in BSON (Binary JSON) format. A document consists of key-value pairs, similar to JSON objects. Each document can contain various data types, including strings, numbers, arrays, and even nested documents. This flexibility allows for dynamic data modeling that can evolve over time.

### How It Works Together

- When you create a database in MongoDB, you can create multiple collections within it. For example, in a database called `Library`, you might have collections like `Books`, `Authors`, and `Members`.
- Each collection then contains documents that represent individual records. In the `Books` collection, a document might include fields such as title, author, genre, and publication year.

This document-oriented approach provides scalability and flexibility, making MongoDB ideal for applications that require rapid iteration and diverse data formats.

Explore more in this repository to deepen your understanding of MongoDB and how to leverage its features effectively!

# MongoDB Installation Guide for Windows 10

This guide will walk you through the process of installing the latest version of MongoDB on Windows 10.

## Prerequisites
- Windows 10 (64-bit)
- Internet connection

## Steps

### 1. Download MongoDB

1. Open your preferred web browser (e.g., Chrome, Firefox).
2. Go to [MongoDB's official website](https://www.mongodb.com).
3. Hover over the **Products** menu and click on **Community Edition** under **MongoDB**.

### 2. Download MongoDB Community Server

1. Scroll down to the **MongoDB Community Server** section.
2. Ensure the following settings are selected:
   - **Version**: Latest (7.0 or the current version)
   - **OS**: Windows 64-bit
   - **Package**: MSI
3. Click **Download** to download the MSI installer.

### 3. Install MongoDB

1. Once the download is complete, locate the `.msi` installer file and double-click to open it.
2. Click **Next** to start the installation.
3. Accept the **License Agreement** and click **Next**.
4. Select **Complete** installation and click **Next**.
5. In the **Service Configuration** section:
   - Leave the default values as is (Service name: `MongoDB`).
   - Ensure **Install MongoDB as a Service** is checked.
   - Click **Next**.
6. Optionally, uncheck **Install MongoDB Compass** if you don't want the MongoDB UI.
7. Click **Next**, then **Install**.
8. Wait for the installation to complete, then click **Finish**.

### 4. Add MongoDB to the System Path

1. Open **File Explorer** and navigate to:
`C:\Program Files\MongoDB\Server\7.0\bin`
2. Copy the path to the **bin** folder.
3. Right-click on **This PC** or **Computer** and select **Properties**.
4. Click **Advanced system settings** on the left side.
5. In the **System Properties** window, click the **Environment Variables** button.
6. Under **System variables**, find **Path** and click **Edit**.
7. Click **New** and paste the copied path.
8. Click **OK** to close all windows.

### 5. Install MongoDB Shell (Optional)

1. Go back to [MongoDB's Download Center](https://www.mongodb.com/try/download/shell).
2. Select the **MSI** installer for your system (Windows 64-bit).
3. Click **Download** and run the installer.
4. Follow the installation instructions to complete the setup.

### 6. Verify MongoDB Installation

1. Open **Command Prompt**.
2. Type the following command to check the MongoDB version:
```bash
mongod --version
```
### 7. Run MongoDB
Open Command Prompt and type:
```bash
mongosh
```
To see the available databases, type:
```bash
show dbs
```
To create and switch to a new database, use:
```bash
use <database_name>
```

You are now ready to use MongoDB on Windows 10!

# Step-by-Step Guide: Create a Database and Insert Data

## Open MongoDB Shell (mongosh):

1. Open your Command Prompt and start the MongoDB shell by typing:
```bash
mongosh
```
2. You should see something like this if MongoDB is running successfully:
```bash
Current Mongosh Log ID: <id>
Using MongoDB: <version>
```
## Create (or switch to) a Database:
In MongoDB, you don’t need to explicitly create a database. You simply switch to the database, and it will be created once you insert data.
### Use the following command to create or switch to a database named myshop:
```bash
use myshop
```
MongoDB will switch to this database. If it doesn’t exist yet, it will create it when you insert your first document.
### Insert Data into a Collection:
In MongoDB, data is stored in collections (similar to tables in SQL databases).
Let’s create a collection called products and insert some data into it.
#### Inserting one document:
```bash
db.products.insertOne({
  name: "Laptop",
  price: 899,
  category: "Electronics",
  stock: 50
})
```
#### Inserting multiple documents:

```bash
db.products.insertMany([
  {
    name: "Smartphone",
    price: 599,
    category: "Electronics",
    stock: 100
  },
  {
    name: "Headphones",
    price: 199,
    category: "Accessories",
    stock: 150
  },
  {
    name: "Coffee Mug",
    price: 15,
    category: "Kitchen",
    stock: 200
  }
])
```
### Verify the Inserted Data:
To check if the data was successfully inserted, you can run a query to display all documents in the products collection:
```bash
db.products.find().pretty()
```
This should display the inserted products in a readable format:
```json
{
  "_id" : ObjectId("..."),
  "name" : "Laptop",
  "price" : 899,
  "category" : "Electronics",
  "stock" : 50
}
{
  "_id" : ObjectId("..."),
  "name" : "Smartphone",
  "price" : 599,
  "category" : "Electronics",
  "stock" : 100
}
{
  "_id" : ObjectId("..."),
  "name" : "Headphones",
  "price" : 199,
  "category" : "Accessories",
  "stock" : 150
}
{
  "_id" : ObjectId("..."),
  "name" : "Coffee Mug",
  "price" : 15,
  "category" : "Kitchen",
  "stock" : 200
}
```
### Querying the Data:
You can filter the data based on certain conditions. 
- For example, to find all electronics items:

```bash
db.products.find({ category: "Electronics" }).pretty()
````
- To find all products that cost more than $500:

```bash
db.products.find({ price: { $gt: 500 } }).pretty()
```
## Summary of Key Commands:
```bash
# Start MongoDB Shell
mongosh

# Create or switch to a database
use myshop

# Insert one document into the products collection
db.products.insertOne({
  name: "Laptop",
  price: 899,
  category: "Electronics",
  stock: 50
})

# Insert multiple documents
db.products.insertMany([
  { name: "Smartphone", price: 599, category: "Electronics", stock: 100 },
  { name: "Headphones", price: 199, category: "Accessories", stock: 150 },
  { name: "Coffee Mug", price: 15, category: "Kitchen", stock: 200 }
])

# View all data in the products collection
db.products.find().pretty()

# Query the data
db.products.find({ category: "Electronics" }).pretty()
db.products.find({ price: { $gt: 500 } }).pretty()
```
This should help you create a MongoDB database, insert data, and perform some simple queries!
