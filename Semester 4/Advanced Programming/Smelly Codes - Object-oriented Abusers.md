---
Zettelkasten: 280222 064621 +0700
---
# Definition
Not using OOP principles properly.

# Examples
## Alternative Classes with Different Interfaces
* Definition: Identical function, different name
* Reason: the programmer don't know the interfaces that being made already existed
* Possible treatment
	* Rename methods
	* Move methods
	* Add parameter
	* Parameterize methods
	* Extract superclass
	* Delete one of the classes
* Payoff 
	* Get rid of unnecessary duplicated code
	* Code becomes more readable and understandable.

## Refused Bequest
* Definition: The subclass is a little bit... off.
* Reason: Making a subclass that completely different with the superclass
* Treatment:
	* Replace inheritance with delegation
	* Extract superclass
* Payoff: Improve code clarity and organization

## Switch Statements
* Definition: complext switch or if statements
* Reason: Fewer switches.
* Treatment:
	* Extract method
	* Move method
	* Replace type code with subclasses
	* Replace type doe with state/strategy
* Payoff: Improve code organization

## Temporary Field
* Definition: Temporary values are rarely needed.
* Reason: Shortcut of programming by making temporary variables for solving large amount of inputs.
* Possible treatment
	* Extract class
	* Replace method with method object
	* Introduce null object
* Payoff: Better code clarity and organization

# Reference
[Catalog of Refactoring by Refactoring Guru](https://refactoring.guru/refactoring/catalog)