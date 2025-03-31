2025-02-01 12:13
Status: 
Tags:

## References

Idea is always to reduce coupling and specifically tightly coupled classes

What exactly is dependency injection?
Classes often require references to other classes. 
I.e. `Car` might need a reference to an `Engine` class. These classes are called dependencies, in this example the `Car` class is dependent on having an instance of the `Engine` class to run.

Think of it as like a [[microservice]] and how you create [[microservice]]s in order to avoid tightly coupled systems. The idea is that you always do it at a orchestrator level kind of thing. There is an algorithm behind the scenes to pull these different classes together. 

Without dependency injection, a `Car` will creates its own `Engine` dependency. 
```
class Car {

    private val engine = Engine()

    fun start() {
        engine.start()
    }
}

fun main(args: Array) {
    val car = Car()
    car.start()
}
```

In Kotlin you can use something called Hilt, which is a dependency injection library for Android 