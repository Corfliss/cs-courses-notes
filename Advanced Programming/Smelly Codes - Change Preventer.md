---
Zettelkasten: 280222 072558 +0700
---
# Definition
You make a change in a code, the other parts of the code must be changed too and making it more complicated.

# Example
## Divergent Change
* Definition: When you make too many changes in a class.
* Reason: Poor program structure or "copypasta programming"
* Possible Treatement
	* Extract class
	* Extract superclass
	* Extract subclass
* Payoff:
	* Improves code organization, as usual
	* Reduces code duplication
	* Simplifies support

## Paralle Inheritance Hierarchies
* Definition: The urge to make a subclass of another class
* Reason: New addition to class, making it harder to maintain
* Treatment
	* Move method
	* Move field
* Payoff
	* Reduces code duplication
	* Improve organization of code.

## Shotgun Surgery
* Definition: A modification requires many changes in many different classes.
* Reason: A single responsibility has been split up among a large number of classes.
* Treatment
	* Move method
	* Move field
	* Inline class
* Payoff
	* Better organization
	* Less code duplication
	* Easier maintenance

# Reference
[Catalog of Refactoring by Refactoring Guru](https://refactoring.guru/refactoring/catalog)
