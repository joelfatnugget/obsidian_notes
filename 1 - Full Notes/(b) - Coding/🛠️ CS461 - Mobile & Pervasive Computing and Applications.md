Mainly writing in [[Kotlin]]
Kotlin uses camelCase

**Revision - Unit 1**
- How to write and run a simple Kotlin Program
- How to modify a simple program to change the output
- How to define a variable and update its value
- Appropriate Data type for a variable from the basic data types in Kotlin.
- How to add comments to code
-  How to define and call your own functions.
- How to return values from a function that you can store in a variable.
- How to define and call functions with multiple parameters.
- How to call functions with named arguments.
- How to set default values for function parameters.
- How to define and call your own functions.
- How to return values from a function that you can store in a variable.
- How to define and call functions with multiple parameters.
- How to call functions with named arguments.
- How to set default values for function parameters.
Unit 1 Pathway 1 completed
Unit 1 Pathway 2 – Not important, just about how to get the android studio to work
Unit 1 Pathway 3 – Learning about layout of phone
- What is a composable function
- What are annotations? 
- How to write composable functions, such as Text, Column and Row composable functions.
- How to display text in your app in a layout.
- How to format the text, such as changing text size.
- How to add an image or photo to your Android app.
- How to display an image in your app with an Image composable.
- Best practices using `String` resources.
- How to build simple layouts with Row and Column composables, and arrange them with horizontalAlignment and verticalArrangement parameters.
- How to customize Compose elements with a Modifier object.



## Chapter 1
Function in Kotlin begins with `fun` keyword
The `fun` keyword is followed by the function name, inputs and curly braces. Similar to what is covered in Java or Python

```
fun calculateTip(){

}
```
Function Names should follow the camel case convention – First Word of **Function name is all lowercase**, **No Space between words**,  other words should begin with a **capital letter**

