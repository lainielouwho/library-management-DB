# library-management-DB
MetaBooks: 
Library Management System Database
This repository contains the SQL scripts required to initialize, populate, and query a Library Management System. The database is designed to manage books, authors, publishers, member registrations, and the tracking of book loans and fines.
File Overview
Library DB.sql: The core schema definition. It creates the tables and defines the relationships (Primary and Foreign Keys).
some_queries.sql: A collection of DML (Data Manipulation Language) and DQL (Data Query Language) scripts to add sample data and perform common administrative tasks.
Database Schema
The database consists of the following relational tables:
Table
Description
PUBLISHER
Stores publishing house details including country of origin.
AUTHOR
Stores names of authors.
BOOK
The central catalog including ISBN, title, publication year, and real-time stock levels.
BOOK_AUTHOR
A junction table facilitating the many-to-many relationship between books and authors.
MEMBERS
User profiles for library patrons, including contact info and join dates.
LOAN
Tracks which members have borrowed which books, including due dates and return status.
FINE
Manages financial penalties for overdue book returns.

Getting Started
1. Initialization
Run the Library DB.sql script first to create the table structures.
Note: Ensure you have a database named LIBRARY created, or uncomment the CREATE DATABASE line in the script.
2. Populating Data
Use the some_queries.sql file to insert sample records for:
Publishers: (e.g., Bloomsbury, Tor Books).
Authors: (e.g., Neil Gaiman, Marie Lu).
Books: (e.g., Coraline, Ender's Game).
3. Common Operations
The provided query script includes examples for:
Member Management: Adding and deleting member records.
Data Analysis: Filtering books by publication year and calculating total stock grouped by genre.
Administrative Tracking: Identifying overdue books by comparing Due_date against a reference date.
Example Query: Stock by Genre
To see which genres are most prevalent in the library, the system uses the following logic:
SQL
SELECT Genre, SUM(Total_stock) AS Total_Books
FROM BOOK
GROUP BY Genre
ORDER BY Total_Books DESC;
