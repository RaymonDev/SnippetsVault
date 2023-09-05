## Scala

### Hello World
```scala
object HelloWorld extends App {
  println("Hello, World!")
}
```

### Variable declaration
```scala
val pi = 3.14159
var count = 0
```

### Basic data types
```scala
val num: Int = 42
val name: String = "John"
val isTrue: Boolean = true
```

### String interpolation
```scala
val name = "Alice"
println(s"Hello, $name!")
```

### Conditional statements
```scala
val age = 18
if (age >= 18) {
  println("You're an adult.")
} else {
  println("You're a minor.")
}
```

### Pattern Matching (Similar to Switch)
```scala
val day = 2
day match {
  case 1 => println("Monday")
  case 2 => println("Tuesday")
  case _ => println("Other day")
}
```

### For loop
```scala
for (i <- 1 to 5) {
  println(i)
}
```

### While loop
```scala
var i = 0
while (i < 5) {
  println(i)
  i += 1
}
```

### Function declaration
```scala
def add(a: Int, b: Int): Int = {
  a + b
}
```

### Anonymous function
```scala
val multiply = (a: Int, b: Int) => a * b
val result = multiply(5, 3)
```

### lists
```scala
val fruits = List("apple", "banana", "cherry")
val firstFruit = fruits.head
```

### Maps
```scala
val scores = Map("Alice" -> 95, "Bob" -> 85, "Carol" -> 90)
val aliceScore = scores("Alice")
```

### Option for handling nulls
```scala
val maybeName: Option[String] = Some("Alice")
val length = maybeName.getOrElse("").length
```

### Class declaration
```scala
class Person(val name: String, var age: Int)
val person = new Person("John", 30)
```

### Inheritance
```scala
class Animal(val name: String)
class Dog(name: String, val breed: String) extends Animal(name)
```

### Trait (Similar to Interface)
```scala
trait Shape {
  def area(): Double
}
```

### Enumerations
```scala
 object Color extends Enumeration {
  val RED, GREEN, BLUE = Value
}
val selectedColor = Color.RED
```

### Try-catch
```scala
try {
  // Code that may throw an exception
} catch {
  case e: Exception => // Handle the exception
}
```

### File IO
```scala
val text = scala.io.Source.fromFile("data.txt").mkString
import java.io._
val writer = new PrintWriter(new File("output.txt"))
writer.write("Hello, World!")
writer.close()
```

### Case classes (Immutable data structures)
```scala
case class Point(x: Int, y: Int)
val point1 = Point(1, 2)
val point2 = Point(1, 2)
val areEqual = point1 == point2 // true
```

### Option and match for safe value retrieval
```scala
val maybeValue: Option[Int] = Some(42)
val result = maybeValue match {
  case Some(value) => value
  case None => 0
}
```

### Filter List
```scala
val numbers = List(1, 2, 3, 4, 5)
val evenNumbers = numbers.filter(_ % 2 == 0)
```

### Map List
```scala
val numbers = List(1, 2, 3, 4, 5)
val squaredNumbers = numbers.map(x => x * x)
```

### Sort List
```scala
val names = List("Alice", "Bob", "Carol")
val sortedNames = names.sorted
```

### String operations
```scala
val text = "Scala is awesome"
val upperCaseText = text.toUpperCase
val words = text.split(" ")
```

### Regular expressions
```scala
val regex = """\d+""".r
val matchResult = regex.findFirstIn("Age: 30")
```

### Date and Time (using java.time)
```scala
import java.time._
val currentDate = LocalDate.now
```

### Random numbers
```scala
import scala.util.Random
val random = Random.nextInt(10)
```

### Multiline strings
```scala
val multilineText =
  """
    This is a
    multiline string.
  """
```

### Break and Continue (Not Natively Supported)
```scala
// Use custom breakable and continue constructs
import util.control.Breaks._

breakable {
  for (i <- 1 to 10) {
    if (i == 5) break
    println(i)
  }
}
```

### Collections operations (e.g., sum)
```scala
val numbers = List(1, 2, 3, 4, 5)
val sum = numbers.sum
```

### read from console
```scala
val input = scala.io.StdIn.readLine()
```

### Type casting (AsInstanceOf)
```scala
val anyValue: Any = 42
val intValue = anyValue.asInstanceOf[Int]
```

### Elivs operator (not natively supported)
```scala
// Use Option to emulate Elvis operator
val result = Option(maybeValue).getOrElse(0)
```

### Custom control structures
```scala
def customLoop(n: Int)(body: => Unit): Unit = {
  var i = 0
  while (i < n) {
    body
    i += 1
  }
}

customLoop(5) {
  println("Custom loop iteration")
}
```

### Exception handling with resources (Try-With-Resources)
```scala
import scala.util.Using
import java.io._

Using(new PrintWriter(new File("output.txt"))) { writer =>
  writer.write("Hello, World!")
}
```

### Futures and async programming
```scala
import scala.concurrent.Future
import scala.concurrent.ExecutionContext.Implicits.global

val futureResult: Future[Int] = Future {
  // Perform asynchronous operation
  42
}

futureResult.onComplete {
  case scala.util.Success(result) => println(s"Result: $result")
  case scala.util.Failure(exception) => println(s"Error: $exception")
}
```

### Pattern matching with case classes
```scala
case class Message(sender: String, content: String)
val message = Message("Alice", "Hello, Bob!")
message match {
  case Message("Alice", _) => println("Received message from Alice")
  case Message(_, _) => println("Received message from someone else")
}
```

### Type parameters and generics
```scala
class Box[T](value: T) {
  def getValue: T = value
}

val intBox = new Box(42)
val stringValue = intBox.getValue.toString
```

### Implicits (Advanced Feature for Implicit Conversions)
```scala
implicit def intToString(i: Int): String = i.toString
val str: String = 42 // Converts int to string implicitly
```