Function names:
- Camel Cases
- Verbs or Verb Phrases
- Each statement should be on its own line
- Opening Curly brace should appear at the end of the line where the function begins → ``fun main() {``
- function body should be indented in with 4 spaces. Do not use tabs to indent your code. **(Why?)**
- Closing curly braces are on its own line too

---
#### Conclusion

- A Kotlin program requires a `main()` function as the entry point of the program.
    
- To define a function in Kotlin, use the `fun` keyword, followed by the name of the function, any inputs enclosed in parentheses, followed by the function body enclosed in curly braces.
    
- The name of a function should follow camel case convention and start with a lowercase letter.
    
- Use the `println()` function call to print some text to the output.
    
- Refer to the Kotlin style guide for formatting and code conventions to follow when coding in Kotlin.

---
### Creating and using functions in Kotlin
Kotlin Data Types:

| Data Type | Examples               |
| --------- | ---------------------- |
| String    | “Huat Ah"<br>“Cooking” |
| Int       | 32                     |
| Double    | 2.0                    |
| Float     | 5.0f                   |
| Boolean   | true<br>false          |
![[Pasted image 20250113161918.png]]
Defining and Using Variables
- You need to **declare** a variable first before using it
- Example
- ```val count: Int = 2```
- An expression is a small unit of code that evaluates to a value. An expression can be made up of variables, function calls, and more. 
- **Evaluate** means determining the value of an expression. 
- Variable names should follow camel case convention

**Something interesting**: String Templates
```
fun main(){
val count: Int = 2
println("You have $count unread messages.")
}
```

- You can even do math inside the ${function}
```
fun main(){
val unreadCount = 5
val readCount = 100
println("You have ${unreadCount + readCount} total messages in your inbox.")
}
```

---
### Checking types in Kotlin
#### is and !is operators
```
if (obj is String){
	print(obj.length)
}

if (obj !is String){
	print("Not a String")
}else{
	print(obj.length)
}
```

---
### Updating Variables (Int)

**Note:** var allows the variable to be mutable. You can now mutate the variable and change it to what you want.
```
fun main(){
	var cartTotal = 0
	println("Total: $cartTotal")

	cartTotal = 20
	println("Total: $cartTotal")
}
```

**Note:** ``val`` on the other hand does not allow the variable to be mutated. It is fixed. Similar to ``Const`` in Java
```
fun main(){
	val cartTotal = 0
	println("Total: $cartTotal")
}
```

---
### Other Data Types:
- ##### String: 
```
fun main(){
	val date = "January 1"
	val time = "19:00"
	val reminder = "Next Meetup: " + date + " at " + time
	println(reminder)
}
```

- ##### Boolean: When your variable only has 2 possible values represented by true or false
```
fun main(){
	val notificationsEnabled: Boolean = true
	println(notificationsEnabled)
}
```

---
### Commenting code
```
// is a comment


/*
* This is also a comment that spans across multiple lines
*
*/

```

### Conclusion

- A variable is a container for a single piece of data.
    
- You must declare a variable first before you use it.
    
- Use the `val` keyword to define a variable that is read-only where the value cannot change once it’s been assigned.
    
- Use the `var` keyword to define a variable that is mutable or changeable.
    
- In Kotlin, it’s preferred to use `val` over `var` when possible.
    
- To declare a variable, start with the `val` or `var` keyword. Then specify the variable name, data type, and initial value. For example: `val count: Int = 2`.
    
- With type inference, omit the data type in the variable declaration if an initial value is provided.
    
- Some common basic Kotlin data types include: `Int`, `String`, `Boolean`, `Float`, and `Double`.
    
- You can only update a variable that has been declared as a mutable variable (with `var`).
    
- Use the `+` symbol to concatenate strings together. You can also concatenate variables of other data types like `Int` and `Boolean` to `String`.
---
### Returning a value from a function
![[Pasted image 20250113162842.png]]
By default if you don’t specify a return type, the default return type is ``Unit``.
- `Unit` means that the function does not return a value. It is equivalent to `void` in other languages (Java) and `None` in Python

### Adding a parameter 
![[Pasted image 20250113163006.png]]
```
fun birthdayGreeting(name: String): String{
	val nameGreeting = "Happy Birthday"
	val ageGreeting = "You are now 5 years old!"
	return "$nameGreeting\n$ageGreeting"
}
```

>[!IMPORTANT]
Unlike in some languages, such as Java, where a function can change the value passed into a parameter, parameters in Kotlin are immutable. You cannot reassign the value of a parameter from within the function body.

![[Pasted image 20250113163953.png]]

### There’s also such a thing as default arguments
```
fun birthdayGreeting(name: String = "Rover", age: Int): String {
    return "Happy Birthday, $name! You are now $age years old!"
}
```

- If you want to skip the name argument and go straight to the age
```
println(birthdayGreeting(age = 5))
println(birthdayGreeting("Rex", 2))
```

#### Conclusion

- Functions are defined with the `fun` keyword and contain reusable pieces of code.

- Functions help make larger programs easier to maintain and prevent the unnecessary repetition of code.

- Functions can return a value that you can store in a variable for later use.

- Functions can take parameters, which are variables available inside a function body.
- Arguments are the values that you pass in when you call a function.

- You can name arguments when you call a function. When you use named arguments, you can reorder the arguments without affecting the output.

- You can specify a default argument that lets you omit the argument when you call a function.
---
### Kotlin with Android App

```
class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState) // This is the entry point to the Android App
        setContent {
            GreetingCardTheme {
                // A surface container using the 'background' color from the theme
                Surface(
                    modifier = Modifier.fillMaxSize(),
                    color = MaterialTheme.colorScheme.background
                ) {
                    Greeting("Android")
                }
            }
        }
    }
}
```

### Composable Function
- All functions marked with Composable annotation can be called from the `setContent()` function or other Composable functions
- Composable functions start with a capital letter
- Composable functions can’t return anything
```
// Combine @Preview with @Composable in order to see it in the preview

@Preview(showBackground = true)
@Composable
fun GreetingPreview(){
	GreetingCardTheme {
		Greeting("Meghan")
	}
}
```

A Composable function 
- Must be in Pascal Case (First letter of each word in a compound word is capitalised)
- Must be a noun (e.g. DoneButton())
- MAY be prefixed by descriptive adjectives: `RoundIcon()`

### Test elements in a Row and column
UI Hierachy
Parent > Child 

#### 3 Basic Standard Layout Elements in Compose
1. Column
2. Row
3. Box
- Each composable functions take composable content as arguments, so you can place items inside these layout elements. For example, in a `Row` composable, each child is placed horizontally next to each other.
- ![[Pasted image 20250115131840.png]]

#### Trailing Lambda Syntax
- Curly Braces are used instead of Parentheses in the Row Composable Function.
- Get used to the Compose syntax 
- Kotlin offers a special syntax for passing functions as parameters to functions
![[Pasted image 20250115132015.png]]
**Note that this is a function at the end of all the parameters!**
```
%% Instead of putting %%
Row(
	content = {
		Text("Some Text")
		Text("Some more text")
		Text("Last text")
		}
)

// You can just put
Row(
	Text("Some Text")
	Text("Some more Text")
	Text("Last Text")
)
```

---

#### Adding Images to the project
Jetpack Compose can access the resources defined in the Android Project.
- `R` Class is automatically generated class by Android that contains the IDs of all resources in the project.
- 
```
// Declaring and getting the image
val image = painterResource(R.drawable.androidparty)
```
*Remember to import the function*

Don’t forget about Accessibility
1. A content description defines the purpose of a UI Element!
	1. This is important for the applications that use TalkBack
	2. If the image is just purely decorative, then remember to insert `contentDescription = null`

---
### Box Layout
- Use box layout to stack elements on top of one another. Similar to that of [[Z-index]] in CSS or Web Dev!
```
@Composable
fun GreetingImage(meesage: String, from: String, modifier: Modifier = Modifier){
	val image = painterResource(R.drawable.androidparty)
	Box(modifier){
		Image(
			painter = image,
			contentDescription = null
			contentScale = ContentScale.Crop // Scale image uniformly to maintain the aspect ratio
			alpha = 0.5F
			)
			GreetingText(
				message = message,
				from = from,
				modifier = Modifier
				.fillMaxSize() // This will fill up the entire screen
				.padding(8.dp)
			)
		}
}
```


#### Layout Modifier
- Modifier are used to decorate UI elements
- I.e. Add backgrounds, padding or behavior to rows, text or buttons
- You need to set the composable or a layout to accept modifier as parameters
- To set children’s position within a `Row`, set the `horizontalArrangement` and `verticalAlignment` arguments. For a `Column`, set the `verticalArrangement` and `horizontalAlignment`
- Note that `verticalAlignment` ≠ `verticalArrangement`
![[unit1-pathway3-activity4-section5-df69881d07b064d0.gif]]

In Column, you have `EqualWeight`, `Space Between`,`Space Around`, `Space Evenly`,`Top`,`Center`,`Bottom`
![[unit1-pathway3-activity4-section5-c1e6c40e30136af2.gif]]
---

#### Clean Code #1
>[!important] Keep your imports listed alphabetically and remove unused imports.

>[!tip] : Be careful of Translation!
- String data type is a sequence of Characters
- Do not hardcode strings, it makes it harder to translate the application. You can extract the strings into a resource file
	- Think of it as a book of variables that contains the String values to these variables
- `Extract string resource` in order to get the Extract Resource Dialogue
```
<resources>
    <string name="app_name">Happy Birthday</string>
    <string name="happy_birthday_text">Happy Birthday Sam!</string>
    <string name="signature_text">From Emma</string>
</resources>
```

```
@Preview(showBackground = true)
@Composable
fun BirthdayCardPreview() {
    HappyBirthdayTheme {
        GreetingImage(
            message = stringResource(R.string.happy_birthday_text),
            from = stringResource(R.string.signature_text)
        )
    }
```


---
## Conclusion
- To create a new project: open Android Studio, click **New Project ➜ Empty Activity ➜ Next**, enter a name for your project and then configure its settings.
    
- To see how your app looks, use the **Preview** pane.
    
- Composable functions are like regular functions with a few differences: functions names are capitalized, you add the `@Composable` annotation before the function, `@Composable` functions can’t return anything.
    
- A `Modifier` is used to augment or decorate your composable.
---
## Chapter 2: Write Conditionals in Kotlin
Idea is to teach you how to use if/else and when statements and expressions to write conditionals in Kotlin.

What you’ll learn?
- How to write boolean expressions
- How to write if/else statements
- How to write when statements
- How to write if/else expressions
- How to write when expressions
- How to use commas to define common behaviour for multiple branches in when conditionals
- How to use the in range to define common behavior for a range of branches in when conditionals.
- How to use the is keyword to write when conditional statements
### Section 1
#### Use if/else statements (Conditions)
```
if (condition1){
	// code to execute if condition1 is true
}else if (condition2){
	// code to execute if condition2 is false
}else if (condition3){
	// code to execute if condition3 is false
} else{
	// code to execute if ALL condition is false
}
```

#### When Statement for multiple branches
- In Kotlin, when you deal with multiple branches, you can use the `when` statement instead of the `if/else` statement because it improves readability. 
- Good readability ensures that developers can correctly understand your code
- `when` statements are preferred when there are more than 2 branches to consider
i.e. 
```
when (parameter){
	condition1 -> body1
	condition2 -> body2
	condition3 -> body3
}
```

**Example 1**
```
fun main(){
	val trafficLightColor = "Black"

	when(trafficLightColor){
		"Red" -> println("Stop")
		"Yellow" -> println("Slow")
		"Green" -> println("Go")
		else -> println("Invalid traffic-light color")
	}
}
```
**Example 2**
```
fun main(){
	val x = 3

	when(x) {
	2 -> println("x is a prime number between 1 and 10.")
	3 -> println("x is a prime number between 1 and 10.")
	5 -> println("x is a prime number between 1 and 10.")
	7 -> println("x is a prime number between 1 and 10.")
	else -> println("x isn't a prime number between 1 and 10.")
	}
}
```

if you want to have multiple conditions, use a comma to correspond to the same body.
**Example 3**
```
fun main(){
	val x = 3

	when(x){
	2,3,5,7 -> println("x is a prime number between 1 and 10")
	else-> println("x isn't a prime number betwen 1 and 10")
	}
}
```


> [!abstract]
>Use the `in` keyword and a range of values in `when` branches

**Example 4**
```
fun main(){
	val x = 3

	when(x) {
	2,3,5,7-> println("X is a prime number between 1 and 10")
	in 1..10 -> println("X is a number between 1 and 10 but it is not a prime number)
	else->println("x is not a prime number between 1 and 10.)
	}
}
```


>[!Abstract]
>Use the `is` keyword as a condition to check the data type of an evaluated value.

```
when(x){
	2,3,5,7 ->println("x is a prime number between 1 and 10.")
	in 1..10 -> println("x is a number between 1 and 10, but not a prime number.")
	is Int -> println("X is an integer number, but not between 1 adn 10.")
	else-> println("x isn't an integer number.")
}
```

#### If/else statements and when (Expressions)
You can use conditionals as expression to return different values for each branch. Similar to [[Ternary Operators]] BUT IT ISN’T CALLED TERNARY OPERATORS
```
fun main(){
	val trafficLightColor = "Black"

	val message = 
		if( trafficLightColor == "Red")"Stop"
		else if(trafficLightColor == "Yellow") "Slow"
		else if(trafficLightColor == "Green")"Go"
		else "Invalid traffic-light color"
}
```
 
>[!note]
>A `when` statement does not need the `else` branch to be defined. However, you need to have the `when` expression to return a value. Kotlin compiler will check whether all branches are exhaustive. An `else` branch ensures that there won’t be a scenario where the variable doesn’t get assigned a value

#### Conclusion
- Kotlin, branching is achieved with `if/else` or `when` conditionals
- It is recommended to use `when` conditional to replace an `if/else` conditional when there are more than 2 branches
- Write more complex conditions in `when` conditionals with the comma (`,`) in ranges, and the `is` keyword
- `if/else` and `when` conditionals can work as either statements or expressions
---
### Section 2: Use nullability in Kotlin
#### Learning Objective
1. Identify what `null` is
2. the difference between nullable and non-nullable types
3. What `null` safety is, its importance, and how Kotlin achieve `null` safety.
4. How to access methods and properties of nullable variables with the `?.` safe call operator and `!!` non-null assertion operator
5. How to perform `null` checks with `if/else` conditionals
6. How to convert a nullable variable to a non-nullable type with `if/else` expressions
7. How to provide a default value when a nullable variable is `null` with the `if/else` expression or the `?:` Elvis operator



#### Use nullable variables
```
fun main(){
	val favouriteActor = null
}
```

- Kotlin → Has a distinction between nullable and non-nullable types:
	- Nullable types are variables that can hold `null`
	- Non-null types are variables that cannot hold `null`.
- A type is only nullable if you explicitly let it hold `null`. As the error message says the String data type is non-nullable, so you cannot reassign the variable to `null`
- To declare the nullable variables in Kotlin, you need to add a `?` operator to the end of the type. 
	- i.e. `String?` can hold either a string or a null
	- Without the nullable type, the compiler infers that it’s a non-nullable type.

>[!note]
>nullable variables for variables that can carry `null` , you should use non-nullable variables for variables that can never carry `null` because the access of nullable variables requires more complex handling.

---
#### Dice Roller Application
#### What you will learn
1. Adding a Button
2. Add behavior to the `Button`
3. How to open and modify the `Activity` code of an Android app

```
@Preview
@Composable
fun DiceRollerApp(){
	DiceWithButtonAndImage()
}
```


```
@Composable
fun DiceWithButtonAndImage(){

}
```

#### Adding a modifier
Compose uses a `Modifier` object, which is a collection of elements that decorate or modify the behavior of Compose UI. You use this `Modifier` to style the Dice Roller app’s components

```
@Composable
fun DiceWithButtonAndImage(modifier: Modifier = Modifier){

}
```
- Function accepts a modifier parameter. Defaults value of `modifier` parameter is a `Modifier` object, hence the `= Modifier` piece of the method signature. 
- Default value of a parameter allows anyone who calls this method in the future decide whether to pass a value for the parameter. 
	- If they pass their own `Modifier` object, they can customize the behavior and decoration of the UI.
	- If they choose not to pass a `Modifier` object, it assumes the value of the default, which is the plain `Modifier` object. 

- `DiceWithButtonAndImage()` composable has a modifier parameter in `DiceRollerApp()`, pass a modifier when the composable is called

```
DiceWithButtonAndImage(modifier = Modifier
	.fillMaxSize()
	.wrapContentSize(Alignment.Center))
```

 #### Create a vertical layout
- vertical layouts are created with the `Column()` function
- `Column()` function a composable layout that places its children in a vertical sequence. 



----
#### Understanding State in Compose
- A State is any value in an app that can change over time

How does. Composition works?
When the state of your app changes, it will schedule a recomposition. Android Compose will run the recomposable to change the values.

> [!NOTE] Composable functions can  store an object across compositions by using `Remember`

A Variables initialised during initial composition and is remembered during pre-composition. You can use remember to store any type of value! Each time the app data is updated, you need a way to observe the change and trigger the recomposition

`mutableStateOf` function
You need this function in order to create an observable that will observe the change and then trigger the recomposition

- Be aware of parent and child and where you write the `State` data. Data can be shared with other composables. 
- **State Hoisting! This is important**
	- You need to hoist the state if the state is meant to be shared acorss multiple composable functions.
	- Move it to the method declarations so that the parent can choose the state. With this change, the composable moved its state to the parent function

#### Usage of Custom Style and Theme
Styles and Themes are a collection of attributes that specifies the appearance for a single UI element. A style can specify attributes such as font colour, font size, background color and more. 


#### The Composition
- Compose is a declarative UI framework, meaning that you declare how the UI should look in your code. 
- There is something called a recomposition to update the composition of the app. You need to recompose in the case where you see a state change.
- Compose apps call composable functions to transform data into UI. If a state change happens, Compose re-executes the affected composable functions with the new state.
- When compose runs your composable, it keeps track of the composables that we are using. 
- Composition can only be produced by an initial composition and updated by recomposition.
- **The only way to modify the Composition is through recomposition**
- Compose needs to know what state to track so that it can schedule the recomposition when it receives an update. 
- Use `State` and `MutableState` types in Compose to make state in your app observable. 
	- `State` in and of itself is not immutable
	- `MutableState` type is mutable → `mutableStateOf()`
- It receives an initial value as a parameter that is wrapped in a `State` object.


#### by remember
If you need to store an object across recompositions with `remember`. A value computed by the `remember` function is stored in the Composition during initial composition and the stored value is returned during recomposition

- When you use remember, always have the default getters and setters in place
```
import androidx.compose.runtime.remember
import androidx.compose.runtime.getValue
import androidx.compose.runtime.setValue
```

```
@Composable
fun EditNumberField(modifier: Modifier = Modifier){
	var amountInput by remember { mutableStateOf("")}
	TextField(
		value = amountInput,
		onValueChange = {amountInput = it},
		modifier = modifier
		)
}
```


#### Modifying the appearance
```
TextField(
	value = amountInput,
	onValueChange = { amountInput = it},
	label = {Text(stringResource(R.string.bill_amount))},
	singleLine = true,
	modifier = modifier
)
```


#### How to parse a string into a int digit?
```
val amount = amountInput.toDoubleOrNull() ?: 0.0
```

- `toDoubleOrNull()` is a predefined Kotlin function that parses a string as a `Double` number and returns the result. If the string isn’t a valid representation of a number. The `?:` operator returns `0.0`
----
### Unit 3 Pathway 1 Activity 2: Generics, Objects, Extensions
#### Make a reusable class with generics

What is a generic Data type?
1. Generic Types allow for a data type, to specify an unknown placeholder data. 
	- It can be used with its properties and methods. 
![[Pasted image 20250210100441.png]]
Notice it is a class with the various properties such as a class name, a generic data type and it’s properties.

>[!note] 
>There is a generic type named `T` or other capital letters if the class has multiple generic types.

To create the class you use:
```
class Question<T>{
	val questionText: String,
	val answer: T,
	val difficulty: String
}
```

Then in order to call the instance of it you have to use
```
fun main(){
	val question1 = Question<String>("Type your reply here", "nevermind", "easy")
	val question2 = Question<Boolean>("Is that true?", false , "hard")
	val question3 = Question<Int>("How old are you?", 20 , "hard")
}
```

#### Using an enum class
enum here works differently from the normal enum class in say python
enum here is used to create types with a limited set of possible values. 

each possible value of an enum is called an **enum constant**
Refer to the enum constant using the `.` operator

For example:
```
enum class Difficulty{
	EASY,MEDIUM,HARD
}
```

then in your `Question` class, change the data type of difficulty from `String` to `Difficulty`
```
class Question<T>{
	val questionText: String,
	val answer: T,
	val difficulty: Difficulty
}
```

then in the instantiating phase:
```
val question1 = Question<String>("abadvasd","okay",Difficulty.MEDIUM)
```

–
Currently the classes that we are working with are subclasses of `Activity`, but there is also another type of classes that don’t have any methods that performs an action. They are called `data class`

A data class allows the compiler to make assumptions and to automatically implement some methods. I.e. `toString()` is called behind the scenes by the `println()` function

>[!important]
>- Data classes need to have at least 1 parameter in its' constructor
>- All constructor parameters must be marked with a `val` or a `var`
>  
>  **data class cannot be abstract, open, sealed or inner**

Think about the toString function in [[Java - IS442 Notes]]
#### Convert `Question` to data class
It’s as simple as just putting a `data` keyword in front of the function
```
data class Question<T> {
	val questionText: String,
	val answer: T,
	val difficulty: Difficulty
}
```

---
#### Defining a Singleton Object
```
object StudentProgress{
	var total: Int = 10
	var answered: Int = 3
}
```

For a singleton Object, all you need to do is to change out the `class` property with an `object` property. A singleton object cannot have a constructor as you can’t create instances directly. Hence, instead of that, all the properties are defined within the curly braces and are given an initial value.

#### Accessing a Singleton Object
Because there is only 1 instance of a singleton… Accessing it’s properties are simple.
```
fun main(){
	println("${StudentProgress.answered} of ${StudentProgress.total} answered.")
}
```

#### Declaring objects as a companion objects (New Concept)
This refers to having a singleton object declared inside another class. One way of doing this is to use a **companion object.**
- This allows you to access its properties and methods from inside the class
i.e. You are putting a Singleton Object inside the class property. 
>[!Question]
>What is the benefit to this though?

```
class Quiz {
	val question1 = Question<String>("Quoth the raven ___", "nevermore", Difficulty.MEDIUM)
    val question2 = Question<Boolean>("The sky is green. True or false", false, Difficulty.EASY)
    val question3 = Question<Int>("How many days are there between full moons?", 28, Difficulty.HARD)

    object StudentProgress {
		var total: Int = 10
		var answered: Int = 3    }
}
```

But instead of writing such a long code, you could just swap it out for a companion object.
```
class Quiz {
    val question1 = Question<String>("Quoth the raven ___", "nevermore", Difficulty.MEDIUM)
    val question2 = Question<Boolean>("The sky is green. True or false", false, Difficulty.EASY)
    val question3 = Question<Int>("How many days are there between full moons?", 28, Difficulty.HARD)

    companion object StudentProgress {        
		var total: Int = 10
        var answered: Int = 3
    }
}
```

---
### Extension Function
fun Quiz.StudentProgress.printProgressBar(){
	repeat(Quiz.answered){ print(“▓”)}
	repeat(Quiz.total - Quiz.answered) { print("▒") } // represents unanswered questions
    println()
    println(Quiz.progressText)
}

---
#### What is an Interface
- An interface is a contract. A class that conforms to an interface is said to extend the interface. 
- The class MUST implement all properties and methods specified in the interface. This lets you easily ensure that any class that extends the interface will have the corresponding methods with the exact same method signature
- If you modify the interface, you will need to update any class that extends the interface

#### How to declare an interface
```
interface ProgressPrintable {
	val progressText: String,
	fun printProgressBar()
}
```

#### How to  implement an interface with the Class?
```
Class Quiz: ProgressPrintable {
	val question1 = Question<String>("Quoth the raven ___", "nevermore", Difficulty.MEDIUM)
    val question2 = Question<Boolean>("The sky is green. True or false", false, Difficulty.EASY)
    val question3 = Question<Int>("How many days are there between full moons?", 28, Difficulty.HARD)

    // use ``override`` because this is from the ProgressPrintable interface
    override val progressText: String
        get() = "${answered} of ${total} answered"

    // use ``override`` because this is from the ProgressPrintable interface
    override fun printProgressBar() {
        repeat(Quiz.answered) { print("▓") }
        repeat(Quiz.total - Quiz.answered) { print("▒") }
        println()
        println(progressText)
    }

    companion object StudentProgress {
        var total: Int = 10
        var answered: Int = 3
    }
}
```

You need to override it. 


#### Using `let()` to replace long object names
```
fun printQuiz() {
    question1.let {
        println(it.questionText)
        println(it.answer)
        println(it.difficulty)
    }
    println()
    question2.let {
        println(it.questionText)
        println(it.answer)
        println(it.difficulty)
    }
    println()
    question3.let {
        println(it.questionText)
        println(it.answer)
        println(it.difficulty)
    }
    println()
}
```

```
val quiz = Quiz()
quiz.printQuiz()
```

This can be re-written as 

```
Quiz().apply{
	printQuiz()
}
```

---
### Unit 3 Pathway 1 Activity 3: Use collections in Kotlin

#### Introduction
Collection Types aka **Data Structures** lets you store multiple values in an organised way.
- Could be an ordered list, a group or a mapping of values of one data type to another
- There’s 2 different sets, a Mutable Collection types or an immutable collection types

#### Arrays
To declare an array
```
val rockPlanets = arrayOf<String>("Mercury","Venus","Earth","Mars")
```

Kotlin actually uses type inference, so you don’t need to specify the type name
>[!NOTE] 
>You can concatenate Arrays together

Arrays are not lists. Arrays have fixed sized. You cannot add elements to an array beyond this size. 

#### List
List on the other hand are ordered and resizable, usually implemented as a resizable array. When the array is filled to capacity, and you try to insert a new element, the array is copied to a bigger array.

##### listOf() function
listOf() takes in items as parameters and returns a List rather than an array.

There is also something called the get() method. The get() method allows you to take an `Int` as a parameter and return the element at that index. 

#### repeat() or for-loop
You can use the repeat() function to execute code multiple lines
another way is just a for-loop
```
for (planet in solarSystem){

}
```

#### Adding to a list
``` 
solarSystem.add(3,"ABC") // This will add it at index 3

solarSystem.add("Pluto") // This will add it to the back of the list
```

#### If you want to update
solarSystem[3] = “Future Moon”

#### Delete/Removal
```
solarSystem.removeAt(9)

solarSystem.remove(“Future Moon”)
```

solarSystem.contains(“Pluto”)

### Sets
- Unable to have duplicate values and does not have a specific order
- This is enabled by a **hash code**
	- A Hash Code is an `Int` produced by the `hashCode()` method of any Kotlin class. 
	- Think of it as a semi-unique identifier for a Kotlin Object. A small change to the object, such as adding one character to a `String` results in a vastly different hash value. 
- Sets have 2 important properties
	- Searching of a specific element is fast – Compared to List
			- indexOf() of a `List` requires checking each element from the beginning until a match is found
			- Sets tend to use more memory than lists for the same amount of data, since more array indices are often needed than the data in the set
- Benefit of Sets is the uniqueness

There’s both Set and MutableSet in Kotlin

### Map Collection
This is similar to a dictionary in Python but a Map in Java
- Map Keys are unique, A Map values however are not. Remember that the identifiers for Maps are that of the keys
- Accessing a value from a map by its key is generally faster than searching through a large list
- Maps can be declared using the `mapOf()` or `mutableMapOf()` function.

```
val solarSystem = mutableMapOf(
	"Mercury" to 0,
	"Venus" to 1,
	...
```

Like lists and sets, Map provides a size property. The other functions are similar to that of Python
``solarSystem.remove(“Pluto”)``

#### Conclusion
- Arrays store ordered data of the same type, and have a fixed size.
    
- Arrays are used to implement many of the other collection types.
    
- Lists are a resizable, ordered collection.
    
- Sets are unordered collections and cannot contain duplicates.
    
- Maps work similarly to sets and store pairs of keys and values of the specified type.

---
### Higher-Order Functions with Collections
#### Loop over a list with forEach()

```
fun main(){
	cookies.forEach{
		println(“Menu item: $it”)
	}
}
```
Notice how $it refers to the for each item. 

- To Access properties and embed them in a string, you need an expression. 
```
cookies.forEach{
	println("Menu item: ${it.name}")
}
```

#### map() function
map function allows you to transform a collection into a new collection with the same number of elements. map() could transform `List<Cookie>` into `List<String>`

```
val fullMenu = cookies.map {
	"${it.name} - $${it.price}"
}
```
The only reason why u need 2 ``$$`` for price is becuz you talking about price


#### filter()
filter function lets you create a subset of collection. If you had a list of numbers, you could use `filter()` to create a new list that only contains numbers divisible by 2

map() will always get a collection of the same size, filter() will get a collection of same size or smaller. Additionally, filter() will always result in the same data type

For each item in the collection: 
- if the result of the lambda expression is true = It will be included in the new collection
- if the result of the lambda expression is false = it will not be included in the new collection

```
val softBakedMenu = cookies.filter {
    it.softBaked
}
```


#### groupBy()
![[Pasted image 20250210142528.png]]

```
val groupedMenu = cookies.groupBy { it.softBaked }
val softBakedMenu = groupedMenu[true] ?: listOf()
val crunchyMenu = groupedMenu[false] ?: listOf()
```


#### fold() function
Takes in 2 aprameters, initial value… data type is inferred when calling the function
Lambda expression that returns a value with the same type as initial value

- The lambda expression has 2 additional parameters:
	- Accumulator. Running total, everything the lambda expression is called, accumulator is equal to the return value from the previous time the lambda was called
	- second parameter is the same type as each element in the collection
```
val totalPrice = cookies.fold(0.0) {total, cookie ->
    total + cookie.price
}
```

`fold()` is sometimes called `reduce()`. The `fold()` function in Kotlin works the same as the `reduce()` function found in JavaScript, Swift, Python, etc. Note that Kotlin also has its own function called `reduce()`, where the accumulator starts with the first element in the collection, rather than an initial value passed as an argument.


#### sortedBy()
this allows you to sort the various objects based on a comparator
Think of Comparable operators in Java. 

```
val alphabeticalMenu = cookies.sortedBy {
    it.name
}
```



---
#### Navigation

----
#### Week 9 - Concurrency, Asynchronous Code

- Concurrency
- Asynchronous code
	- launch() – Don’t care about return result
	- async() – Care about return result
Coroutine = “cooperative” piece of Code
Coroutine → Thread → CPU Core
- Coroutine Concepts
	- Job
	- CoroutineScope
		- Attached to MainActivity (LifeCycleScope)
		- Attached to ViewModel (ViewModelScope)
	- CoroutineContext
	- Dispatcher
		- Which thread to run the coroutine on? 
		- Dispatcher.Main
		- Dispatcher.IO
		- Dispatcher.Default
	- Dependency Injection 
		- Multiple components that need other components… Using Dependency Injection 

Structured concurrency – How you really want to structure your code. Think of it as a reporting structures! The guy at the top says cancel all the work, those at the bottom will also adhere

The **SUSPENSE** modifier is used to mark a function whose execution can be suspended and resumed at a later point.



Collect and CollectAsState

CollectAsState converts it into a different object for you. 