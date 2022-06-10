---
Zettelkasten: 240122 040126 +0700
---
# What is Python?
In short, Python is an interpreted language.

Long answer, Python is looking each of the instruction, one at a time, and turns that instruction to something that can be run, or in other way to say it: executed. You can either put your code directly to this Python interpreter, or you can just import that program to your storage and then Python will execute it one by one.

# Example
Take a look at this example:

```py
# A program for addition

# Step 1: Ask for the numbers
str1 = input("Enter your first number: ")
str2 = input("Enter your second number: ")

# Step 2: Change the data type
int1 = int(str1)
int2 = int(str2)

# Step 3: Apply the addition
sum = int1 + int2

# Step 4: Print out the result
print("The sum is " + sum)
```

This is basically an addition program. In here, the program will ask for an input with a request message twice. Then store it in a variable called str1 and str2 respectively. Then, since the variable is a string type, you will find in step 2 another variable turns a string into an integer, which later summed up in step 3 with the variable sum. Lastly, to print it in the display using combination of "The sum is" and the number added.

**Why Python?**
In short, again: It has simple and familiar syntaxes. Perfect for beginners. So for now, this course notes will be using Python a lot.

Back to [[Programming Foundation 1]]