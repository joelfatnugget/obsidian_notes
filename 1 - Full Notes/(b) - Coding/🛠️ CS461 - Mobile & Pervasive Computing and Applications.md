Mainly writing in [[Kotlin]]
Kotlin uses camelCase
# Lesson 1
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
## Conclusion

- A Kotlin program requires a `main()` function as the entry point of the program.
    
- To define a function in Kotlin, use the `fun` keyword, followed by the name of the function, any inputs enclosed in parentheses, followed by the function body enclosed in curly braces.
    
- The name of a function should follow camel case convention and start with a lowercase letter.
    
- Use the `println()` function call to print some text to the output.
    
- Refer to the Kotlin style guide for formatting and code conventions to follow when coding in Kotlin.

---
## Creating and using functions in Kotlin
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
##### is and !is operators
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
## Updating Variables (Int)

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
## Other Data Types:
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
## Commenting code
```
// is a comment


/*
* This is also a comment that spans across multiple lines
*
*/

```

## Conclusion

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

## Adding a parameter 
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

## Conclusion

- Functions are defined with the `fun` keyword and contain reusable pieces of code.

- Functions help make larger programs easier to maintain and prevent the unnecessary repetition of code.

- Functions can return a value that you can store in a variable for later use.

- Functions can take parameters, which are variables available inside a function body.
- Arguments are the values that you pass in when you call a function.

- You can name arguments when you call a function. When you use named arguments, you can reorder the arguments without affecting the output.

- You can specify a default argument that lets you omit the argument when you call a function.
---
## Kotlin with Android App

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

## Test elements in a Row and column
UI Hierachy
Parent > Child 

##### 3 Basic Standard Layout Elements in Compose
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



#### Adding Images to the project
Jetpack Compose can access the resources defined in the Android Project.
- `R` Class is automatically generated class by Android that contains the IDs of all resources in the project.
- 
```
// Declaring and getting the image
val image = painterResource(R.drawable.androidparty)
```
*Remember to import the function*



---
#### Clean Code #1
>[!important] Keep your imports listed alphabetically and remove unused imports.

---
## Conclusion
- To create a new project: open Android Studio, click **New Project ➜ Empty Activity ➜ Next**, enter a name for your project and then configure its settings.
    
- To see how your app looks, use the **Preview** pane.
    
- Composable functions are like regular functions with a few differences: functions names are capitalized, you add the `@Composable` annotation before the function, `@Composable` functions can’t return anything.
    
- A `Modifier` is used to augment or decorate your composable.