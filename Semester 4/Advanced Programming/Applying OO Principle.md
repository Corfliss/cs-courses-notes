---
Zettelkasten: 020222 220629 +0700
---
# Get to Know with OO Principle
As far as I know, OO Principle has 4 principle:
- Abstraction
- Polymorphism
- Inheritance
- Encapsulation

So, let's see what people say about the OO principle application.

Spoiler alert: I, uhh, I kinda forgot the basic foundation of which one should be explained first, it's all in reversed.

# The Four Basic Concepts of OOP 
Initially, I am looking for the difference between OO Principle and OO Programming, and I think both are used interchangeably. So, let's use OOP for OO Programming for now. And I use and article from Kyle Herrity.[^1]

## Abstraction
### Understanding
To put it simple, abstraction is about treating an object as something that works well like a "black box", where you don't know how it is working from the inside, you just know it is working. For example, Let's say there is a class called Car to represent a car. And there is a method call accelerate() and brake() to accelerate and brake respectively. You don't know how it works internally, but you just know that it just works.

### In Java
Data abstraction means to hide certain details and showing only essentials information to the user

There is a keyword named `abstract` in Java means two things, but both are about non-access modifier.
* Abstract class: classes that cannot be used to create objects
* Abstract method: can only be used in an abstract class and it does not have a body, because it is inherited[^2]

#### Example Code: MainAbs.java[^2]
```java
// Make an abstract class about class animal that has sound and sleep behavior
abstract class Animal {
  public abstract void animalSound();  // Abstract method
  public void eatSpaghetti() {         // Regular body
    System.out.println("Yum");
  }
}

// Animal myObj = new Animal(); -> will generate an error

class Cow extends Animal {             // Make a subclass first using extends
	public void animalSound()          // The method will be accessible by Main class
	System.out.println("Nyeh heh heh heh heh")   // Don't ask why nyeh heh heh.
}

//Main regular class
class MainAbs {
	public static void main(String[] args) {
		Cow Papyrus = new Cow();        // Create a cow object named Papyrus
		Papyrus.animalSound();          // Will return "Nyeh heh heh heh heh"
		Papyrus.eatSpaghetti();         // Papyrus' favorite.
	}
}

// Don't ask why I put Papyrus in my code. Nyeh heh heh heh heh.
```

## Polymorphism
### Understanding
Polymorphism is about overriding a method of a subclass from its class. For example, if there is a class called Tree, then there is a class called BananaTree and CoconutTree. Tree has a method called ProduceFruit(), then BananaTree can override it with ProduceBananaFruit() and CoconutTree with ProduceCoconutFruit().

### In Java
#### Example Code: MainPol.java[^3]
```java
// Make a class about animal again
class Weapon {
	public void WeaponSound() {
		System.out.println("The sound of poggers of FPS");
	}
}

class Shotgun extends Weapon {
	public void WeaponSound() {
		System.out.println("Bzzah");
	}
}

class Minigun extends Weapon {
	public oid WeaponSound() {
		System.out.println("Brrrrrrrrrrrrrrrrrr");
	}	
}

class MainPol {
	public static void main(String[] args) {
		Weapon gun = new Weapon();
		Weapon spas12 = new Shotgun();
		Weapon gatling = new Minigun();
		gun.WeaponSound();                    // "Will return 
											     // "The sound of poggers of FPS"
		spas12.WeaponSound();                 // Will return "Bzzah"
		gatling.WeaponSound();                // Will return "Brrrrrrrrrrrrrrrrrr"
	}
}
```

## Inheritance
### Understanding
(I should've explain inheritance first before polymorphism.)
Inheritance is about the relation between a class with another class, and the relation of this is like a "IS A" relation. For example, if there is a class called Family, then there is a subclass of Father and Child. Father "IS A" Family, and Child "IS A" Family.

### In Java
#### Example Code: MainInh.java[^4]
```java
class Vehicle {
	protected String brand = "Toyota"    // Vehicle Attribute
	public void honk();                  // Vehicle method
		System.out.println("AAAAAAAAAAAAAAAAAAAA")
}

class Car extends Vehicle {
	private String modelName = "Supra";    // Car attribute
	public static void main(String[] args) {
		Car aCar = new Car                 // Make aCar object
		aCar.honk();                       // Honk the car
		System.out.println(aCar.brand+" "+aCar.modelName); // Will out Toyota Supra
	}
}
```


## Encapsulation
### Understanding
This is related with the security of the code. So, when there is a class, it should be encapsulated so that only important methods that can only access it for interfacing.
When a class does not allow calling code access to its private date directly, it can be say that it is well encapsulated. For example: If there is a data called socialSecurityNumber inside a Customer class and a method called bankTransaction() on another Class, let's say Transaction, socialSecurityNumber is encapsulated so that no method that can access class except bankTransaction().

### In Java
#### Example Code: MainEnc.java[^5]
```java
// Spoilers:  taken directly from the w3School webiste
public class Main {
  public static void main(String[] args) {
    Person myObj = new Person();
    myObj.setName("John"); // Set the value of the name variable to "John"
    System.out.println(myObj.getName());
  }
}

// Outputs "John"
```

# Reference

[^1]: Herrity, K. (2021, October 6). _What Is Object-Oriented Programming? The Four Basic Concepts of OOP_. Indeed Career Guide. Retrieved February 2, 2022, from https://www.indeed.com/career-advice/career-development/what-is-object-oriented-programming
[^2]: W3School. (n.d.). _Java Abstraction_. Retrieved February 2, 2022, from https://www.w3schools.com/java/java_abstract.asp
[^3]: W3School. (n.d.-b). _Java Polymorphism_. Retrieved February 3, 2022, from https://www.w3schools.com/java/java_polymorphism.asp
[^4]: W3School. (n.d.-b). _Java Inheritance (Subclass and Superclass)_. Retrieved February 3, 2022, from https://www.w3schools.com/java/java_inheritance.asp
[^5]: W3School. (n.d.-b). _Java Encapsulation and Getters and Setters_. Retrieved February 3, 2022, from https://www.w3schools.com/java/java_encapsulation.asp