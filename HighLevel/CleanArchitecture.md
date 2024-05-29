# Introduction
Architecture represents the significant design decisions that shape a system, where 
significant is measured by the cost of change. - Grady Booch
A good architectuer comes from understanding it more as a journey than a destination, more as
a process of enquiry than a frozen artifact.
Architecture rules are the same across systems from different domains.
The goal of software architecture is to minimize the human resources required to build and
maintain a system. If the effort is low and stays low, the design is good. If the effort grows,
the system is bad. 
High level decisions and low level details are intertwined. 
The only way to go fast is to go well.
Software should be easy to change, that's why it's called soft. If it's hard to change, then it's called hardware.
There are four aspects:
1. Urgent and Important
2. Not urgent and Important
3. Urgent and Non important
4. Not urgent and not important

Business managers tend to think classify tasks in third block as tasks in first block. Architecture is always important.
Development teams need to guard the architecture. 

# Paradigm Overview
Three paradigms: structured, object oriented and functional.
Each paradigms takes power away from the programmers. They influence architecture. 

## Structured programming
Dijkstra combined control structures with sequential execution. Sequential statements could be proved correct through simple enumeration similar to mathematical proof. Unrestrained use of goto leads to a program that cannot be proved correct. 
Structured programming allows modules to be recursively decomposed into provable units leading to decomposition of functional blocks. 

Testing shows the presence, not absense of bugs. That being said, you could use tests to prove a (decomposed) program incorrect. Software architecture strives to define modules/components that are easily falsifiable.

## Object Oriented Programming
One advantages of OO is encapsulation but encapsulation could be achieved with C already. Inheritance too could be achieved in C with a bit of trickery but multiple inheritance 
could turn out to be more complex. Polymorphism enables dependency inversion and any source code dependency anywhere in the code base could be inverted. This enables absolute
control of all source code dependencies int the system. Each component in the system could be deployed independently. This enables plugin architecture decoupling low level modules
and high level modules. 

## Functional programming
