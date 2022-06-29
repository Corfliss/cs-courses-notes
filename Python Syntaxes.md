---
Zettelkasten: 2022.06.29 23:00:37 +0700
---
# What is Syntax in Python?
Syntax means the exact writing rule of the code that should be followed in order to make it run properly. Failure to do so will return a syntax error

## How to Syntax
Let's say we want to print about "Hello, world" in the screen, to do so it works like this:
```python
print("Hello, world")
```
To explain in further, we have command that says `print` that means to print it in the said program, or in the compiler. In this case, "Hello, world" is printed, as noted by the parenthesis that surrounds the sentence.

But, let's say we make a mistake and then this happen
```python
print"Hello, world")
```
This time, without open parenthesis of the program. That is why, this will return an error in the program.  A syntax error. Go ahead and try it in an online compiler :)

## Indentation in Python
Normally, when it comes to any programming language, the end of the statement in a program usually ends with semicolon (;), but as for Python, it doesn't require semicolon at all. As for the replacement, Python is using indentation to understand the program written by humans. This means, it can return error when there is an indentation missed.

## Comments with Hashtag (#)
Additionally, when programming a code, often you will find a text that starts with hashtag (#). This is the part of the code that will be ignored by the compiler, which is the reader of the program execution. But for humans, it is useful to make a note on your program so that you can understand the code better for yourself.

# Reference
https://www.w3schools.com/python/python_syntax.asp

Back to [[Programming Foundation 1]]