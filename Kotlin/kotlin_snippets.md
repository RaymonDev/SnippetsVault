## Kotlin

### Hello World
```kotlin
fun main() {
    println("Hello, World!")
}
```

### Variable declaration
```kotlin
val pi = 3.14159
var count = 0
```

### Basic data types
```kotlin
val num: Int = 42
val name: String = "John"
val isTrue: Boolean = true
```

### String interpolation
```kotlin
val name = "John"
val age = 42
println("My name is $name and I am $age years old.")
```

### Conditional statements
```kotlin
val age = 18
if (age >= 18) {
    println("You're an adult.")
} else {
    println("You're a minor.")
}
```

### When expression
```kotlin
val day = 2
when (day) {
    1 -> println("Monday")
    2 -> println("Tuesday")
    else -> println("Other day")
}
```

### For loop
```kotlin
for (i in 1..5) {
    println(i)
}
```

### While loop
```kotlin
var i = 0
while (i < 5) {
    println(i)
    i++
}
```

### Function declaration
```kotlin
fun add(a: Int, b: Int): Int {
    return a + b
}
```

### Lambda Functions
```kotlin
val multiply = { a: Int, b: Int -> a * b }
val result = multiply(5, 3)
```

### Extension Functions
```kotlin
fun String.isPalindrome(): Boolean {
    val cleanStr = this.replace("\\s".toRegex(), "").toLowerCase()
    return cleanStr == cleanStr.reversed()
}
```

### Lists
```kotlin
val fruits = listOf("apple", "banana", "cherry")
val firstFruit = fruits[0]
```

### Maps
```kotlin
val scores = mapOf("Alice" to 95, "Bob" to 85, "Carol" to 90)
val aliceScore = scores["Alice"]
```

### Null safety
```kotlin
val nullableValue: String? = null
val length = nullableValue?.length ?: 0
```

### Class declaration
```kotlin
class Person(val name: String, var age: Int)
val person = Person("John", 30)
```

### Inheritance
```kotlin
open class Animal(val name: String)
class Dog(name: String, val breed: String) : Animal(name)
```

### Interfaces
```kotlin
interface Shape {
    fun area(): Double
}
```

### Enum
```kotlin
enum class Color {
    RED, GREEN, BLUE
}
val selectedColor = Color.RED
```

### Try-catch
```kotlin
try {
    // Code that may throw an exception
} catch (e: Exception) {
    // Handle the exception
}
```

### File IO
```kotlin
val text = File("data.txt").readText()
File("output.txt").writeText("Hello, World!")
```

### Extension Properties
```kotlin
val List<String>.secondOrNull: String?
    get() = if (size >= 2) this[1] else null
```

### Filter List
```kotlin
val numbers = listOf(1, 2, 3, 4, 5)
val evenNumbers = numbers.filter { it % 2 == 0 }
```

### Map List
```kotlin
val numbers = listOf(1, 2, 3, 4, 5)
val squaredNumbers = numbers.map { it * it }
```

### Sort List
```kotlin
val names = listOf("Alice", "Bob", "Carol")
val sortedNames = names.sorted()
```

### String operations
```kotlin
val text = "Kotlin is awesome"
val upperCaseText = text.toUpperCase()
val words = text.split(" ")
```

### Regular Expressions
```kotlin
val regex = "\\d+".toRegex()
val match = regex.find("Age: 30")?.value
```

### Date and Time
```kotlin
import java.time.LocalDate
val currentDate = LocalDate.now()
```

### Random Numbers
```kotlin
val random = (0..10).random()
```

### Multiline Strings
```kotlin
val multilineText = """
    This is a
    multiline string.
"""
```

### Break and Continue
```kotlin
for (i in 1..10) {
    if (i == 5) break
    println(i)
}
```

### Collections Operations (e.g., sum)
```kotlin
val numbers = listOf(1, 2, 3, 4, 5)
val sum = numbers.sum()
```

### Read from console
```kotlin
val input = readLine()
```

### Type casting
```kotlin
val anyValue: Any = 42
val intValue = anyValue as? Int
```

### Elvis operator
```kotlin
val result: Int? = null
val finalResult = result ?: 0
```

### Extension Properties
```kotlin
val List<String>.secondOrNull: String?
    get() = if (size >= 2) this[1] else null
```

### Get current thread name
```kotlin
val threadName = Thread.currentThread().name
```

### Exception handling with resources
```kotlin
val file = File("example.txt")
file.bufferedReader().use { reader ->
    val content = reader.readText()
    // Process content
}
```

### Function references
```kotlin
fun isEven(n: Int) = n % 2 == 0
val checkEven: (Int) -> Boolean = ::isEven
```

