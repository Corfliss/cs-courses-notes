---
Zettelkasten: 020222 211006 +0700
---

# What is Object, Anway?
Most dictionaries said a tangible material thing. But in computer science, especially in object-oriented programming, it is ==an object is an instance of a thing tha typically represents a real world object and have all the same type of characteristics (properties), behaviors (methods), and states (data)==[^1]

# What is OOAD?
There is a difference between Object-oriented Analysis (OOA), and Object-oriented Design (OOD). ==In a nutshell, OOA is more to the technical side of the object oriented software development, like the what. While design is more about the plan for the software itself Like the how.==

# OOA vs OOD
Here is what is OOA and OOD

## What is OOA in OOAD?
In short it is an iterative way of analysis for below:[^1]
* Takes place during development life cycle.
* Aims to model the **functional** requirements of the software.
* Completely independent of any potential requirements.

## What is OOD in OOAD?
Extension of OOA with considerations to constraints like budget, time, hardware capabilities, etc.

### Layers of OOD
Futhtermore, OOD is having some layers for it. Which include as below.[^2]
1. The subsystem layer, represents the ==availability of the software==to achieve user requirements.
2. The class and objects layer, represents the ==class hierarchies== that enables system to do generalization and specialization of the program. Like every object.
3. The message layer, represents the design details on how each ==objects communicate== and establish internal and external interfaces for the system.
4. The responsbilities layer, ==data structure and algorithm design== for all the attributes and operations for each objects.

# Origin Story
In software development, there is a life cycle of it. Its called Software Development Life Cycle (SDLC), it can ve various such as waterfall method or iterative model. But mostly it can be break down into some stages such as requirements, planning, design, coding, testing, deployment, and maintenance. However, it is quite strict and sequential, unable to make adaptive change for when the test and feedback stray away from the planning. Hence, OOAD was born, this includes Unified Modeling Language (UML) and Rational Unified Process (RUP).[^1]

# Advantages vs Disadvantages
## Advantages of OOAD
* Encourage encapsulation
* Easy to understand

## Disadvantages of OOAD
* In procedural programming paradigm, it is not suitable.
* Too complex for simple applications.

# Further reading:
* [Waterfall Model](https://airbrake.io/blog/sdlc/waterfall-model)
* [Software Development Life Cycle (SDLC)](https://www.tutorialspoint.com/sdlc/sdlc_overview.htm)

Back to [[Advanced Programming]]

# Reference:

[^1]: Banks, F. (2020, November 11). _What is Object-Oriented Analysis and Design and How To Use It_. Airbrake. Retrieved February 2, 2022, from https://airbrake.io/blog/design-patterns/object-oriented-analysis-and-design
[^2]: GeeksforGeeks. (2020, April 7). _Object Oriented Analysis and Design_. Retrieved February 2, 2022, from https://www.geeksforgeeks.org/object-oriented-analysis-and-design/