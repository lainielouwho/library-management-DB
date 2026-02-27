# Library Management System

A relational database management system (RDBMS) designed to track library assets, member records, and borrowing activities. This project uses SQL to handle complex relationships between books, authors, publishers, and loans.

## 📂 Project Structure

* **`Library DB.sql`**: Contains the Data Definition Language (DDL) to create the `LIBRARY` database and its relational tables.
* **`some_queries.sql`**: Contains sample Data Manipulation Language (DML) for inserting records and administrative queries.

## 🏗️ Database Schema

The database is built on a relational model with the following tables:

| Table | Primary Key | Description |
| :--- | :--- | :--- |
| **`PUBLISHER`** | `Publisher_id` | Stores publishing house names and countries. |
| **`AUTHOR`** | `Author_id` | Stores author names. |
| **`BOOK`** | `Book_id` | Catalog of books including ISBN, stock levels, and genre. |
| **`MEMBERS`** | `Member_id` | Registered patrons with contact details and hashed passwords. |
| **`LOAN`** | `Loan_id` | Records of borrowed books, due dates, and return status. |
| **`FINE`** | `Fine_id` | Financial penalties associated with specific loans. |
| **`BOOK_AUTHOR`** | `(Book_id, Author_id)` | Junction table mapping books to their respective authors. |

## 🚀 Usage Examples

### 1. Data Insertion
The system allows for easy entry of new inventory. For example, adding a publisher:

```sql
INSERT INTO PUBLISHER (Publisher_id, Publisher_name, Country) 
VALUES (11, 'Bloomsbury', 'UK');

