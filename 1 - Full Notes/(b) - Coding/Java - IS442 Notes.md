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

## References

