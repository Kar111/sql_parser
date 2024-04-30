
# SQL Query Parser

## Introduction
This project implements an SQL query parser in Java, designed to interpret and decompose complex SQL SELECT queries into a structured format. The parser supports a variety of SQL constructs including joins, subqueries, groupings, sorting, and truncation, making it a versatile tool for understanding and manipulating SQL queries programmatically.

## Features
- **Field Enumeration**: Supports explicit enumeration of fields with aliases and wildcard '*'.
- **Joins**:
    - Implicit joins (e.g., `SELECT * FROM A, B, C`)
    - Explicit joins (INNER, LEFT, RIGHT, FULL)
- **Filters**: Ability to parse conditions specified in the WHERE clause.
- **Subqueries**: Supports subqueries in the FROM clause.
- **Grouping and Sorting**: Handles GROUP BY and ORDER BY clauses.
- **Truncation**: Supports LIMIT and OFFSET for query result truncation.
- **Parser Structure**: Utilizes a class structure to encapsulate various components of SQL queries including columns, sources, joins, conditions, and more.

## Installation

### Prerequisites
- Java JDK 17 or higher
- Git

Usage
To use the SQL query parser, compile and run the Main class. The Main method demonstrates how the parser can be used to interpret various SQL queries.

// Example of running the parser
public class Main {
public static void main(String[] args) {
String query = "SELECT author.name, count(book.id), sum(book.cost) " +
"FROM author LEFT JOIN book ON (author.id = book.author_id) " +
"GROUP BY author.name HAVING COUNT(*) > 1 AND SUM(book.cost) > 500 " +
"LIMIT 10;";
Query parsedQuery = SQLQueryParser.parse(query);
System.out.println(parsedQuery);
}
}

