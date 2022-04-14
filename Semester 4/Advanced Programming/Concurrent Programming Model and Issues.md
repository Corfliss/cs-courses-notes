# Introduction
Execution flow and there are no other flows happening at the same time. So then that was the assumption that was implicitly taught in foundation of programming. In this concurrent programming.

You have program running at the same time. So that is the overview that can have multiple execution tool and each has their own instruction executed.

# Attribution
Based on Chapter 19&20 from Software Construction on MIT OCW 6.005.
Loosely combined materials from Introduction to concurrent programming book.

# Learning objective
know models forconcurrent programming like share memory and message passing. Know distinction between threads and processes.

# Definition of Concurrency
"Mulltiple computations that are happening at the same time" (MIT OCW, 2016)

# Concurrency & Parallelism
* Concurrent activities are not necessarily always executed simultaneously
	 * Simultaneous execution of multiple activities → parallelism
* Example?

# Motivation (AKA Reason to Learn)
* Separation of (processing) concerns
	* E.g. Game engine (graphics, network, AI, sound, etc)
* Application responsiveness
	* E.g. Web server, GU-based application
* It is natural -> How human does things

# Concurrent Programming Models
## Shared Memory Model
* Concurrent modules interact by reading and writing shared object in memory
* Example
	* Multipurpose processor (or cores) -> Share physical memory
	* Mutliple programs -> Share common filesystem
	* Multiple threads -> Share the same Java objects

## Message Passing Model
* Concurrent modules interact by sending messages to each other through a communication channel
* Example
	* Computers in a network
	* Client-server (Web)
	* Program via pipe e.g ls | tail | grep foo
* Three levels of concurrency
	* Low
		* Explicit use of atomic operations
		* Usually used by library writers or system programmers
	* Medium
		* Most programming languages provide support in this level
		* Provide synchronization mechanism, e.g. sempahore, lock
		* Used by application developers
	* High
		* Atomic operations and synchronization are abstracted via libraries
		* Used by application developers

# Threads and Processes
## Process
* An instance of running program that is isolated from other processes on the same machine
* Has its own private section of the machine's memory
* Example: see Task Manager (Windows) or ps/top (Unix)

## Thread
* A locus of control inside a running program
	* Represents thread/flow of program execution
* Running in a process -> Share process'memory space
* Thread may have a thread-local memory
* Example: basic Java Swing GUI appication
	* Two threads: main thread and even dispatch thread.

### Single Thread, Single Core
* Thread processing have no time slicing
## Double Thread, Single Core
* Time-slicing/Interleaving
* Issue will be a long-running thread
	* Certain operation took most of computationn time -> App become not responsive, or freeze on GUI-based app.
### Two Threads, Two Cores
* No time-slicing, just a thread each for each core.
* Three threads, two cores
* Will have another time-slicing/interleaving

### Process(es) Scheduling
* Processes also "sliced" in CPU
	* Handled by OS
* Similar mechanisms with thread time-slicing
* Discussed in OS course

### Threading in Java
#### java.lang.Thread
![[java.lang.Thread.png]]

##### java.lang.Runnable
![[java.lang.Runnable.png]]

# Shared Memory Model
#ongoing 