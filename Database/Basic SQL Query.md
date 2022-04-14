---
Zettelkasten: 240322 151358 +0700
---
# `SELECT` Statement
## Basic Retrieval Queries
* SQL allows a table (relation) to have two or more tuples that are identical in all their attribute values
* Different with formal relational model
* Use contstraint on DDL
## Example
```
SELECT <ATTRIBUTE_LIST>
FROM <TABLE_LIST>
WHERE <CONDITION>;
```
* Logical comparison operators:
* = (equal to)
* < (less than)
* <= (less than or equal to)
* > (more than)
* >= (more thann or equal to)
* <> not equal

## Cartesian Product (Cross Product)
* Denoted by 'X' operator
* Operation that applied on two relation
* Produces a new element by
	* combining every tuple from one relation
	* with every tuple form the other relation

## Join
* Combine related tuples from two relations into single "longer" tuples
* General join condition of the form
* [Condition] AND [Condition] AND ...
	* Tuples that satisfy the join condition will be combined
	* Join condiiton(s) is define in the WHERE clause
# Aliases
## Ambiguous Attribute Names
* Same name can be used for two (or more) attributes
	* As long as the attributes are in different relations
	* Must qualify the attribute name with the relation name to prevent ambiguity

### Example
```
SELECT Fname, EMPLOYEE.Name, Address
FROM EMPLOYEE, DEPARTMENT
WHERE DEPARTMENT.Name = 'Research' AND DEPARTMENT.Dnumber=EMPLOYEE.Dnumber;
```

* Some queries need to refer to the same relation twice, so aliases are given to the relation name

### Example
```
SELECT E.Fname, E.Lname, S.Fname, S.Lname
FROM EMPLOYEE AS E, EMPLOYEE AS S
WHERE E.Super_ssn=S.Ssn;
```

# `WHERE` Clause
## Unspecified WHERE Clause
* A missing WHERE- clause indicate no condition
* All tuples of the relations in the FROM-clause are selected.
### Example
```
SELECT Ssn
FROM EMPLOYEE;
```

## Use of Asterisk
* Specify an asterisk (*):
* Retrieve all the attribute values of the selected tuples

### Example
```
SELECT *
FROM EMPLOYEE
WHERE Dno=5;
```

## Tables as Sets in SQL
### DISTINCT
* SQL does not automatically eliminate duplicate tuples in query results
	* Use the keyword DISTINCT in the SELECT clause
	* Only distinct tuples should remain in the result

#### Example
```
SELECT DISTINCT Salary
FROM EMPLOYEE;
```

### SET Operations
* `UNION EXCEPT` (difference), `INTERSECT` Duplicate tuples are eliminated
* Corresponding multiset operations
	* `UNION ALL`
	* `EXCEPT ALL`
	* `INTERSECT ALL`

#### Example
```
(SELECT DISTINCT Pnumber
FROM PROJECT, DEPARTMENT, EMPLOYEE
WHERE Dnum=Dnumber AND Mgr_ssn=Ssn AND Lname='Smith')
UNION
(SELECT DISTINCT Pnumber
FROM PROJECT, WORKS_ON, EMPLOYEE
WHERE Pnumber=Pno AND Essn=Ssn AND Lname='Smith');
```

## Substring Pattern Matching and Arithmetic Operators
### `LIKE` Comparison Operator
* Used for string pattern matching
* % replaces an arbitrary number of zero of more characters
* Underscore (\_) replaces a single character

### Standard Arithmetic Operators
* Addition (+),
* Subtraction (-),
* Multiplication (*)
* Division (/)

### `BETWEEN` Comparison Operator

## Ordering of Query Results
### `ORDER BY` Clause
* Keyword DESC to see descending order of values
* Keyword ASC to see ascendding order of values

#### Example
```
SELECT <ATTRIBUTE_LIST>
FROM <TABLE_LIST>
WHERE <CONDITION>
ORDER BY <ATTRIBUTE_LIST>;
```

