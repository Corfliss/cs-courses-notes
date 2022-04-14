---
Zettelkasten: 210322 205217 +0700
---
# What Is Asynchronous Programming
## From my POV
* When you can call more than one programs at any time and has no waiting time to do so. 
## From S. Clearly
* Centered around the idea of an asynchronous operation
* Some operation that is started that will completes some time later
## From Eric Vogel
* a means of parallel programming
* A unit of work runs separately from the main application thread
* Notifies the calling thread of its completion, failure or progress

## Why Asynchronous Programming
* To save more time and resources
* To eliminate inefficiency of waiting
* To reduce request congestions
* To improve code organization

# Sync vs Async
## Multitasking Ability
* Sync: Must. Done. First. Before. Others.
* Async: I can multitask of doing another thing while on a thing.

## Thread Usage
* Sync: Must. Use. One.
* Async: I can use up to the number of threads available
* Async: I also can finish a thing from a thread and ends using another

# Correlation with Concurrency
* We can use both sync and async in multi thread

# How Is It Working (in Java)?
## Callable Interface
* Runs like Runnable
* Returns objects such as integers, etc. after the process is completed
* Assign target for a lambda expression or method reference.

## Future Interface
* Representing the result of asynchronous computation
* Several method provided
	* To check whether the task is completed or canceled
	 * To wait the task completion
	 * To retrieve the result
 * When get()-ing, the program will wait until the task is completed
 * No methods to manually complete the task
 * Provide a default response given a very long time task

## CompletableFuture Interface
* A class that implements Future and CompletionStage
* Can supply a callback function that will be executed when the task is completed or error.
* The result of each task can be chained or combined
	 * The result of one task can be supplied to another task
	* We can run many parallel tasks and supply a function to combine the results of all tasks.

## Supplier Interface
* A built-in interface representing a supplier of some results/values

## Retrofit
* One of many HTTP clients for Java
* Mainly used for as HTTP client for Android
* Synchronous available
*  How it works
	* Build a Retrofit instance that target a base URL
	* Parse JSON objects into Java Objects
	* Create implementation depending on the service

# Promise
* ![[Promise Flowchart.png]]


# Reference
* CSUI slides of Advanced Programming
* Some other internet articles such as
	* [Callable Interface Documentation](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/Callable.html)
	* etc.