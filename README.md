# SQL_DEVEOLPER_TASK1
# 📚 Library Database Schema

This project contains the SQL script and ER diagram for a simple **Library Management System**. It demonstrates how to set up a relational database with proper entity relationships using **MySQL**.

---

## 🔧 Tools Used

- MySQL Workbench
- SQL (DDL)
- ER Diagram (Manually created)

---

## 🎯 Objective

To design and implement a structured relational database schema for a library system that manages books, members, and their borrowing transactions.

---

## 📁 Repository Structure

├── library_schema.sql # SQL script to create the database and tables
├── er_diagram.png # Entity-Relationship Diagram of the schema
└── README.md # Project documentation


---

## 🧱 Database Schema Overview

### 📄 Tables:
- **Members**: Stores member details
- **Books**: Stores book details
- **Loans**: Tracks book borrowing records

### 🔑 Relationships:
- Each member can borrow multiple books.
- Each loan record references one member and one book.

---

## 🗂️ SQL Script Summary

```sql
CREATE DATABASE LibraryDB;
USE LibraryDB;

CREATE TABLE Members (
    member_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100),
    membership_date DATE
);

CREATE TABLE Books (
    book_id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(150),
    author VARCHAR(100),
    isbn VARCHAR(20),
    published_year INT
);

CREATE TABLE Loans (
    loan_id INT AUTO_INCREMENT PRIMARY KEY,
    member_id INT,
    book_id INT,
    loan_date DATE,
    return_date DATE,
    FOREIGN KEY (member_id) REFERENCES Members(member_id),
    FOREIGN KEY (book_id) REFERENCES Books(book_id)
);

______

