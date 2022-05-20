---
Zettelkasten: 2022.05.20 09:35:49 +0700
---
# Informal Guide to Make Relational Database
## Guide 1: Regarding Relation Attributes Semantics
* Every tuple in a relation should represents one entity or relationship instance
* schema needs to be designed in order to be easily explained by relations.
* Don't merge different entities.
* Only foreign key that refers to other relations.
* Entity attributes and relationships should be separated

## Guide 2: Regarding Duplicate Data and Update Anomaly
* Redundant information makes waste of storage and potentially cause update anomaly
* Please don't save joined relation, as it can cause update anomaly.
* Update anomaly includes
	* Insertion anomaly
	* Deletion anomaly
	* Modification anomaly
* Try to make an anomaly-free schema.
* If there is no option for anomaly-free, it needs to be recorded and handled by application. 

## Guide 3: Regarding NULL Value
* Storage waste in physical level
* Make problems when joining or aggregating
* Cannot be determined the cause of NULL
* Relations should be designed with less NULL.

## Guide 4: Regarding Spurious Tuple
* Sometimes when decomposing relation or joining it there are tow things:
	* Will the decomposition makes the data gone?
	* Will the joining makes data overload (that doesn't exists)?
* Relation should be designed to fulfill lossless join condition
* No spurious tuples that is a result of natural join relation
* Avoid relation that has matching attribute apart from PK and FK

# Functional Dependency
# Normalization Based on Primary Key
# General Normal Form
# Functional Dependency