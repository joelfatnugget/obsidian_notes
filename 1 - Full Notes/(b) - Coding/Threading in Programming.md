08-01-2025 10:19
Status: 
Tags:

## References
Threads are not the same as processes

In order to understand threads you have to understand processes first. 

Each Program has a set of instructions and manuals. This means multiple processes. Each process cannot communicate with the other process. Therefore even if one process has a bug or an issue, it will not affect the other processes. For example, in Google Chrome, 1 process will not affect the other process. Each Tab is in it's own process. Therefore if one tab is down or buggy, the other tabs are not affected.

This is not the case when you are using Arc, when one tab is down, sometimes it may affect all the other tabs.

Pros: One tab misbehaves due to bug or malicious attack, other tabs are unaffected
Question: Does this help prevent against Cross-site scripting?

Cons: Memory intensive and having to keep all the connections alive. 



## Thread
What is a thread?
> A thread is a unit of execution within a process.

A process has 1 thread, the main thread. Each thread has it's own **stack**, **Registers**, **Program Counters**
 ![[Process vs Thread.png]]

Because there is a shared memory address space, different processes are now able to communicate with one another. 
Pros: Ability to communicate across different threads.
Cons: Vulnerable to attacks, 1 attack to one thread can bring down the entire process.

# How does OS run a thread or process on the CPU?
## Context Switching
