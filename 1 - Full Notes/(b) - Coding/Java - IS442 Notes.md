2025-01-17 10:00
Status: 
Tags: #java

```
String str1 = "SMU";
String str2 = "SMU";


if(str1 == str2){
....
}
```
This will return `true`, because it will get the code from the String Pool. It is unique to Java and particularly Strings.
- Same Storage location, therefore str1 == str2. This is not strict!


```
String str1 = new String("SMU");
String str2 = new String("SMU");


if(str1 == str2){
....
}
```
This will return `false` because the New keyword is inside, so it will pull from the String pool but different locations.

In terms of checking for values… you can think of JDK as having a Cache-ing system. Instead it is called a buffer and it will check the buffer instead of checking the hard drive.



#### Inheritance
- Constructors are not inherited by subclasses
- Constructors of the superclass can be invoked from the subclass
	- You do this by using the super(x) function to call the constructor (with input x) in the immediate parent class
	- if you are in the same class, you can call this(x)
	- if no super(x) in a constructor, java will automatically call super() for you

##### Overriding
Overriding occurs when the subclass has the same signature (name, number and type of parameters).
```
public class Employee{
	private String name;
	private double baseSalary;

	public String toString(){
		return "name=" + name + ",baseSalary=" + baseSalary;
	}
}
```


```
public class Manager extends Employee {
	private double allowance;
	public String toString(){
	return super.toString() + ",allowance=" + allowance;
	}
}
```

You cannot override the parent method with a stricter modifier. I.e. Your Manager cannot inherit a public and then implement a protected method. 

>[!important]
>static and final methods CANNOT be overriden

```
Parent p = new Child();
Child c = new Parent(); // This will result in a compile error
```

Only child can inherit and access the parents methods. But the parent cannot inherit the child methods.


**Method Showcase: instanceof** 
	The usage of instanceof is to help check if an object can be converted to class
```
if (shape instanceof Rectangle){
...
}
```

How to create a subclass?
just use the word extends
```
public class Cow extends Mammal {
	public Cow(String name){
		super(name);	
	}
}
```

All abstract methods must be implemented in the child class. 

Abstract class **CANNOT** be used for instantiating an object.

If the child class is not an abstract class, it must contain all the concrete implementation of all inherited abstract methods so that the instantiated object can be used to invoke that method. 

If child class is an abstract class, it is optional to override abstract methods. 


#### Interface Properties
- Child class MUST provide implementations of the methods specified in the interface
```
public class Cat extends Mammal implements Pet{

}
```
This means that Cat is a child of Mammal and is implementing the interface Pet


- Java does not support multiclass inheritance; instead interface provides a workaround. 

>[!Danger]
- Polymorphism: 
	- **Allowing objects of different classes to be treated interchangeably if they implement the same interface.**
	- Idea is to promote code *reusability* & *flexibility* in OO
- Abstraction
	- Interface provides a way to achieve abstraction
	- This is because they define a set of methods without specifying their implementation details. This allows for separating the behavior of a lass from its implementation.

If you are an abstract class, that is implementing the interface you don’t need to override the interface abstract methods. 

BUT 
if you are a class implementing the interface, it must provide all the concrete implementation of ALL implemented abstract methods.

###### Every interface is implicitly abstract and public
##### Every field/variable in the body of an interface is implicitly public, static and final
###### Every method declared in the body of an interface is implicitly public and abstract

All Java class are automatically extension of the standard class Object. 

Object specifies some basic behaviors common to all objects.


### Pure Polymorphism
- Which method to invoke will only be determined at execution time.
- It’s more of a late binding

---
#### Comparable Interface

Comparable interface is used to sort a collection of objects of a particular class. 

In Comparable interface there is something called a compareTo… this compares the object with the specified object for order.

```
public class Student implements Comparable<Student>{
	public int compareTo(Student another){
	return name.compareTo(another.name);
	}
}
```

```
import java.util.ArrayList;
import java.util.Collections;


public class StudentTest {
	public static void main(String[] args) {
		ArrayList<Student> sList = new ArrayList<Student>();
		sList.add(new Student("Charlie", 12));
		sList.add(new Student("Amy", 13));
		sList.add(new Student("Billy", 11));
		Collections.sort(sList); // This one is the important thing!
		System.out.println(sList);
	}
}
```
By using Collections.sort() it actually sorts it based on the name of the student. 

Remember this uses the Collections.sort()

Remember that Comparable Interface is less useful then Comparator

```
public class AgeComparator impelmeents Comparator <Student> {
	public int compare(Student s1, Student s2){
		return s1.getAge()-s2.getAge();
	}
}
```

```
public class StudentTest{
...
	Collections.sort(sList, new AgeComparator());
}
```

Remember that the Comparator will always return an integer. Play around.


![[Screenshot 2025-02-14 at 13.27.39.png]]

---
