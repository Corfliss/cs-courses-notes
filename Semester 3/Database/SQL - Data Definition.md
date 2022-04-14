---
Zettelkasten: 180322 100820 +0700
---
# SQL Data Definition and Data Types
## Basic SQL
* Shorts for Structured Query Language
* Considered one of the major reasons for the commercial success of relational database
* Characteristics
	* Standardized - Many new feature over time
	* Interactive - Via GUI, prompt or embedded
	* Declarative - Based on relational algebra

## SQL DDL and DML
### DDL (Data Definition Language)
Defining the relational schema - relations, attributes, domain, the metadata. This includes:
* CREATE table
* ALTER table
* DROP table

### DML (Data Manipulation Language)
Defining the queris against the schema. Such as
* SELECT
* INSERT
* UPDATE
* DELETE

## Domain
* It is possible to specify data type directly
* Easier to change the data type for a domain that is used by numerous attributes
* Improves schema readability

## Schema
### Characteristics
* Group together tables and other constructs that belongs to the same database
* Identified by a schema name
* Includes an authorization identifier and descriptors for each elements

### Create/Drop a Schema
#### Create Schema
* Using `CREATE SCHEMA COMPANY`
	* Create a schema of company
	* Tables can now be created and added to schema

#### Dropping a Schema
* Using `DROP SCHEMA COMPANY RESTRICT`
	* Drop operation fails if the schema is not empty
* Using `DROP SCHEMA COMPANY CASCADE`
	* Drop operation removes everything in the schema

## Data Types in SQL
### Numeric
* Integer `INT`
* Arbitrary precision numbers `NUMERIC`
* Floating-point numbers `FLOAT`

### Character-string
* Fixed length `CHAR(n)`
* Variable-length with limit `VARCHAR(n)`
* Variable unlimited length `TEXT`

### Bit-string
* Fixed length `BIT(n)`
* Varying length `BIT VARYING(n)`
* Varying length `BIT VARYING(n)`

#### Boolean Data Types
* `TRUE` or `FALSE` or `NULL`

### Date Data Types
* Ten positions
* Components are YEAR, MONTH, and DAY in the form YYYY-MM-DD

### Timestamp Data Types
* Includes the DATE and TIME fields
* Plus a minimum of six positions for decimal fractions of seconds
* Optional WITH TIME ZONE qualifier

### Interval Data Types
Specifies a relative value that can be used to increment or decrement an absolute value of a date, time, or timestamp

## Relation in SQL
### Base relations
* Relation and its tuples are actually created and stored as a file
by the DBMS

### Virtual relations
* May or may not correspond to an actual physical file

## Create a Table
### Characteristics
* Specify a new relation
* Provide name, attributes, and initial constraint (data types)
* A constraint NOT NULL may be specified on an attribute
* We may specify primary key and foreign keys

### Foreign Key
* Some foreign keys may cause errors
	* Circular references
	* Foreign key which refers to the table itself


### `ALTER TABLE`
* add an attribute to one of the base relations
* The new attribute will have NULLs in all the tuples of the relation right after the command is executed

### `DROP TABLE`
* Remove a relation (base table) and its definition
* Relation can no longer be used in queries, updates, or any other
commands since its description no longer exists

# Specifying Constraint in SQL
### Definition
* Data types are used to limit the data to be stored in a table
* There are still many constraint to be handle
	* Key constraints
	* Referential Integrity Constraints
* Other constraints, ex: product price should only accept positive values
* SQL allows us to define constraints through DDL
	* An error is raised when a constraint is violated

### Constraints
#### `CHECK`
* Most generic constraint type
* Specify that the value in a certain column must satisfy a particular condition
* Clarifies error messages and allow changes to the constraint
* Can be dropped or replaced with another constraint

#### `NOT NULL`
* Constraint NOT NULL may be specified for a particular attribute
* Implicitly specified for primary keys

#### `UNIQUE`
* Ensure that the data in a column is unique with respect to all the rows in the table

### Value
#### Primary Key
* Combination between unique constraint and NOT NULL constraint

#### Foreign Key
* Referential integrity
	* values in a table must match the values appearing on the other table

#### Default Values
* An attribute can be assigne with default value
* The value will be created when a new row inserted
* No value is specified for that attribute
* If no default value is declared explicityly, the default value is NULL

# Modification Data Statements(`INSERT, DELETE, UPDATE`)
## `INSERT`
* Used to add one ormore tuples to a relation (table)
* Attribute values should be listed in the same order as the attributes were specified in the `CREATE TABLE` command
* Another variation of INSERT allows insertion of multiple tuples resulting from a query into a relation

## `DELETE`
* Removes tuples from a relation
* Includes a WHERE clause to select the tuples to be deleted

## `UPDATE`
* Modify attribute values of one or more selected tuples
* Additional SET clause in the UPDATE command
	* Specifies attributes to be modified and new values