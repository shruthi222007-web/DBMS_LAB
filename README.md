# DBMS Lab Exercises

> A comprehensive collection of **8 hands-on DBMS lab exercises** covering SQL fundamentals through advanced PL/SQL concepts. Perfect for students learning relational databases and procedural SQL.

Complete set of DBMS / PL-SQL lab exercises — SQL commands, PL/SQL blocks, expected outputs, and explanations, each in its own `.sql` file. Built from lab manual Ex. No. 1–8 (Simple/Nested/Sub Queries → Exception Handling).

---

## Table of Contents

- [Features & Highlights](#features--highlights)
- [Overview](#overview)
- [Repository Structure](#repository-structure)
- [Quick Start](#quick-start)
- [Exercise Index](#exercise-index)
  - [Ex 1: Simple, Nested & Sub Queries](#ex-1--simple-nested--sub-queries)
  - [Ex 2: Join Queries](#ex-2--join-queries)
  - [Ex 3: Views & Index](#ex-3--views--index)
  - [Ex 4: Implicit & Explicit Cursors](#ex-4--implicit--explicit-cursors)
  - [Ex 5: Procedures & Functions](#ex-5--procedures--functions)
  - [Ex 6: Triggers](#ex-6--triggers)
  - [Ex 7: Normalized Schema (Library System)](#ex-7--normalized-schema-library-system)
  - [Ex 8: Exception Handling](#ex-8--exception-handling)
- [Prerequisites & Setup](#prerequisites--setup)
- [How to Run](#how-to-run)
- [Database Compatibility](#database-compatibility)
- [Schema Summary](#schema-summary)
- [Troubleshooting](#troubleshooting)
- [Author & License](#author--license)

---

## Features & Highlights

* 8 Progressive Exercises — From basic queries to advanced PL/SQL
* Self-Contained Files — Each exercise is independent with complete setup
* Detailed Comments — Fully documented SQL/PL-SQL code
* Expected Outputs — Results shown inline for easy verification
* Oracle Connector Ready — Exercises 6–8 use Oracle SQL and PL/SQL syntax
* Real-World Schemas — Student enrollment, library system, and customer data
* Learning Outcomes — Each exercise builds foundational database skills
* Production-Ready — Best practices and proper syntax throughout

---

## Overview

This repository contains **8 DBMS lab exercises** covering core relational database and PL/SQL concepts, progressing from basic queries to advanced procedural SQL:

### Learning Path

| # | Topic | Difficulty | Time | Key Skills |
|---|-------|------------|------|-----------|
| 1 | Simple, Nested & Sub Queries | Beginner | 30 min | `SELECT`, `WHERE`, nested `IN`, scalar subqueries, `GROUP BY`/`HAVING` |
| 2 | Join Queries | Beginner+ | 40 min | `INNER JOIN`, `LEFT JOIN`, `RIGHT JOIN`, `FULL OUTER JOIN` |
| 3 | Views & Index | Beginner+ | 35 min | `CREATE VIEW`, DML through views, `CREATE INDEX`, performance tuning |
| 4 | Implicit & Explicit Cursors | Intermediate | 45 min | `%FOUND`, `%NOTFOUND`, `%ROWCOUNT`, `%ISOPEN`, cursor loops |
| 5 | Procedures & Functions | Intermediate | 50 min | `CREATE OR REPLACE PROCEDURE`, `CREATE OR REPLACE FUNCTION`, parameters |
| 6 | Triggers | Intermediate | 45 min | `BEFORE INSERT/UPDATE/DELETE` triggers, `:NEW`/`:OLD`, event handling |
| 7 | Normalized Schema (Library System) | Beginner+ | 40 min | ER modeling, normalization, M:N associative entities |
| 8 | Exception Handling | Intermediate | 40 min | Pre-defined & user-defined exceptions, error propagation |

### What's in Each File

Each `.sql` file is **self-contained** and includes:
- Header comment block — Exercise No., Title, Aim, and Algorithm (from lab manual)
- Table creation & sample data — `CREATE TABLE`, `INSERT` statements
- Fully commented SQL/PL-SQL — Every query explained step-by-step
- Expected output — Results shown as inline comments directly below each query
- Result statement — Summary of the outcome and learning points

---

## Repository Structure

```
DBMS_EXERCISE/
├── README.md                                    # This file
├── DBMS_Experiment_1_Simple_Nested_Subqueries.sql
├── DBMS_Experiment_2_JOIN_Queries.sql
├── DBMS_Experiment_3_View_and_Index.sql
├── DBMS_Experiment_4_Cursors.sql
├── DBMS_Experiment_5_Procedures_and_Functions.sql
├── DBMS_Experiment_6_triggers.sql
├── DBMS_Experiment_07_normalized_schema_library.sql
└── DBMS_Experiment_08_exception_handling.sql
```

> Note: Each `.sql` file is standalone — you can run any exercise independently without running the others.

---

## Quick Start

### For Oracle SQL Developer / SQL*Plus

1. Open your RDBMS client (Oracle SQL Developer or SQL*Plus)
2. Navigate to the `DBMS_EXERCISE` directory
3. Run an exercise file:
   ```sql
   @DBMS_Experiment_1_Simple_Nested_Subqueries.sql
   ```
4. View output — Results appear in the console

### For MySQL Workbench

1. Open MySQL Workbench → File → Open SQL Script
2. Select an exercise file (e.g., `DBMS_Experiment_1_Simple_Nested_Subqueries.sql`)
3. Execute — Click the Execute icon or press `Ctrl+Enter`

### For PostgreSQL (psql)

```bash
psql -U username -d database_name -f DBMS_Experiment_1_Simple_Nested_Subqueries.sql
```

---

## Exercise Index

### Ex 1 — Simple, Nested & Sub Queries

**File:** `DBMS_Experiment_1_Simple_Nested_Subqueries.sql`
**Difficulty:** Beginner
**Time:** 30 minutes

**What you'll learn:**
- Writing basic `SELECT` statements with `WHERE` clauses
- Using nested `IN` subqueries (3 levels deep)
- Scalar aggregate subqueries with functions like `AVG`, `MAX`, `MIN`
- Grouping and filtering results with `GROUP BY` and `HAVING`

**Concepts covered:**
- **Tables:** `Students`, `Courses`, `Enrollments`
- **Queries:** Simple filters → nested IN → scalar subqueries → GROUP BY/HAVING
- **Real-world example:** Finding students enrolled in multiple courses with average grades

---

### Ex 2 — Join Queries

**File:** `DBMS_Experiment_2_JOIN_Queries.sql`
**Difficulty:** Beginner+
**Time:** 40 minutes

**What you'll learn:**
- All four join types: `INNER`, `LEFT`, `RIGHT`, `FULL OUTER`
- Cross joins and self joins
- Join performance and optimization
- Handling NULL values in joins
- MySQL-compatible `UNION`-based workarounds (since MySQL lacks `FULL OUTER JOIN`)

**Concepts covered:**
- **Tables:** `Student`, `Courses`, `Enrollments`
- **Queries:** INNER JOIN → LEFT JOIN → RIGHT JOIN → FULL OUTER JOIN
- **Real-world example:** Finding students, their courses, and enrollment details with multiple join strategies

---

### Ex 3 — Views & Index

**File:** `DBMS_Experiment_3_View_and_Index.sql`
**Difficulty:** Beginner+
**Time:** 35 minutes

**What you'll learn:**
- Creating views with `CREATE VIEW`
- Performing DML operations (`INSERT`, `UPDATE`, `DELETE`) through views
- How view changes affect underlying tables and vice versa
- Creating and inspecting indexes for query optimization
- Index impact on performance

**Concepts covered:**
- **View Operations:** Creating views, modifying data through views, understanding updatable views
- **Indexes:** Creating indexes, checking index details with `SHOW INDEX`, query performance
- **Real-world example:** A student view for simplified access and an index on frequently searched columns

---

### Ex 4 — Implicit & Explicit Cursors

**File:** `DBMS_Experiment_4_Cursors.sql`
**Difficulty:** Intermediate
**Time:** 45 minutes

**What you'll learn:**
- Implicit cursor attributes: `SQL%FOUND`, `SQL%NOTFOUND`, `SQL%ROWCOUNT`, `SQL%ISOPEN`
- Explicit cursor declaration and usage
- Cursor loop patterns with `OPEN` → `FETCH` → `EXIT WHEN` → `CLOSE`
- Handling NO_DATA_FOUND exceptions
- Row-by-row processing in PL/SQL

**Concepts covered:**
- **Implicit Cursors:** Automatic cursor attributes after DML operations
- **Explicit Cursors:** Full cursor lifecycle management
- **Real-world example:** Bulk updating records and iterating through results with proper cursor control

---

### Ex 5 — Procedures & Functions

**File:** `DBMS_Experiment_5_Procedures_and_Functions.sql`
**Difficulty:** Intermediate
**Time:** 50 minutes

**What you'll learn:**
- Creating procedures with `CREATE OR REPLACE PROCEDURE`
- Creating functions with `CREATE OR REPLACE FUNCTION`
- Input (IN), output (OUT), and bidirectional (IN/OUT) parameters
- Return types and calling PL/SQL blocks
- Differences between procedures and functions

**Concepts covered:**
- **Procedures:** No return value, used for actions (`Sum_Numbers` procedure)
- **Functions:** Explicit return type, used for computations (`Sum_Function`)
- **Parameters:** IN (default), OUT, and IN/OUT modes
- **Real-world example:** Calculating sums and returning results to calling programs

---

### Ex 6 — Triggers

**File:** `DBMS_Experiment_6_triggers.sql`
**Difficulty:** Intermediate
**Time:** 45 minutes

**What you'll learn:**
- Creating row-level triggers with `BEFORE INSERT/UPDATE/DELETE`
- Using `:NEW` and `:OLD` pseudo-records
- Trigger timing: `BEFORE` vs `AFTER`
- Event handling: `INSERT`, `UPDATE`, `DELETE`
- Raising application errors with `RAISE_APPLICATION_ERROR`
- Trigger-based logging and validation

**Concepts covered:**
- **BEFORE INSERT trigger:** Validation and auto-calculation
- **BEFORE UPDATE trigger:** Tracking old vs new values
- **BEFORE DELETE trigger:** Logging deletion events
- **Real-world example:** Auto-logging changes, enforcing business rules (e.g., salary caps)

---

### Ex 7 — Normalized Schema (Library System)

**File:** `DBMS_Experiment_07_normalized_schema_library.sql`
**Difficulty:** Beginner+
**Time:** 40 minutes

**What you'll learn:**
- Entity-Relationship (ER) modeling
- Database normalization (1NF → 3NF)
- Many-to-Many (M:N) relationships using associative/junction tables
- Proper foreign key relationships
- Real-world schema design

**Concepts covered:**
- **Entities:** Authors, Books, Borrowers (independent entities)
- **Relationships:**
  - Books ↔ Authors (M:N via `BookAuthors`)
  - Borrowers ↔ Books (M:N via `BorrowedBooks`)
- **Real-world example:** A complete library system with proper normalization

---

### Ex 8 — Exception Handling

**File:** `DBMS_Experiment_08_exception_handling.sql`
**Difficulty:** Intermediate
**Time:** 40 minutes

**What you'll learn:**
- Pre-defined exceptions: `NO_DATA_FOUND`, `TOO_MANY_ROWS`, `OTHERS`
- User-defined exceptions with `EXCEPTION ... WHEN`
- Exception propagation and handling
- Using `RAISE` and `RAISE_APPLICATION_ERROR`
- Error messages and logging

**Concepts covered:**
- **Pre-defined Exceptions:** Automatic Oracle exceptions (`NO_DATA_FOUND`, `OTHERS`)
- **User-defined Exceptions:** Custom exceptions for business logic (`ex_invalid_id`)
- **Exception Handling:** `BEGIN...EXCEPTION...END` blocks
- **Real-world example:** Validating user input and raising appropriate errors on violations

---

## Prerequisites & Setup

### System Requirements

| Component | Requirement | Notes |
|-----------|-------------|-------|
| RDBMS | Oracle 12c+ | Required for the identity columns used by Exercise 7 |
| Client | Oracle SQL Developer, SQL*Plus, Oracle connector for VS Code, or DBeaver | Use an Oracle connection |
| OS | Windows, macOS, or Linux | DBMS software is cross-platform |
| Disk Space | 100 MB (minimum) | For DBMS installation + sample data |
| RAM | 2 GB (minimum) | Most modern systems have this |

### Which Database Should I Choose?

**For beginners and academic coursework:**
- **Oracle** — Best for exercises 4–8 (PL/SQL features)
- **MySQL** — Great for exercises 1–3, 7 (standard SQL); requires workarounds for 4–6, 8
- **PostgreSQL** — Good for exercises 1–3, 7; requires PL/pgSQL translation for 4–6, 8

**Recommended:** Use **Oracle** for the complete course workflow. Exercises 6–8
are written for Oracle and should be run through an Oracle connector, not MySQL
Workbench.

### Installation Links

- PostgreSQL (Free): https://www.postgresql.org/download/
- MySQL (Free): https://dev.mysql.com/downloads/mysql/
- Oracle XE (Free): https://www.oracle.com/database/technologies/xe-downloads.html
- Oracle SQL Developer (Free): https://www.oracle.com/tools/downloads/sqldev-downloads.html

### Client Tools (IDE / GUI)

| Tool | Best For | Cost | Platform |
|------|----------|------|----------|
| Oracle SQL Developer | Oracle DB | Free | Win/Mac/Linux |
| SQL*Plus | Oracle DB (CLI) | Free | Win/Mac/Linux |
| MySQL Workbench | MySQL | Free | Win/Mac/Linux |
| pgAdmin | PostgreSQL | Free | Win/Mac/Linux |
| DBeaver | Any RDBMS | Free/Pro | Win/Mac/Linux |
| VS Code + Extensions | Any (with extensions) | Free | Win/Mac/Linux |

---

## How to Run

### Oracle SQL Developer or SQL*Plus

**Using SQL Developer (GUI):**

1. Open Oracle SQL Developer
2. Create or connect to a database
3. File → Open → Select a `.sql` file (e.g., `DBMS_Experiment_1_Simple_Nested_Subqueries.sql`)
4. Click the Execute button or press `Ctrl+Enter`
5. View results in the Script Output panel

**Using SQL*Plus (Command Line):**

```bash
# Connect to Oracle
sqlplus username/password@database

# Run a script from SQL*Plus prompt
SQL> @DBMS_Experiment_1_Simple_Nested_Subqueries.sql

# Enable output (important for PL/SQL!)
SQL> SET SERVEROUTPUT ON

# Exit
SQL> EXIT;
```

**Using an Oracle connector in VS Code:**

1. Install an Oracle database extension that supports SQL scripts and PL/SQL.
2. Create an Oracle connection and open the database connection in the extension.
3. Open one of `DBMS_Experiment_6_triggers.sql`,
  `DBMS_Experiment_07_normalized_schema_library.sql`, or
  `DBMS_Experiment_08_exception_handling.sql`.
4. Choose the extension's **Run Script** or **Run SQL** command for the active
  Oracle connection. Do not use a MySQL connection for these files.
5. Enable the extension's DBMS Output panel when running Exercises 6 or 8.

Exercises 6–8 drop their own objects before creating them, so each file can be
run independently and repeatedly in the same Oracle schema.

### Oracle Connector Checklist

Use the following checklist when running the converted exercises:

- Connect to an Oracle 12c or newer database before executing the script.
- Run the complete file as a script so `/` terminators compile PL/SQL blocks.
- Enable DBMS Output before running Exercises 6 or 8.
- Run Exercise 7 before checking its library verification queries.
- Re-running a converted exercise is supported because its objects are dropped first.
- Use a schema with permission to create tables, triggers, and PL/SQL blocks.
- Review the connector's script output for ORA- errors after execution.
- Run each exercise in its own Oracle schema session when isolating lab results.
- Keep the Oracle connection active while the script creates dependent objects.
- Confirm the active connection belongs to the intended Oracle schema.
- Do not substitute MySQL delimiter commands for the Oracle `/` block terminator.
- Exercise 8 uses a fixed sample customer ID and requires no substitution prompt.
- Exercise 6 catches the expected validation error so the script can continue.
- Exercise 7 uses Oracle `DATE` literals to avoid session date-format issues.
- After successful execution, use the included `SELECT` statements to verify rows.

**Important:** Make sure `SET SERVEROUTPUT ON` is enabled so that `DBMS_OUTPUT.PUT_LINE` output is visible (this is included in each PL/SQL file).

---

### MySQL Workbench (Exercises 1–3 only)

**Step-by-step:**

1. Open MySQL Workbench
2. Click File → Open SQL Script
3. Select an exercise file (e.g., `DBMS_Experiment_1_Simple_Nested_Subqueries.sql`)
4. Click the Execute button or press `Ctrl+Shift+Enter`
5. Check the Output tab for results

**Alternative — Command line:**

```bash
mysql -u username -p database_name < DBMS_Experiment_1_Simple_Nested_Subqueries.sql
```

**Note:** Exercises 4, 5, 6, 8 use Oracle PL/SQL syntax and require translation to MySQL stored procedures.

---

### PostgreSQL (Exercises 1–3 only)

**Using pgAdmin (GUI):**

1. Open pgAdmin → Expand your server
2. Right-click your database → Query Tool
3. Click Open → Select a `.sql` file
4. Click Execute or press `F5`
5. View results in the panel below

**Using psql (Command Line):**

```bash
# Connect to PostgreSQL database
psql -U username -d database_name

# Run a script
\i DBMS_Experiment_1_Simple_Nested_Subqueries.sql

# Or execute directly without connecting first
psql -U username -d database_name -f DBMS_Experiment_1_Simple_Nested_Subqueries.sql
```

**Note:** Exercises 4, 5, 6, 8 use Oracle PL/SQL and require translation to PL/pgSQL.

---

## Database Compatibility

### Exercise Support by Database

| Exercise | Oracle | MySQL | PostgreSQL | Notes |
|----------|:------:|:-----:|:----------:|-------|
| Ex 1 — Simple, Nested & Sub Queries | Yes | Yes | Yes | Standard SQL — all databases supported |
| Ex 2 — Join Queries | Yes | Partial | Yes | MySQL needs `UNION` workaround for `FULL OUTER JOIN` |
| Ex 3 — Views & Index | Yes | Yes | Yes | Standard SQL — all databases supported |
| Ex 4 — Implicit & Explicit Cursors | Yes | No | No | Oracle PL/SQL only; MySQL/PostgreSQL use different cursor syntax |
| Ex 5 — Procedures & Functions | Yes | Partial | Partial | Oracle syntax; MySQL/PostgreSQL require stored procedure syntax changes |
| Ex 6 — Triggers | Yes | Partial | Partial | Oracle `:NEW`/`:OLD`; MySQL/PostgreSQL use `NEW`/`OLD` |
| Ex 7 — Normalized Schema | Yes | No | No | Oracle identity columns and `DATE` literals |
| Ex 8 — Exception Handling | Yes | No | No | Oracle PL/SQL exception syntax; others use different approaches |

### Legend
- Yes — Supported: Works out-of-the-box
- Partial — Minor Changes: Requires syntax adjustments
- No — Not Supported: Requires significant translation or alternative approach

### Database-Specific Notes

#### Oracle (Recommended for Learning)
- **Best for:** All 8 exercises (complete feature coverage)
- **Advantages:** 
  - All exercises work natively
  - Industry-standard PL/SQL
  - Rich feature set for learning
- **Setup:** Oracle XE (free) is sufficient for coursework

#### MySQL
- **Best for:** Exercises 1–3, 7
- **Limitations:**
  - Exercises 4, 5, 6, 8 require syntax translation
  - No native `FULL OUTER JOIN` (use `UNION` workaround)
  - Uses stored procedures instead of PL/SQL blocks
- **Workarounds:**
  - `FULL OUTER JOIN` emulation: Use `UNION` of left and right joins
  - Procedures: Use `CREATE PROCEDURE...BEGIN...END`
  - Exception handling: Use MySQL error handling syntax

#### PostgreSQL
- **Best for:** Exercises 1–3, 7
- **Limitations:**
  - Exercises 4, 5, 6, 8 require PL/pgSQL translation
  - Different trigger syntax (NEW/OLD instead of :NEW/:OLD)
  - Different exception handling
- **Workarounds:**
  - Use PL/pgSQL blocks instead of PL/SQL
  - Translate `DBMS_OUTPUT.PUT_LINE` to `RAISE NOTICE`
  - Use PostgreSQL-specific trigger and exception syntax

---

## Schema Summary

### Schema Overview

This repository uses multiple schemas to teach different concepts:

#### Schema 1: Student Enrollment System (Exercises 1–3)

```sql
Students / Student
├── StudentID (Primary Key)
├── Name
└── Age

Courses
├── CourseID (Primary Key)
└── CourseName

Enrollments
├── EnrollmentID (Primary Key)
├── StudentID (Foreign Key → Students)
└── CourseID (Foreign Key → Courses)
```

**Real-world use:** Track student course enrollments and grades

#### Schema 2: Customer Database (Exercises 4–6)

```sql
customers
├── id (Primary Key)
├── name
├── address
└── salary

customer
├── sid (Primary Key)
├── sname
└── stotal

classb
├── sid (Primary Key)
├── sname
├── sdept
├── stotal
└── grade
```

**Real-world use:** Customer account management with department tracking

#### Schema 3: Library Management System (Exercise 7)

```sql
Authors
├── AuthorID (Primary Key)
├── FirstName
└── LastName

Books
├── BookID (Primary Key)
├── Title
├── Genre
└── PublicationYear

Borrowers
├── BorrowerID (Primary Key)
├── FirstName
├── LastName
└── MembershipDate

BookAuthors (M:N Junction Table)
├── BookID (Foreign Key → Books)
├── AuthorID (Foreign Key → Authors)

BorrowedBooks (M:N Junction Table)
├── BorrowerID (Foreign Key → Borrowers)
├── BookID (Foreign Key → Books)
├── BorrowedDate
└── ReturnDate
```

**Real-world use:** Complete library system with authors, books, and borrower tracking

### Key Concepts Demonstrated

- **Primary Keys:** Unique identifiers for each entity
- **Foreign Keys:** Relationships between tables
- **Normalization:** Reduced data redundancy and improved integrity
- **Associative Tables:** Junction tables for many-to-many relationships (BookAuthors, BorrowedBooks)
- **Data Types:** VARCHAR, INT, DATE, NUMBER
- **Constraints:** NOT NULL, UNIQUE, FOREIGN KEY relationships

---

## Troubleshooting

### Common Issues & Solutions

#### "ORA-06550: Line 1, Column 7: PLS-00103: Encountered the symbol 'CREATE'"
**Problem:** PL/SQL block execution issue
**Solution:** Ensure `SET SERVEROUTPUT ON` is set before running PL/SQL blocks

```sql
SET SERVEROUTPUT ON;
-- Then run your script
@DBMS_Experiment_4_Cursors.sql
```

#### "Table 'tablename' doesn't exist"
**Problem:** Running exercise in wrong database or database not initialized
**Solution:**
- Verify you're connected to the correct database
- Ensure you're running the `.sql` file from the beginning (includes `CREATE TABLE` statements)

#### "MySQL: FULL OUTER JOIN not supported"
**Problem:** MySQL doesn't have native `FULL OUTER JOIN`
**Solution:** Use the `UNION`-based workaround included in Exercise 2:

```sql
-- FULL OUTER JOIN emulation in MySQL
SELECT * FROM table1 LEFT JOIN table2 ON ...
UNION
SELECT * FROM table1 RIGHT JOIN table2 ON ...;
```

#### "PostgreSQL: function dbms_output.put_line(...) does not exist"
**Problem:** Trying to run Oracle PL/SQL on PostgreSQL
**Solution:** Translate `DBMS_OUTPUT.PUT_LINE` to `RAISE NOTICE`:

```plpgsql
-- Oracle
DBMS_OUTPUT.PUT_LINE('Hello World');

-- PostgreSQL
RAISE NOTICE 'Hello World';
```

#### "Syntax error near ':='"
**Problem:** Running Oracle PL/SQL on MySQL/PostgreSQL
**Solution:** Differences in syntax for variable assignment and procedures. Consult database-specific stored procedure documentation.

#### "No rows returned" (when expecting results)
**Problem:** Data not inserted properly or query has wrong logic
**Solution:**
1. Check `INSERT` statements completed successfully
2. Verify `WHERE` clause conditions
3. Run intermediate `SELECT` queries to debug
4. Check table contents: `SELECT * FROM table_name;`

#### "Permission denied" when running scripts
**Problem:** User doesn't have required privileges
**Solution:**
- Ensure user account has `CREATE TABLE`, `INSERT`, `SELECT` privileges
- For PL/SQL: User needs `CREATE PROCEDURE` and `CREATE TRIGGER` privileges
- Connect as an admin/privileged user if needed

### Debugging Tips

1. **Enable verbose output:**
   ```sql
   SET SERVEROUTPUT ON SIZE 20000;  -- Oracle
   ```

2. **Run queries step-by-step:**
   - Don't run the entire file; execute queries individually
   - Check each `SELECT` output before proceeding

3. **Check table structure:**
   ```sql
   -- Oracle
   DESC table_name;

   -- MySQL
   SHOW COLUMNS FROM table_name;

   -- PostgreSQL
   \d table_name
   ```

4. **Review error messages carefully:**
   - Note the line number where the error occurred
   - Look for syntax issues or missing objects

5. **Consult database documentation:**
   - Oracle: `SELECT * FROM USER_TABLES;` lists your tables
   - MySQL: `SHOW TABLES;`
   - PostgreSQL: `\dt` lists tables

---

## Author & License

### Author

**Thamizhselvan_M**
B.E. Computer Science and Engineering
IFET College of Engineering
GitHub: [thamizhselvanm-web](https://github.com/thamizhselvanm-web)

---

### License

**Academic & Educational Use**

This project is created for **academic and educational purposes**. It's designed to support DBMS lab coursework and is freely available for:
- Educational use in classroom settings
- Personal learning and skill development
- Forking and adapting for your own coursework
- Sharing with other students (with attribution)

**Please cite:** If you use this repository in your coursework or publications, please provide attribution to Thamizhselvan_M.

---

### Contributing

Have improvements or corrections? Feel free to:
- Report issues in GitHub
- Submit pull requests for bug fixes
- Suggest enhancements

---

### Support & Questions

For questions about:
- **SQL/Database concepts** — Refer to database-specific documentation
- **DBMS topics** — Check standard textbooks or official documentation
- **This repository** — Create an issue on GitHub

**Additional Resources:**
- [Oracle Documentation](https://docs.oracle.com/en/database/)
- [MySQL Documentation](https://dev.mysql.com/doc/)
- [PostgreSQL Documentation](https://www.postgresql.org/docs/)

---

### Disclaimer

> This repository is provided AS-IS for educational purposes. Users are responsible for understanding the code and ensuring it's appropriate for their use case. The author is not liable for any damages or issues arising from the use of these exercises.

---

---

## Getting Started Tips

### For First-Time Learners

1. **Start with Exercise 1** — Establish foundational SQL knowledge before moving to PL/SQL
2. **Read comments carefully** — Each SQL file contains detailed explanations
3. **Run queries individually** — Execute one query at a time to understand output
4. **Experiment with data** — Modify queries and observe how results change
5. **Review Oracle documentation** — Reference official docs when encountering unfamiliar concepts

### Recommended Learning Sequence

- **Week 1:** Exercises 1–3 (Core SQL fundamentals)
- **Week 2:** Exercise 7 (Database design & normalization)
- **Week 3:** Exercises 4–5 (PL/SQL basics)
- **Week 4:** Exercises 6 & 8 (Advanced PL/SQL features)

### Common Pitfalls to Avoid

- Running entire `.sql` files without reading the code
- Skipping normalization concepts (Exercise 7)
- Not enabling `SET SERVEROUTPUT ON` for PL/SQL blocks
- Modifying database structure without backing up data
- Ignoring database-specific syntax differences

### Performance Considerations

- **Indexes:** Use indexes on frequently searched columns to improve query speed
- **Query Optimization:** Analyze execution plans for complex queries
- **Join Strategy:** Consider join order and type for optimal performance
- **Cursor Usage:** Use explicit cursors only when necessary; prefer set operations
- **Commit Strategy:** Batch transactions appropriately to avoid locking issues

### Exercise Prerequisites & Dependencies

| Exercise | Prerequisite Knowledge | Required for |
|----------|----------------------|--------------|
| Ex 1 | Basic SQL SELECT syntax | Exercises 2–3 |
| Ex 2 | Exercise 1 completion | Exercises 3–7 |
| Ex 3 | Exercises 1–2 | Exercise 7 |
| Ex 4 | Exercise 1, basic PL/SQL | Exercises 5–6, 8 |
| Ex 5 | Exercise 4 | Exercises 6, 8 |
| Ex 6 | Exercise 5 | Exercise 8 |
| Ex 7 | Exercises 1–3 | Advanced DB design |
| Ex 8 | Exercises 4–5 | Production code review |

### Learning Outcomes by Exercise

After completing all exercises, you should be able to:

**SQL Skills (Exercises 1–3, 7):**
- Write complex SELECT queries with multiple conditions
- Design normalized database schemas
- Create and maintain database views
- Implement indexing strategies
- Perform different types of joins

**PL/SQL Skills (Exercises 4–6, 8):**
- Write PL/SQL blocks with declarations and executable sections
- Implement explicit and implicit cursors
- Create reusable procedures and functions
- Design and implement database triggers
- Handle exceptions gracefully
- Debug PL/SQL code effectively

### Verifying Your Setup

Before running exercises, verify your environment:

**Oracle Setup:**
```sql
SELECT * FROM V$VERSION;  -- Check Oracle version
SELECT USER FROM DUAL;    -- Verify connected user
SET SERVEROUTPUT ON;      -- Enable output
```

**MySQL Setup:**
```sql
SELECT VERSION();         -- Check MySQL version
SELECT USER();            -- Verify current user
SELECT DATABASE();        -- Confirm database selection
```

**PostgreSQL Setup:**
```sql
SELECT VERSION();         -- Check PostgreSQL version
SELECT CURRENT_USER;      -- Verify current user
\l                        -- List all databases
```

### Common SQL Patterns Used in Exercises

| Pattern | Purpose | Exercise(s) |
|---------|---------|------------|
| INNER JOIN | Combine related tables | Ex 2 |
| LEFT OUTER JOIN | Include unmatched rows | Ex 2 |
| Subquery in WHERE | Filter based on aggregation | Ex 1 |
| GROUP BY + HAVING | Aggregate with conditions | Ex 1 |
| UNION | Combine result sets | Ex 2 |
| Scalar Subquery | Single-value expression | Ex 1, 5 |
| CREATE VIEW | Store reusable query | Ex 3 |
| CREATE INDEX | Improve query performance | Ex 3 |
| Normalization | Reduce data redundancy | Ex 7 |

### PL/SQL Best Practices

**Cursor Management:**
- Always close cursors after use to free resources
- Use `FOR ... IN` loop for automatic cursor management
- Avoid cursor loops for large result sets
- Consider using bulk operations with `FORALL`

**Error Handling:**
- Always include exception handlers in production code
- Use specific exception types, not generic OTHERS
- Log error details before raising or re-raising exceptions
- Provide meaningful error messages to users

**Code Organization:**
- Use meaningful names for procedures, functions, and variables
- Include comments explaining complex logic
- Keep procedures focused on single responsibilities
- Use packages to organize related procedures and functions

**Performance:**
- Test queries before embedding in procedures
- Use bind variables to avoid recompilation
- Monitor execution time for large operations
- Consider parallel execution for heavy workloads

### Trigger Design Patterns (Exercise 6)

**Audit Triggers:**
Track changes to sensitive columns
```sql
BEFORE INSERT OR UPDATE ON employees
FOR EACH ROW
BEGIN
  INSERT INTO audit_log VALUES(:NEW.id, SYSDATE, USER);
END;
```

**Validation Triggers:**
Enforce business rules
```sql
BEFORE INSERT ON orders
FOR EACH ROW
BEGIN
  IF :NEW.quantity < 0 THEN
    RAISE_APPLICATION_ERROR(-20001, 'Quantity cannot be negative');
  END IF;
END;
```

**Cascade Triggers:**
Maintain referential integrity
```sql
BEFORE DELETE ON departments
FOR EACH ROW
BEGIN
  DELETE FROM employees WHERE dept_id = :OLD.dept_id;
END;
```

**Performance Tips for Triggers:**
- Keep trigger logic minimal
- Avoid recursive triggers
- Use simple SQL, not complex queries
- Test trigger performance with realistic data volumes

### Database Normalization Theory (Exercise 7)

**1st Normal Form (1NF):**
- Eliminate repeating groups
- Ensure atomic values in each column
- Each cell contains single, indivisible value

**2nd Normal Form (2NF):**
- Must satisfy 1NF
- Remove partial dependencies
- Non-key attributes depend on entire primary key

**3rd Normal Form (3NF):**
- Must satisfy 2NF
- Remove transitive dependencies
- Non-key attributes depend only on primary key

**Denormalization Trade-offs:**
- Improved query performance through reduced joins
- Risk of data inconsistency
- Increased storage requirements
- Use carefully for specific performance bottlenecks

**Exercise 7 Includes:**
- Converting unnormalized data to 3NF
- Identifying candidate keys
- Resolving multivalued dependencies
- Creating entity-relationship diagrams

### Practice Assignments & Extensions

**After Exercise 1:**
- Write a query using ALL comparison operator
- Create a subquery using correlated subqueries
- Find students with above-average performance

**After Exercise 2:**
- Combine four tables using different join types
- Create a complex query with multiple joins
- Analyze join performance with EXPLAIN PLAN

**After Exercise 3:**
- Create indexed views on frequently queried data
- Test index impact on query performance
- Implement partial indexes for specific conditions

**After Exercise 4:**
- Write a cursor fetching 1000+ rows efficiently
- Implement error handling within cursor loops
- Use cursor attributes (FOUND, NOTFOUND, ROWCOUNT)

**After Exercise 5:**
- Create a function returning complex data type
- Implement function with multiple OUT parameters
- Handle exceptions within function body

**After Exercise 6:**
- Design cascade triggers for multi-level updates
- Implement audit trail with triggers
- Create disabled triggers for maintenance windows

**After Exercise 8:**
- Implement custom exception types
- Create exception handler for all SQL errors
- Log exceptions to audit table

### Assessment Criteria for Exercises

**Code Quality Evaluation:**
- Readability: Well-commented, meaningful variable names
- Correctness: Produces accurate results for all test cases
- Efficiency: Runs within acceptable time limits
- Robustness: Handles edge cases and errors gracefully
- Best Practices: Follows SQL/PL-SQL standards

**Exercise Submission Checklist:**
- [ ] All required queries/procedures implemented
- [ ] Code includes comments explaining logic
- [ ] All error cases handled appropriately
- [ ] Results verified against expected output
- [ ] Performance verified for large datasets
- [ ] No hard-coded values or magic numbers
- [ ] Database objects properly named and documented
- [ ] Commit messages explain the work done

**Testing Strategy:**
- Test with sample data provided
- Test with boundary values (empty sets, null values)
- Test with large result sets (1000+ rows)
- Verify error handling with invalid inputs
- Document all test cases and results

### Reference Materials & Resources

**Oracle Documentation:**
- Oracle SQL Language Reference: [docs.oracle.com/sql-lang](https://docs.oracle.com)
- PL/SQL Language Reference: [docs.oracle.com/plsql](https://docs.oracle.com)
- Oracle Database Administration Guide: [docs.oracle.com/dba-guide](https://docs.oracle.com)

**MySQL Documentation:**
- MySQL SQL Reference: [dev.mysql.com/doc](https://dev.mysql.com/doc)
- MySQL PL/SQL Equivalent (Stored Procedures): [dev.mysql.com/doc/refman](https://dev.mysql.com)

**PostgreSQL Documentation:**
- PostgreSQL SQL Reference: [postgresql.org/docs](https://www.postgresql.org/docs)
- PL/pgSQL Language: [postgresql.org/docs/plpgsql](https://www.postgresql.org/docs)

**Educational Resources:**
- Database Normalization Tutorial: W3Schools Database Normalization
- SQL JOIN Visualizer: Visual guide to SQL JOINs
- Explain Plan Analyzer: Tools for query optimization
- PL/SQL Interactive Sandbox: Oracle Live SQL environment

### Frequently Asked Questions (FAQ)

**Q: Can I use these exercises with database systems other than Oracle?**
A: Yes! Exercises 1–3 work with MySQL and PostgreSQL. Exercises 4–8 require minor syntax modifications for non-Oracle databases. Refer to the compatibility matrix in the README.

**Q: What if I make mistakes while running exercises?**
A: Use ROLLBACK to undo changes before committing. Create backup tables before testing triggers. Use DROP TABLE IF EXISTS to remove test objects safely.

**Q: How long should each exercise take?**
A: See the Learning Path section. Times are estimates; actual time depends on your experience level and understanding depth.

**Q: Can I modify the SQL files?**
A: Absolutely! Modify, experiment, and extend the queries. Learning by doing is the best approach.

**Q: Are there solutions provided?**
A: Check for a solutions branch or contact the instructor. Working through problems yourself provides better learning outcomes.

**Q: What's the difference between implicit and explicit cursors?**
A: Implicit cursors are automatic for single-row queries; explicit cursors provide fine control for multiple-row processing.

**Q: Why use normalization if it requires more joins?**
A: Normalization reduces storage, improves data integrity, and simplifies updates. Query optimization and indexing mitigate join performance costs.

### Contributing & Feedback

**How to Contribute:**
1. Fork the repository or create a feature branch
2. Make improvements (add exercises, fix bugs, enhance documentation)
3. Test all changes thoroughly
4. Write clear, descriptive commit messages
5. Submit a pull request with detailed explanation

**Types of Contributions Welcome:**
- Bug fixes and corrections
- Enhanced documentation and comments
- Additional practice exercises
- Performance optimizations
- Database compatibility improvements
- Real-world use case examples
- Translation to other languages

**Reporting Issues:**
- Use GitHub Issues to report bugs
- Include database version and error messages
- Provide minimal reproduction steps
- Attach relevant SQL excerpts

**Questions & Discussion:**
- GitHub Discussions for questions
- Include your environment details
- Be specific about what's not working
- Check existing issues before posting

---

## Final Notes

This repository serves as a comprehensive learning platform for database management fundamentals. Whether you are a student, educator, or professional seeking to refresh your database skills, these exercises provide practical, hands-on experience with industry-standard technologies.

Start with Exercise 1 and progress sequentially. Don't rush. Focus on understanding concepts rather than just completing exercises. Experiment, make mistakes, and learn from them.

Happy learning!

**Last Updated:** August 2026
**Repository Status:** Active & Maintained
