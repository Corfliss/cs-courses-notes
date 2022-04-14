---
Zettelkasten: 080222 035447 +0700
---
# Why Software Testing?
* To be informed if we are making mistakes
* To make sure the program is used the way it suppose to do

# Kinds of Errors
## Syntax error
* The usual of fault in language use
* The usual got caught by the toolchain
### Example Without Syntax Error: 
```Python
def marco():
	print("Polo")
	print("Bolong") 
```
### Example With Syntax Error
```Python
def marco():
	print("Polo")
  print("Bolong") // Identation needed
```

## Semantics Error
* Correct syntax, but can't do what it asked to do
### Example With Semantics Error
```Python
def take(something):
	obj = something[1]
	obj.status = "OK"
	return obj
```

## Design Error
	* Broad term
	* Neither syntax or semantics error
### Example With Design Error
```Python
def cubeSqrt(num):
	return num ** -3
```

# How of Testing

## How Testing Helps
* Avoiding Both semantcis and design errors
* More confidence in quality of code

## How to Test
### Verification and Validation
Accroding to IEEE-STD-610

#### Verification
* Proving meets all specified requirements
* During a particular stage of its development
* "Am I building the product right?"

#### Validation
* End product stakeholder's true needs met
* End product stakeholder's expecatione met
* "Am I building the right product?"

### Post vs Pre
#### Post
* Code first, test later
* Pesonally, I think this is worse

#### Pre
* Test first, code later
* AKA Test-driven Development (TDD)
* Personally, I think this is better

### Unit and Function Test 
#forlater Basically, what we learned in Platfrom-based Programming course (coming soon to the notes)

#### Unit Test
* White box test 
*  Black box test
* Smallest, testable, part of the software
	* Function, method, class
* Verify the correctness of individual unit
* Independently tested
* If tested with other unit test
	* Integration test

#### Functionn Test
* Black box test
* Ensure everything works as a whole
* User's POV testing

# What Aspect to Test

## **Correctness**
* Using mathematical proof
	* In discrete maths
	* Formal methods
* Using test cases
	* More accessible than the first.

### Writing Test Cases
* Success and alternative scenario(s)
	* Test the unit under conditions
	* Perfrom each of the responsbility
	* Can be sucessful or alternative
* Error conditions (including exceptions)
* Boundary/edge cases

### Issues in Testing
* Coverage
	* Exhaustive testing on all possible values is infeasible
* Method
	* Unstructured, trial and error approach in determining test cases
* Random or statistical testing
	* Real world physical testing does not work in software

### Input Space Partitioning
* A modeling of an unit
* Disjoint and complete, like puzzle pieces
* Pick values from each partitions to form test cases
## Resources
## Resposiveness

# Test First Programming
Write the tests before writing real implementation code.



#ongoing 

