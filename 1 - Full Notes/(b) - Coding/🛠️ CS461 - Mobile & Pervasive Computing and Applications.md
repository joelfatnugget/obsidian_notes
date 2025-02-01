Mainly writing in [[Kotlin]]
Kotlin uses camelCase
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
