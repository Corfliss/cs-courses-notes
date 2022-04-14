---
Zettelkasten: 310322 100450 +0700
---
# Data Models
* A set of concepts to describe the structure of a database
* Certain constraints that the database should obey.
## Operation
* Operations for specifying database retrievals and updates
* By referring to the concepts of the data model

## Categories of Data Models
### Conceptual (High-level, Semantic)
* Provide concepts that are close to the way many users perceive data
*  Example: entity, attribute, relationship among entities

### Physical (Low-level, Internal)
* Provide concepts that describe details of how data is stored in the computer
* Example: tree, graph

### Implementation (Representational)
 * Provide concepts that fall between the above two
 * Balancing user views with some computer storage details
 * Example: relational, network or hierarchical data model

## History of Data Models
### History of Network Model
* The first one to be implemented by Honeywell in 1964-65 (IDS System)
* Adopted heavily due to the support by CODASYL (CODASYL - DBTG report of 1971).
* Later implemented in a large variety of systems 
	* IDMS (Cullinet - now CA)
	* DMS 1100 (Unisys)
	* IMAGE (H.P.)
	* VAX -DBMS (Digital Equipment Corp.).
* Data in a network in terms of interdependencies connections among data items
* Graphs
### Hierarchical Data Model
* Implemented in a joint effort by IBM and North American Rockwell (1965)
* Resulted in the IMS family of systems, the most popular model
* Other system based on this model: System 2k (SAS inc.)
* Data in hierarchies in terms of interdependencies and connections among data items
* Tree

### Relational Model
* Proposed in 1970 by E.F. Codd (IBM),
* First commercial system in 1981-82.
* Now in several commercial products
	* DB2
	* ORACLE
	* SQL Server
	* SYBASE
	* INFORMIX

### Object-oriented Data Model
* Several models have been proposed for implementing in a database system.
* One set comprises models of persistent OO Programming Languages such as 
	* C++(e.g., in OBJECTSTORE or VERSANT)
	* Smalltalk (e.g., in GEMSTONE).
* Additional sytems like
	* O2, ORION (at MCC - then ITASCA)
	* IRIS (at H.P.- used in Open OODB)

### Object Relational Model
* Most Recent Trend
* Started with Informix Universal Server
* Exemplified in the latest versions of Oracle-10g, DB2, and SQL Server etc. systems

# Schema
## Database Schema
* The description of a database
* Includes descriptions of the database structure
* Includes the constraints that should hold on the database

## Schema Diagram
* A diagrammatic display of (some aspects of) a database schema

## Schema Construct
* A component of the schema or an object within the schema
* e.g.: STUDENT, COURSE

Database State/Snapshot
* The actual data stored in a database at a particular moment in time
* Also called the current set of occurrences/instances

## Three-Schema Architecture
# DBMS Component
# DBMS Architecture

