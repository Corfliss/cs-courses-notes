---
Zettelkasten: 280222 064625 +0700
---
# Definition
It it so big it is hard to work with.

# Examples
## Long methods
* Definition: So long it is a spaghetti
* Reason: Adding more and more without delegation
* Possible Treatment
	* Extract method
	* Replace temp with query
	* Introduce parameter object
	* Preserve whole object
	* Decompose conditional
* Payoff
	* Shorter code live longer
	* Prevent any duplicated code

## Big Class
* Definition: Class with too many variables and methods
* Reason: Relying a class to do many things at once.
* PossibleTreatment
	* Extract class
	* Extract subclass
	* Extract interface
* Payoff
	* More simpler classes
	* Avoiding possibility of code duplication

## Primitive Obsession 
* Definition: Using primitives variables rather than an object.
* Reason: Oversimplifying data storing
* Possible Treatment
	* Replace data value with object
	* Introduce parameter object
	* Preserve whole object
	* Replace type code with class
	* Replace type code with subclasses
	* Replace type code with state/strategy
	* Replace array with object
* Payoff
	* More flexible codes
	* Better understandibility and organization of code
	* Easier finding of duplicated code.

## Long Parameter List
* Definition: Too many parameters
* Reason: Byproduct to make class independent to each other
* Possbile treatment
	* Replace parameter with method call
	* Preserve whole object
	* Introduce parameter object
* Payoff
	* More readable, shorter codes
	* May reveal previously unnoticed duplicate code.

## Data Clumps
* Definition: Identical group of variables that should be turned into a class.
* Reason: Poor program structure ("copypasta programming")
* Treatment
	* Extract class
	* Introduce parameter objects
	* Preserve whole objects
* Payoff
	* Improves understanding and organization of the code
	* Reduces code size

# Reference
[Catalog of Refactoring by Refactoring Guru](https://refactoring.guru/refactoring/catalog)