### range check
```kotlin
val number = 5
if (number in 1..10) {
    println("Number is in the range 1 to 10.")
}
```

### Coroutines
```kotlin
import kotlinx.coroutines.*
fun main() {
    runBlocking {
        launch {
            delay(1000)
            println("Hello from coroutine!")
        }
    }
}
```

### Extension function for JSON parsing
```kotlin
import com.fasterxml.jackson.module.kotlin.jacksonObjectMapper

inline fun <reified T> String.fromJson(): T =
    jacksonObjectMapper().readValue(this, T::class.java)

val json = "{\"name\":\"Alice\", \"age\":30}"
val person = json.fromJson<Person>()
```

### Function wtih a generic type constraint
```kotlin
fun <T : Number> add(a: T, b: T): T {
    return when (a) {
        is Double -> a + b as T
        is Float -> a + b as T
        is Long -> a + b as T
        else -> a.toInt() + b.toInt() as T
    }
}

val result = add(1.5, 2.5)
```

### Singleton object
```kotlin
object Configuration {
    val apiKey = "your_api_key"
}

val apiKey = Configuration.apiKey
```

### Custom exception
```kotlin
class CustomException(message: String) : Exception(message)

fun someFunction() {
    throw CustomException("This is a custom exception.")
}
```

### Seaaled classes and when expression
```kotlin
sealed class Result
data class Success(val data: String) : Result()
data class Error(val message: String) : Result()

fun processResult(result: Result) {
    when (result) {
        is Success -> println("Success: ${result.data}")
        is Error -> println("Error: ${result.message}")
    }
}
```

### Function with varang parameters
```kotlin
fun sum(vararg numbers: Int): Int {
    return numbers.sum()
}

val total = sum(1, 2, 3, 4, 5)
```

### Inline function
```kotlin
inline fun measureTimeMillis(block: () -> Unit): Long {
    val startTime = System.currentTimeMillis()
    block()
    return System.currentTimeMillis() - startTime
}

val executionTime = measureTimeMillis {
    // Code to measure execution time
}
```

### Delegated properties
```kotlin
class User {
    var name: String by Delegates.observable("John") { _, old, new ->
        println("Name changed from $old to $new")
    }
}

val user = User()
user.name = "Alice"
```

### Lazy initialization
```kotlin
val expensiveData: String by lazy {
    // Initialize expensive data
    "This data took some time to initialize"
}

// Access expensiveData when needed
val result = expensiveData.length
```

### Coroutines with deferred result
```kotlin
import kotlinx.coroutines.*
fun asyncTask(): Deferred<String> = GlobalScope.async {
    delay(1000)
    return@async "Task completed"
}

val result = runBlocking {
    val deferred = asyncTask()
    deferred.await()
}
```

### Extension function on collections
```kotlin
fun <T> List<T>.customFilter(predicate: (T) -> Boolean): List<T> {
    val filteredList = mutableListOf<T>()
    for (item in this) {
        if (predicate(item)) {
            filteredList.add(item)
        }
    }
    return filteredList
}

val numbers = listOf(1, 2, 3, 4, 5)
val evenNumbers = numbers.customFilter { it % 2 == 0 }
```

### Using sequence for lazy evaluation
```kotlin
val numbers = sequence {
    yield(1)
    yield(2)
    yield(3)
}

val sum = numbers.sum()
```

### Reflection
```kotlin
class Person(val name: String, val age: Int)

val person = Person("Alice", 30)
val clazz = person::class
val properties = clazz.memberProperties
```

### Higher-Order Functions
```kotlin
fun doOperation(value: Int, operation: (Int) -> Int): Int {
    return operation(value)
}

val result = doOperation(5) { it * 2 }
```

### Companion object
```kotlin
class MyClass {
    companion object {
        fun staticFunction() {
            println("This is a static function")
        }
    }
}

MyClass.staticFunction()
```

### Function with reified type parameter
```kotlin
inline fun <reified T> printType() {
    println(T::class.simpleName)
}

printType<String>() // Prints "String"
```

### Custom operator overload
```kotlin
data class Vector(val x: Int, val y: Int)

operator fun Vector.plus(other: Vector): Vector {
    return Vector(this.x + other.x, this.y + other.y)
}

val result = Vector(1, 2) + Vector(3, 4)
```

### Immutable collections
```kotlin
val immutableList = listOf("apple", "banana", "cherry")
val modifiedList = immutableList.toMutableList()
modifiedList.add("date")
```

### Data classes
```kotlin
data class Point(val x: Int, val y: Int)

val point1 = Point(1, 2)
val point2 = Point(1, 2)
val areEqual = (point1 == point2) // true
```

### Inline classes
```kotlin
inline class Meter(val value: Double)

val length = Meter(5.0)
val doubleValue: Double = length.value
```


