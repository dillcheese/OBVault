---
lastSync: Tue Nov 04 2025 18:02:03 GMT-0500 (Eastern Standard Time)
---
# Advanced Database Concepts

Midterm: Cheat Sheet allowed (1page)

Final: Open Book

## Other Stuff


In SQL, `%` is a wildcard character primarily used with the `LIKE` operator for pattern matching in `WHERE` clauses.

Usage with `LIKE`:

- `%` represents zero, one, or multiple characters.

For example:

- `'A%'` matches any string starting with 'A' (e.g., 'Apple', 'America').
- `'%ing'` matches any string ending with 'ing' (e.g., 'running', 'singing').
- `'%app%'` matches any string containing 'app' (e.g., 'application', 'happy').

#### Quiz 2

Use the following SELECT statement to answer the questions:

1 SELECT customer#, COUNT(*
2 FROM customers JOIN orders USING(customer#)
3 WHERE orderdate > '02-APR-09'
4 GROUP BY customer#
5 HAVING COUNT()> 2;

Which line of the SELECT statement is used to restrict groups displayed in the query results?

- **(`HAVING COUNT(*) > 2`)** → restricts **groups** after they are formed.
The `HAVING` clause is specifically used to filter groups after they have been created by the `GROUP BY` clause.

*MIN* and *MAX* function can be used on any value (number, datetime, even strings)

group functions/multi row functions/ aggregate function = used in conjunction with the `GROUP BY` clause
COUNT, SUM AVG, MAX, MIN e.g:  SELECT department, COUNT() AS num_employees  
FROM employees  
GROUP BY department;
Group functions *ignore null values* when doing calculations

A single-row function in SQL is a type of function that operates on a single row of data at a time and returns a single result for each row.
Such as: `UPPER()`, `LOWER()`, `INITCAP()`, `CONCAT()`, `SUBSTR()`, `LENGTH()`, `TRIM()`, `REPLACE()`

HAVING clause needs a condition. e.g:  HAVING COUNT(CustomerID) > 5;

#### Quiz 3 Joins


A *primary key* uniquely identifies each row within a single table, ensuring data integrity by preventing duplicate entries and serving as a fundamental reference point. 
- **Example:** In a `Customers` table, `CustomerID` would be the primary key. Each customer has a unique `CustomerID`, which identifies them within that table.
A *foreign key* is a column in one table that references the primary key of another table, creating a link between the two tables and enforcing referential integrity to maintain consistency in the relationships. 
- **Example:** In an `Orders` table, a `CustomerID` column would be a foreign key. It references the `CustomerID` (primary key) in the `Customers` table, showing which customer placed that order.

a **column qualifier** is the **table name or alias** used to identify which table a column belongs to when multiple tables are involved.
e.g: SELECT c.lastname, c.firstname, o.orderdate
FROM customers c
JOIN orders o ON c.customer# = o.customer#;


A *NATURAL JOIN* in SQL is a type of JOIN that automatically combines two or more tables based on *columns with the same name and data type* in both tables.
It implicitly determines the join condition, meaning you do not explicitly specify the columns to join on using an `ON` or `USING` clause.

Consider two tables: `Employees` with columns `EmpID`, `EmpName`, `DeptID` 
and `Departments` with columns `DeptID`, `DeptName`.

```
SELECT *  
FROM Employees NATURAL JOIN Departments;
```
This query would join the `Employees` and `Departments` tables based on the common column `DeptID`. 
The result would include all columns from both tables, with `DeptID` appearing only once.

*Equality Join:* created by matching equivalent values in each table (natural join is a equality join)
JOIN orders o ON c.customer# = o.customer#;  OR  JOIN orders USING (customer#);

*INTERSECT:* used to make certain that only the rows returned by both queries are displayed in the results
The INTERSECT operator is specifically designed to return only the rows that are **common** to the result sets of _both_ queries being combined.

| Operator      | Function                                                         |
| ------------- | ---------------------------------------------------------------- |
| **INTERSECT** | Returns only the rows that exist in **Query 1 AND Query 2**.     |
| **UNION**     | Returns all unique rows from Query 1 *OR* Query 2.               |
| **UNION ALL** | Returns all rows from Query 1 AND Query 2, including duplicates. |
| **MINUS**     | Returns rows from Query 1 that are NOT in Query 2.               |

*Cartesian Join:* results consisting of each row from the first table being replicated from every row in the second table?

*Cross Join:*  A SQL `CROSS JOIN` produces the Cartesian product of two tables. This means that every row from the first table is combined with every row from the second table. The resulting table will have a number of rows equal to the product of the number of rows in each of the original tables.
**Example:**
Consider two tables: `Customers` (with columns `CustomerID`, `Name`) and `Products` (with columns `ProductID`, `ProductName`).
If `Customers` has 3 rows and `Products` has 4 rows, a `CROSS JOIN` between them would result in a table with
3×4=123 cross 4 equals 12
3×4=12 rows, showing every customer paired with every product.

*Outer Join Operator:* Queries can use the outer join operator (+) as alternative syntax within predicates of the WHERE clause.
SELECT * FROM T1
LEFT OUTER JOIN T2 ON T1.PK1 = T2.FK1 
AND T1.PK2 = T2.FK2

SELECT * FROM T1, T2 
WHERE T1.PK1 = T2.FK1(+) 
AND T1.PK2 = T2.FK2(+)

![](data:image/gif;base64,R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw==)
**SQL Self Join:** Table is joined to itself

To find pairs of customers from the same city, excluding comparing a customer with themselves:
```
SELECT
    A.CustomerName AS Customer1,    B.CustomerName AS Customer2,    A.City
    FROM    Customers AS A
    INNER JOIN    Customers AS B
    ON    A.City = B.City AND A.CustomerID <> B.CustomerID
    ORDER BY    A.City, Customer1, Customer2;
```

SQL *set operators* combine the results of two or more `SELECT` statements into a single result set.

#### Quiz 4 Subqueries

Single-row operators are those that work with one value at a time (e.g., =, <, >, <=, >=, <>[not equal operator] ). 
Multiple-row operators are those that compare a value to a set of values (e.g., IN, ANY, ALL).

##### Single-Row Operators
- Compare **one value to one value**
- Used with simple conditions in `WHERE` or `HAVING` clauses
- Return **TRUE/FALSE** for each row

| Operator     | Meaning                  | Example                            |
| ------------ | ------------------------ | ---------------------------------- |
| `=`          | Equal to                 | `WHERE state = 'NY'`               |
| `<>` or `!=` | Not equal to             | `WHERE cost <> 20`                 |
| `<`          | Less than                | `WHERE retail < 50`                |
| `>`          | Greater than             | `WHERE pubid > 10`                 |
| `<=`         | Less than or equal to    | `WHERE discount <= 0.15`           |
| `>=`         | Greater than or equal to | `WHERE orderdate >= '01-JAN-2025'` |

##### Multiple-Row Operators
- Compare a value to a **set of values** (from a list or subquery)
- Often used with subqueries that return multiple rows

| Operator        | Meaning                                           | Example                                                                 |
| --------------- | ------------------------------------------------- | ----------------------------------------------------------------------- |
| `IN`            | Equal to **any value in the list**                | `WHERE state IN ('NY','CA','TX')`                                       |
| `ANY` or `SOME` | Compare to **any value** returned by subquery     | `WHERE cost > ANY (SELECT cost FROM books WHERE category='BUSINESS')`   |
| `ALL`           | Compare to **all values** returned by subquery    | `WHERE cost > ALL (SELECT cost FROM books WHERE category='CHILDREN')`   |
| `EXISTS`        | Returns TRUE if subquery returns at least one row | `WHERE EXISTS (SELECT 1 FROM orders o WHERE o.customer# = c.customer#)` |

#### Quiz 5: PL/SQL Intro & Block Structures


PLSQL blocks require BEGIN and END;
Basic Loop (LOOP END LOOP), General Loop (WHILE, BEGIN, END  loop)

 The `:=` operator is used for assignment. This operator assigns a value to a variable.
 *Assignment statements* are used to change the values of variables.
```
DECLARE
  v_number NUMBER;
  v_name VARCHAR2(50);
BEGIN
  -- Assigning a literal value to a number variable
  v_number := 10;

  -- Assigning a string literal to a varchar2 variable
  v_name := 'John Doe';

  -- Assigning the result of an expression
  v_number := v_number + 5;

  DBMS_OUTPUT.PUT_LINE('Number: ' || v_number);
  DBMS_OUTPUT.PUT_LINE('Name: ' || v_name);
END;
/
```

A *constant* is an identifier whose value is assigned once during its declaration and cannot be changed throughout the execution of the program. This immutability is enforced by the `CONSTANT` keyword during declaration.

A *constant declaration* in PL/SQL follows this general syntax:
```
CONSTANT_NAME CONSTANT DATATYPE := VALUE;
```
- `CONSTANT_NAME`: The name you assign to the constant.

If the EXIT WHEN clause is not included in a basic loop, then the result is an *infinite loop*

IF statements: [IF statement (PL/SQL) - IBM Documentation](https://www.ibm.com/docs/en/ias?topic=plsql-if-statement)

CASE [ expression ]

   WHEN condition_1 THEN result_1
   WHEN condition_2 THEN result_2
   WHEN condition_n THEN result_n
   ELSE result

END

`TYPE IS RECORD` statement creates records
```
DECLARE  
TYPE record_type_name IS RECORD (  
field1_name datatype [NOT NULL] [:= default_value],  
field2_name datatype [NOT NULL] [:= default_value],  
basket bb_basket.idBasket%TYPE,
-- ... more fields  
);  
BEGIN  
...  
END;
```

A record can store and handle multiple values of different data types as one unit.
A collection can store multiple values of one data type.

The PL/SQL searched `CASE` statement evaluates multiple Boolean expressions and executes the sequence of statements associated with the first condition that evaluates to `TRUE`. 

```
CASE    
	WHEN condition_1 THEN        
	statements_1    
	WHEN condition_2 THEN        
	statements_2   
	 -- ... more WHEN clauses    
	 ELSE
		else_statements
END CASE;
```
`WHEN condition_N THEN statements_N`: Each `WHEN` clause contains a `condition` (a Boolean expression) and a `statements` block. The `conditions` are *evaluated sequentially* from *top to bottom*. If a `condition` evaluates to `TRUE`, the corresponding `statements` are executed, and control passes to the next statement after the `END CASE`. Subsequent `WHEN` clauses are not evaluated.
















## Class 1 (Sept 2)
Data Definition Language (DDL)
CREATE TABLE
ALTER TABLE
DROP TABLE

Data Manipulation Language (DML)
INSERT 
UPDATE
DELETE

commit
or 
rollback

Query Language

SELECT * or col1,col5
FROM table
WHERE 
GROUP BY
HAVING
ORDER BY

SELECT col1,col2
FROM table1 JOIN table2
ON table1.fk =table2.pk

SELECT col1,col3
FROM table1
WHERE x > ( SELECT x FROM table5)



Q1: list of all employees in HR_employees where people work under either department 80 or 50 and at the same time earning less than or equal to 1000

SELECT * 
FROM HR_employees 
WHERE (department_ID = 80 OR department_ID = 50) AND salary >= 1000 


Q2: list of total number of book in COMPUTER category in JL_BOOKS table

SELECT COUNT * as computer_books
FROM JL_Books
WHERE category = 'Computer'

Q3: List of average salary for each department in HR_employees

SELECT department_id, AVG (salary) as average_salary
FROM HR_employees 
GROUP BY department_id


Exercises set 2 (Week 1)  
1.  List all employees who work in department 50, 60, or 90.  
2.  Show employees with salary between 5000 and 9000 (inclusive).  
3.  Fix the following query so it finds employees who are either in department 10 or 20 and are sales reps:  
4.  SELECT * FROM employees  
5.  WHERE department_id = 10 OR department_id = 20 AND job_id = 'SA_REP';  
6.  Find all employees whose department_id is not between 20 and 80.


## Class 2 (9/9/2025)

String data (case sensitive)

Subquery: query inside a query

Correlated subquery:  a subquery that depends on values from the outer query.

SELECT column1, column2, ...
FROM table1 outer
WHERE column1 operator
      (SELECT column
       FROM table2
       WHERE expr1 = outer.expr2);



<> not equal to (!=)
	
AND  

UNION :  used to combine the result-set of two or more `SELECT` statements.
SELECT _column_name(s)_ FROM _table1_  
UNION  
SELECT _column_name(s)_ FROM _table2_;

## Class 3 (9/16/2025)

SELECT first _ name, last _ name, salary,
NTILE(4) OVER (ORDER BY salary DESC) AS salary bucket
FROM hr_ employees;

Joins

Subqueries

## Class 4 (Sept 23)

**Intro to PL/SQL**

PL/SQL:
Stands for "procedural Language extension to SQL"
Is Oracle Corporation's standard data access language for relational databases
Seamlessly integrates procedural constructs with SQL

Provides a block structure for executable units of code.
Maintenance of code is made easier with such a well-defined structure.

Provides procedural constructs such as:
- Variables, constants, and data types
- Control structures such as conditional statements and loops. Reusable program units that are written once and executed many times

**Benefits**
Modularized program development
Integration with Oracle tools
Portability
Exception handling

![[Pasted image 20250923165704.png]]


**Rules**

![[Pasted image 20250923171431.png]]


SQL Engine
 
================

list lname and salary and department id info which belong to one particular employee  (which is 175 Hutton)  
when you get these info ,please check how much this employee makes, take a note and which department he/she  works  
based on these info  make decision and increase person salary

step 1:  
select last_name, salary, department_id from hr_employees where employee_id=175

step 2: take note of salary , last    
           sal : 8800  laname : Hutton  d id : 80                                 ===> 8850  
  
Step 3:  apply rule / logic  
if this person work for department 50 and  
                     salary is > 5000  then add 100 to existing salary and displyay new salary  
                     if salary is < 5000 then add 300  existing salary and displyay new salary  
            if this person work for department 80   
                     and   
                      salary is > 5000  then add 50 to existing salary and displyay new salary  
                     if salary is < 5000 then add 80  existing salary and displyay new salary  
  
  Step 4:      Display : Hutton   curr salary  8800    new  sal: 8850  
        ===    
  
list name and salary and department id info belong to one particular employee  (which is 134  )

step 1:  
select last_name, salary, department_id from hr_employees where employee_id=134

step 2: take note of salary , last    
           sal : 9200  laname : Rugers  d : 50    ===>    9200+100  
  
Step 3:  if this person work for department 50 and  
                     salary is > 5000  then add 100 to existing salary and displyay new salary  
                     if salary is < 5000 then add 300  existing salary and displyay new salary  
            if th is person work for department 80   
                     and   
                      salary is > 5000  then add 50 to existing salary and displyay new salary  
                     if salary is < 5000 then add 80  existing salary and displyay new salary  
  
                     Rugers    2900+100  
  
  
        Problem 1 :  Human dependent.. Someone has to be available 7/24  
        Problem 2:  human error/ mistakes  
        Problem 3:  lack of test / second pair of eye  
  
        Problem 4: time consuming


==== PL/SQL Engine  Rules:
rule 1:  every line of our program has to end with ;  
rule 2: if you are bringing some data elements from database table  use sELECT INTO  
rule 3: if you are storing info coming from database, create variable and declare them in   
DECLARE section .. variable_name   data type  
rule 4: once you use SELECT INTO variables, from there on, always use  var_xxxx  version of   
do not use column anymore  
rule 5: every section has to have END .. loop  end loop , if  end if,  begin  end
rule 6:  IF you are comparing variable equal to some number  use =  
             IF v_cur_sal =5000 THEN  
rule 7:  but, if you want to assign value to variable, or re use or re assign value  
      then use   :=   

variable Naming rules of variables:

1)Must start with a letter   
2) Can include letters or numbers  
3) Can include special characters (such as $, _, and #)  
4) name lenght of variable must be up to max 30  characters  
5) Must not include reserved words (such as SELECT , FROM , table, WHERE etc)  
6) do not use same column name as variable  
   do not do this below  
    SELECT salary INTO salary from Hr_employees where emp_id=156;

