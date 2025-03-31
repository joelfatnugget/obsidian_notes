Before you can embark on what is an Array you need to know that a computer memory is made up of bytes and bits
1 Byte = 8 bits

A computer needs to know what kind of information is stored in what byte, hence the computer uses an abstraction known as a **memory address.** Each byte of memory is associated with a unique number that serves as its address. 

Accessing the RAM it is said to be stored or retrieved in O(1) time. 

#### Referential Arrays

In Python, it must adhere to the requirement that each cell of the array use the same number of bytes. I.e. list is [‘John’, ‘Joel’, ‘Johnson’] all of these have to have the same number of bytes despite the number of names. Hence, what they do is that they have referential arrays. Think of it as pointers to the elements in the Array. 

Python actually represents a list using an internal storage mechanism of an array of **object references.** What is stored is just a consecutive sequence of memory addresses at which the elements of the sequence reside.


![[Screenshot 2025-02-03 at 15.29.32.png]]
This is interesting! When you actually initialise an array of 8 spaces, it all points to the same element. Not individual elements.

#### Compact Arrays in Python
In Both [[C]] and [[Python]], both actually store the Strings as an array of characters. C has an explicit declaration but not python. In Python you store the String as a variable but at the low level it actually stores it as a Character Array.



#### Implementing a Dynamic Array
Python does it’s own Dynamic Array manipulation by conducting the following steps:
1. Allocating a new array B with larger capacity
2. Set B[i] = A[i] for all the elements in A
3. Set A = B, B is the array that will support the list
4. Insert the new element in the new array
They usually double the size of the array! It’s just a commonly used rule for the new array

![[Screenshot 2025-02-03 at 15.45.42.png]]

#### Searching for Occurrences of a Value
`count` , `index` and `__contains__` methods proceed through iteration of the sequence from left to right. Index and `__contains__` actually might be less than n because it will stop the moment it finds it. 
Worst Case: O(n)
But for `index` and `__contains__` it might be less than n

Lexicographic Comparisons
- Evaluating such a condition requires an iteration taking time proportional to the length of the shorter of the 2 sequences
- [7,3…] < [7,5…] this is definitely true ah

#### Adding Elements to a List
In worst case it requires Omega(n) because underlying array is resized
But it uses O(1) time in the amortized sense. This means it is an average time. Sometimes it may be O(1) and other times it may be O(n) etc… but again we are just taking the amortized version of it.

Generally in Python there is such a thing as extending a list. 
#### Extending a List
To extend a list means to take the elements in 1 list and add it to the back of the elements in the other list.
```
for element in list1:
	data.append(element)
```
This means that you are taking all the elements in list1 and appending it to the back of data. However, this is not the best way as you can just call the extend method. Constant factors in Asymptotic analysis are significantly smaller. It is more efficient because the result size of the updated list can be calculated in advance



### Sorting a Sequence
#### Insertion-Sort Algorithm
```
def insertion_sort(A):
	for i in range(1, len(A)):
		cur = A[i]
		j = i
		while j > 0 and A[j-1] > cur:
			A[j] = A[j-1]
			J -= 1
			A[j] = cur
```

It’s multiple nested loops. It starts with the first 2 elements, then it will expand to the first 3 elements… until it reaches the end of the loops.

