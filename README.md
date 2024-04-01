<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SQL Concepts</title>
<style>
    body {
        font-family: Arial, sans-serif;
        margin: 20px;
        line-height: 1.6;
    }
    h2 {
        color: #333;
    }
    code {
        font-family: Consolas, monospace;
        background-color: #f4f4f4;
        padding: 5px 10px;
        border-radius: 4px;
    }
</style>
</head>
<body>
    <h2>Basic SQL Concepts:</h2>
    <ol>
        <li>
            <strong>Introduction to SQL:</strong>
            <ul>
                <li><em>Definition of SQL:</em> Structured Query Language (SQL) is a standard language for managing and manipulating relational databases.</li>
                <li><em>Importance and usage in database management:</em> SQL allows users to interact with databases by querying, updating, and managing data.</li>
            </ul>
        </li>
        <li>
            <strong>Relational Databases:</strong>
            <ul>
                <li><em>Understanding the concept of relational databases:</em> Relational databases organize data into tables with rows and columns.</li>
                <li><em>Tables, rows, and columns:</em> Tables represent entities, rows contain individual records or tuples, and columns define attributes or fields of the data.</li>
            </ul>
        </li>
        <li>
            <strong>Basic Queries:</strong>
            <ul>
                <li><em>SELECT statement:</em> The SELECT statement retrieves data from one or more tables based on specified criteria.
                    <code>SELECT * FROM Users;</code></li>
                <li><em>Retrieving data from a single table:</em> Example queries demonstrating the retrieval of data from a single table using SELECT.
                    <code>SELECT username, email FROM Users;</code></li>
                <li><em>Use of WHERE clause for filtering data:</em> The WHERE clause filters data based on specified conditions, allowing users to retrieve specific subsets of data.
                    <code>SELECT * FROM Users WHERE username = 'john';</code></li>
            </ul>
        </li>
        <li>
            <strong>Sorting and Filtering:</strong>
            <ul>
                <li><em>ORDER BY clause for sorting:</em> The ORDER BY clause arranges query results in ascending or descending order based on specified columns.
                    <code>SELECT * FROM Users ORDER BY username ASC;</code></li>
                <li><em>LIMIT clause for limiting the number of rows returned:</em> The LIMIT clause restricts the number of rows returned by a query, which is useful for pagination or sampling.
                    <code>SELECT * FROM Users LIMIT 10;</code></li>
            </ul>
        </li>
        <li>
            <strong>Aggregate Functions:</strong>
            <ul>
                <li><em>SUM(), AVG(), MIN(), MAX(), COUNT() functions:</em> Aggregate functions perform calculations on a set of values and return a single result.
                    <code>SELECT COUNT(*) FROM Users;</code></li>
                <li><em>Grouping data with GROUP BY clause:</em> The GROUP BY clause groups rows that have the same values into summary rows, typically used with aggregate functions.
                    <code>SELECT department, AVG(salary) FROM Employees GROUP BY department;</code></li>
                <li><em>Filtering grouped data with HAVING clause:</em> The HAVING clause filters grouped data based on specified conditions, similar to the WHERE clause but used with aggregated data.
                    <code>SELECT department, AVG(salary) FROM Employees GROUP BY department HAVING AVG(salary) > 50000;</code></li>
            </ul>
        </li>
    </ol>

    <h2>Additional Concepts:</h2>
    <ul>
        <li>
            <strong>Constraints:</strong>
            <ul>
                <li><em>Primary Key:</em> Ensures each row in a table is uniquely identified.
                    <code>CREATE TABLE Orders (order_id INT PRIMARY KEY, product_id INT, quantity INT);</code></li>
                <li><em>Foreign Key:</em> Establishes a relationship between two tables based on a column in one table referencing the primary key in another.
                    <code>CREATE TABLE Orders (order_id INT PRIMARY KEY, product_id INT, quantity INT, FOREIGN KEY (product_id) REFERENCES Products(product_id));</code></li>
                <li><em>Unique Constraint:</em> Ensures that all values in a column are distinct.
                    <code>CREATE TABLE Users (user_id INT PRIMARY KEY, username VARCHAR(50) UNIQUE);</code></li>
                <li><em>Check Constraint:</em> Restricts the values that can be inserted into a column based on a logical expression.
                    <code>CREATE TABLE Employees (employee_id INT, age INT CHECK (age >= 18));</code></li>
                <li><em>Default Constraint:</em> Specifies a default value for a column when no value is explicitly provided.
                    <code>CREATE TABLE Students (student_id INT, grade VARCHAR(2) DEFAULT 'A');</code></li>
            </ul>
        </li>
        <li>
            <strong>Commands:</strong>
            <ul>
                <li><em>CREATE TABLE:</em> Creates a new table in the database.
                    <code>CREATE TABLE Products (product_id INT PRIMARY KEY, product_name VARCHAR(100), price DECIMAL(10,2));</code></li>
                <li><em>ALTER TABLE:</em> Modifies the structure of an existing table.
                    <code>ALTER TABLE Users ADD COLUMN date_joined DATE;</code></li>
                <li><em>DROP TABLE:</em> Deletes a table and its data from the database.
                    <code>DROP TABLE Products;</code></li>
                <li><em>INSERT INTO:</em> Adds new rows of data into a table.
                    <code>INSERT INTO Users (username, email) VALUES ('john_doe', 'john@example.com');</code></li>
                <li><em>UPDATE:</em> Modifies existing data in a table.
                    <code>UPDATE Users SET email = 'john.doe@example.com' WHERE user_id = 1;</code></li>
                <li><em>DELETE FROM:</em> Removes rows of data from a table.
                    <code>DELETE FROM Users WHERE user_id = 1;</code></li>
                <li><em>CREATE INDEX:</em> Creates an index on a table column to improve query performance.
                    <code>CREATE INDEX idx_username ON Users(username);</code></li>
                <li><em>CREATE VIEW:</em> Creates a virtual table based on the result set of a SELECT query.
                    <code>CREATE VIEW HighSalaryEmployees AS SELECT * FROM Employees WHERE salary > 100000;</code></li>
            </ul>