Scalar variable (basic) which can only hold one info in one cell  
   char  
   varchar  
   date  
   number  
   boolean    (TRUE  or FALSE)

##### Rules of programming:  
===================  
1)program will start with BEGIN and end with END;  
optionally you can have DECLARE before begin in case you need to open variable /container in the memory  
2) every line has to end with ;  
3) you can still use any SQL command inside BEGIN and END;  
except SELECT will require INTO keyword  
4) you can only allow to pull database table column value as part of SELECT and from there load those values to varuable and deal with variable  
5) if you have control structure such as  
IF .it has to have END IF  
LOOP it haas to have END LOOP  
6) -- makes that particular line invisible by program but developer will still see the line  
7) if you want to assign a value (initial or overwrite value ) use :=  
8) if you want to compare whether something is equal to something else =  
rules of variable naming:  
- must start with letter, it may have numbers or symbols  
- better to have prefix or \suffix  
	v_ var_  
* symbols (special char) _ # $  
* name of variable can not be more than 30  
* do not use reserved word as variable ( SELECT , FROM , WHERE, ...)  
* do not use column name as variable


======================= PL/SQL  engine =======

DECLARE  
  var_lname   varchar(25);  
  var_sal     number(8,2);       
  var_did     number(4);  
   var_new_salary   number (8,2);  
  
