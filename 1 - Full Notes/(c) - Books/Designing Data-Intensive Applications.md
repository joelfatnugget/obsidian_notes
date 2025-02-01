2025-01-29 11:46
Status: [[System Design]] [[Reliability]] [[Maintainability]] [[Scalability]]
Tags:



## Part 1: Foundations of Data Systems
### Chapter 1: Reliability, Scalability and Maintainability
There are 3 concerns that are most important in most software systems:
1. Reliability
2. Scalability
3. Maintainability

#### Reliability
- Things that can go wrong are called *faults*, and systems that anticipate faults and can cope with them are considered *fault-tolerant* or *resilient*
-  a fault ≠ a failure
- A Failure = When the whole system stops providing the required service to the user
- It is impossible to reduce the probability of a fault to 0

Another way is to keep testing the system. By randomly killing an individual process without warning you see how the system reacts to the breakdown. Take Netflix and their Chaos Monkey approach. 
They always test their system.

In terms of reliability there are 2 kinds of faults that might occur:
1. Hardware Fault
2. Software Faults

In terms of hardware faults, there is always redundancy in place in order to ensure the system does not go down. I.e. Double power generators, RAID for Hard Drvies, Hot Swappable CPU etc etc

Multi-machine redundancy was only required by a small number of applications that required high availability





