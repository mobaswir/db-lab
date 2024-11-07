# MySQL Installation and Setup Guide

This guide will help you install MySQL, verify the installation, set up a sample database, and load the HR schema.

---

## Installation

- **Download MySQL Installer (8.0.40)**  
   [Download MySQL](https://dev.mysql.com/downloads/installer/)

- **Installation Steps**  
   - Choose **Server Only**.
   - Click **Execute** and follow the prompts.
   - Click **Next** as needed.

- **Configuration**
   - Select **Development Computer** setup type.
   - **TCP/IP Settings**: 
     - **Port**: 3306
     - **X Protocol Port**: 33060
   - **Network Access**:
     - Ensure Windows Firewall ports are open for network access.

- **Authentication**
   - Use **Strong Password encryption** for authentication.
   - Set a password (make sure to remember it).

- **Access Permissions**
   - Grant full access as prompted.

- Click **Execute** to apply configurations, then **Finish** to complete the installation.

---

## Verification

1. **Open MySQL Command Line Client**:
   - Enter your password when prompted.

2. **Check Installed Databases**:
   - Run the following command:
     ```sql
     SHOW DATABASES;
     ```
   - This should display a list of databases (typically, there are about 4 default databases).

---

## Getting Started

1. **Create a Database**:
   ```sql
   CREATE DATABASE test_database;
   ```

2. **Switch to `test_database`**:
   ```sql
   USE test_database;
   ```

3. **Create a User**:
   ```sql
   CREATE USER 'test_admin'@'localhost' IDENTIFIED BY 'admin';
   ```

4. **Grant Privileges**:
   ```sql
   GRANT ALL PRIVILEGES ON test_database.* TO 'test_admin'@'localhost';
   ```

5. **Create a Sample Table and Insert Data**:
   - Create a table:
     ```sql
     CREATE TABLE test (name VARCHAR(50), email VARCHAR(50));
     ```

   - Insert data:
     ```sql
     INSERT INTO test (name, email) VALUES ('abc', 'abc@gmail.com');
     ```

6. **View Data**:
   ```sql
   SELECT * FROM test;
   ```

   Expected output:
   ```
   +------+---------------+
   | name | email         |
   +------+---------------+
   | abc  | abc@gmail.com |
   +------+---------------+
   ```

---

## Load the HR Schema

1. **Create and Use the HR Database**:
   ```sql
   CREATE DATABASE hr;
   USE hr;
   ```

2. **Source the `hr_mysql.sql` File**:
   ```sql
   SOURCE D:/hr_mysql.sql;
   ```

3. **Verify HR Data**:
   - Run a query to check if the data is loaded:
     ```sql
     SELECT * FROM employees;
     ```

---

Now you should have a MySQL server set up, with both `test_database` and `hr` loaded and ready to use. Enjoy exploring MySQL!