BEGIN

    select last_name, salary, department_id INTO var_lname, var_sal, var_did  from hr_employees where employee_id=175;
     
    IF var_did = 50 THEN  
         IF var_sal > 5000 THEN  
                  var_new_salary := var_sal +100;  
         ELSE    
               var_new_salary := var_sal +300;  
         END IF;       
    ELSIF  var_did=80 THEN  
  
       IF var_sal > 5000 THEN  
                  var_new_salary := var_sal +80;  
         ELSE    
               var_new_salary := var_sal +50;  
         END IF;       
  
    END IF;  
  
      DBMS_OUTPUT.PUT_LINE  (var_lname);  
      DBMS_OUTPUT.PUT_LINE  (var_sal);  
      DBMS_OUTPUT.PUT_LINE  (var_new_salary);  
  
END;

## Class 5 (Oct 7, Week 6)
V1 for Assignments
Group Project
Anything for Frontend

1. PL/SQL (basic foundation/rules)
2. Variable usage - definition of variable
3. Control Structures (IF THEN ELSE and LOOPS)

= is compare
:= is variable assignment


#### Nested Blocks and Control Structures
IF...
	THEN...
END IF;

IF...
	THEN...
	ELSE...
END IF;

if, then, elsif, then, end if;

best
if, then, elsif, then, else, then, endif; 


