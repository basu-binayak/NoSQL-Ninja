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
