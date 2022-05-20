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
## Definition
### Simple
* Let A, B be sets of attributes
* A → B equals A functionally determines B
* Whenever two tuples agree on A then they agree on B.

### Advanced
* Given attribute sets A={A1,...,Am} and B = {B1,...,Bn} in R,
* The functional dependency A → B on R holds if for any ti ,tj in R:
* if ti[A1] = tj[A1] AND ti[A2]=tj[A2] AND ... AND ti [Am] = tj [Am] :
	* ti[B1] = tj[B1] AND ti [B2]=tj [B2] AND ... AND ti[Bn] = tj [Bn]

## Determining Functional Dependency Using Armstrong's Rules:
### Inference Rules
1. Reflexive: If {X ⊇ Y} then X → Y
2. Augmentation: If {X → Y} |= XZ → YZ
3. Transitive: If {X→Y, Y→Z} |= X → Z

### Derived Inference Rule
1. Decomposition: If {X→ YZ} |= X → Y
2. Additive (Union): If {X→ Y, X→ Z} |= X → YZ
3. Pseudotransitive: If {X→ Y, WY→ Z} |= WX → Z

### Example
#### Provided FDs
1. {Name} → {Color}
2. {Category} → {Department}
3. {Color, Category} → {Price}

#### Inferred FDs and rule used
1. {Name, Category} → {Name} | Reflexive
2. {Name, Category} → {Color} | Transitive
3. {Name, Category} → {Category} | Reflexive
4. {Name, Category → {Color, Category} | Union
5. {Name, Category} -> {Price} | Transitive

## Closure (Penutup)

# Normalization Based on Primary Key
# General Normal Form
# Functional Dependency