3 loop types:
Basic (does not check condition)
For 
While (checks condition at beginning)

for loop: cannot use the incrementor outside of the loop unlike the other loops.

Continue (skip a certain increment in a for loop. Continue WHEN  xx IN (10,20,30); skips 10,20 and 30 in a for loop)





## Class 6 (Oct 14 Week 7)
Before midterm
#### Composite Variables
can hold multiple types of data types unlike scalar variables

3 types of variables:
**a) Record types**
1. *exact clone of record table*

The %ROWTYPE attribute is useful when you want to retrieve a row with:  
– The SELECT * statement  
– Row-level INSERT and UPDATE statements

2. *custom record type*

TYPE example_type IS RECORD
(
	m_salary                 hr_employees.salary%TYPE,
	m_department_id   hr_employees.department_id%TYPE 
);

**b) Array / Collections?**
Key Value pairs (CAN be different data types)

An *associative array* is a PL/SQL collection with two columns:  
• Primary key of integer or string data type  
• Column of scalar or record data type

**c) Cursors**


## Class 7 (Oct 28)
Midterm

### Quiz: Procedures

Procedures can accept and return none, one, or many parameters.

PL/SQL Procedure Parameter modes: IN, OUT, or IN OUT
PL/SQL function parameters can only be IN.

**IN**: The parameter is used to pass a value **into** the subprogram. The value cannot be modified inside the subprogram. (Default mode)

**OUT**: The parameter is used to pass a value **out of** the subprogram back to the caller. The initial value is ignored, and the parameter must be assigned a new value before the subprogram exits.

**INOUT**: The parameter is used to pass an initial value **into** the subprogram, and a potentially modified value **out of** the subprogram.

**Application procedures** (or client-side code, sometimes called client-side procedures or routines) are saved within the application files or libraries (e.g., Oracle Forms, Reports, or a Java/C# application layer) that reside on the user's computer or application server (the **client-side**). These procedures execute locally or on the middle-tier application server.

**Stored procedures and functions** (Option A), **Functions** (Option B), and **Packages** (Option C) are all types of **server-side** $\text{PL/SQL}$ subprograms. They are compiled and stored within the **Oracle database instance** itself and are executed by the database server.

An application trigger performs tasks automatically when a particular application event occurs, such as when the user clicks a button on the screen

Autonomous transactions are transactions created within another transaction.
A database trigger performs tasks automatically when a DML action occurs on the table with which it is associated.

### Quiz: Cursors

`SQL%ROWCOUNT` is an implicit cursor attribute in Oracle PL/SQL that returns the number of rows affected by the most recently executed `INSERT`, `UPDATE`, or `DELETE` statement, or the number of rows returned by a `SELECT INTO` statement.

The primary purpose of the `FOR UPDATE` clause is to lock the selected rows so they can be modified with an `UPDATE ... WHERE CURRENT OF cursor_name` statement.

An **explicit cursor** in SQL, particularly within procedural extensions like PL/SQL, is a named pointer to a private SQL area used to process queries or DML statements that return or affect multiple rows. Unlike **implicit cursors**, which are automatically managed by the database for single-row operations or standard DML, explicit cursors provide developers with fine-grained control over the retrieval and processing of individual rows within a result set.

The `FETCH` statement is used to retrieve rows from a result set one at a time using a previously declared cursor. Cursors are database objects that allow for sequential processing of individual rows returned by a query, typically within stored procedures, functions, or triggers. The `FETCH` statement, when used with a cursor, moves the cursor's position and retrieves the data from the current row into specified variables.
### Quiz: Functions

A compiler hint is a request a programmer includes within his or her code that asks Oracle to modify the default processing in some manner.


## Class 8 (Nov 4)

**Cursors Cont.**
A cursor is a pointer to the private memory area allocated by the Oracle Server. It is used to handle the result set of a SELECT statement.

Cursor could be entire table, portion of a table, some columns etc.
Cursor is a memory structure (have to close when finished using)

Two types of Cursors: 
**Implicit:** Created and managed internally by the Oracle Server to process SQL statements  
**Explicit:** Declared explicitly by the programmer

**Cursor FOR LOOP**

FOR j_rec IN cursor LOOP

END LOOP;


## Class 9 ()
















