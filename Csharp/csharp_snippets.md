## C#

### Hello World    
```csharp
using System;
class Program {
    static void Main() {
        Console.WriteLine("Hello, World!");
    }
}
```

### Variables
```csharp
int age = 30;
string name = "John";
bool isAlive = true;
```

### User Input
```csharp
Console.Write("Enter something: ");
string userInput = Console.ReadLine();
```

### If-else Statement
```csharp
if (age >= 18) {
    Console.WriteLine("You are an adult.");
} else {
    Console.WriteLine("You are a minor.");
}
```

### For loop
```csharp
for (int i = 0; i < 5; i++) {
    Console.WriteLine(i);
}
```

### While loop
```csharp
int count = 0;
while (count < 5) {
    Console.WriteLine(count);
    count++;
}
```

### Arrays
```csharp
int[] numbers = { 1, 2, 3, 4, 5 };
string[] names = { "John", "Mary", "Bob" };
```

### Array access
```csharp
int firstNumber = numbers[0];
```

### Functions
```csharp
int Add(int a, int b) {
    return a + b;
}
```

### Object oriented programming
```csharp
class Person {
    public string Name { get; set; }
    public int Age { get; set; }
    public void Greet() {
        Console.WriteLine($"Hello, my name is {Name}.");
    }
}
```

### Constructors and object initialization
```csharp
class Person {
    public string Name { get; set; }
    public int Age { get; set; }
    public Person(string name, int age) {
        Name = name;
        Age = age;
    }
}
```

### Inheritance
```csharp
class Student : Person {
    public string School { get; set; }
}
```

### Lists (System.Collections.Generic.List)
```csharp
using System.Collections.Generic;
List<int> numbers = new List<int> { 1, 2, 3, 4, 5 };
```

###  List Operations (Add, Remove)
```csharp
numbers.Add(6);
numbers.Remove(3);
```

### List Iteration (foreach)
```csharp
foreach (int num in numbers) {
    Console.WriteLine(num);
}
```

### Dictionaries (System.Collections.Generic.Dictionary)
```csharp
using System.Collections.Generic;
Dictionary<string, int> scores = new Dictionary<string, int>();
scores["Alice"] = 95;
```

### Dictionary access and iteration
```csharp
foreach (var pair in scores) {
    Console.WriteLine($"{pair.Key}: {pair.Value}");
}
```

### String manipulation
```csharp
string text = "Hello, World!";
string upperText = text.ToUpper();
```

### String splitting
```csharp
string[] words = text.Split(new char[] { ' ', ',' });
```

### String Joining
```csharp
string[] words = { "Hello", "World" };
string joinedText = string.Join(" ", words);
```

### DateTime (System.DateTime)
```csharp
DateTime currentDate = DateTime.Now;
```

### DateTime Formatting
```csharp
string formattedDate = currentDate.ToString("yyyy-MM-dd");
```

### Exception handling
```csharp
try {
    int result = 10 / 0;
} catch (DivideByZeroException e) {
    Console.WriteLine("Error: " + e.Message);
}

### File Reading
```csharp
using System.IO;
string content = File.ReadAllText("example.txt");
```

### File Writing
```csharp
using System.IO;
File.WriteAllText("output.txt", "This is some text.");
```

### Working with Enums
```csharp
enum DaysOfWeek {
    Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday
}
```

### Enum.Parse
```csharp
DaysOfWeek day = (DaysOfWeek)Enum.Parse(typeof(DaysOfWeek), "Wednesday");
```

### LINQ (Language-Integrated Query)
```csharp
using System.Linq;
int[] numbers = { 1, 2, 3, 4, 5 };
var evenNumbers = numbers.Where(n => n % 2 == 0);
```

### LINQ (Select Projection)
```csharp
using System.Linq;
int[] numbers = { 1, 2, 3, 4, 5 };
var squaredNumbers = numbers.Select(n => n * n);
```

### LINQ (Ordering)
```csharp
 using System.Linq;
int[] numbers = { 5, 2, 9, 1, 3 };
var sortedNumbers = numbers.OrderBy(n => n);
```

### LINQ (Grouping)
```csharp
using System.Linq;
string[] fruits = { "apple", "banana", "cherry", "date", "fig" };
var groupedByLength = fruits.GroupBy(fruit => fruit.Length);
```

### LINQ (Joining)
```csharp
using System.Linq;
var users = new[] { new { ID = 1, Name = "Alice" }, new { ID = 2, Name = "Bob" } };
var orders = new[] { new { UserID = 1, Product = "Apple" }, new { UserID = 2, Product = "Banana" } };
var joinedData = users.Join(orders, user => user.ID, order => order.UserID, (user, order) => new { user.Name, order.Product });
```

### Delegates and Events
```csharp
public delegate void MyEventHandler(object sender, EventArgs e);
public event MyEventHandler MyEvent;
```

### Custom delegates and event handlers
```csharp
public delegate int CalculationDelegate(int a, int b);
public int Add(int a, int b) {
    return a + b;
}
CalculationDelegate calc = Add;
int result = calc(5, 3);
```

### Asynchronous Programming (async/await)
```csharp
using System;
using System.Threading.Tasks;
async Task<int> LongRunningOperationAsync() {
    await Task.Delay(2000);
    return 42;
}
```

### Async/Await Error Handling
```csharp
try {
    int result = await LongRunningOperationAsync();
    Console.WriteLine(result);
} catch (Exception ex) {
    Console.WriteLine("Error: " + ex.Message);
}
```

### Attributes and Reflection
```csharp
[Serializable]
public class MyClass { }
Type type = typeof(MyClass);
Attribute[] attributes = Attribute.GetCustomAttributes(type);
```

### Working with Nullable Types
```csharp
int? nullableInt = null;
if (nullableInt.HasValue) {
    int value = nullableInt.Value;
}
```

### Extension Methods
```csharp
public static class StringExtensions {
    public static bool IsPalindrome(this string str) {
        // Check if the string is a palindrome
    }
}
```

### IDisposable and using
```csharp
using (var resource = new DisposableResource()) {
    // Use the resource
}
```

### Interoperability with Unmanaged Code (DllImport)
```csharp
using System.Runtime.InteropServices;
[DllImport("user32.dll")]
static extern bool SetWindowText(IntPtr hWnd, string lpString);
```

### Lambda Expressions with LINQ (C# 3.0+)
```csharp
using System;
using System.Linq;
var numbers = new[] { 1, 2, 3, 4, 5 };
var evenNumbers = numbers.Where(n => n % 2 == 0);
```

### LINQ Query Syntax (C# 3.0+)
```csharp
using System;
using System.Linq;
var numbers = new[] { 1, 2, 3, 4, 5 };
var evenNumbers = from num in numbers where num % 2 == 0 select num;
```

###  Extension Methods with LINQ (C# 3.0+)
```csharp
using System;
using System.Linq;
public static class EnumerableExtensions {
    public static int CustomSum(this IEnumerable<int> source) {
        int sum = 0;
        foreach (int num in source) {
            sum += num;
        }
        return sum;
    }
}
var numbers = new[] { 1, 2, 3, 4, 5 };
int sum = numbers.CustomSum();
```

### Delegates and Anonymous Methods (C# 2.0+)
```csharp
public delegate void MyDelegate(string message);
public static void DisplayMessage(string message) {
    Console.WriteLine(message);
}
MyDelegate del = DisplayMessage;
del("Hello, delegate!");
```

### Events and Event Handlers (C# 2.0+)
```csharp
public class EventPublisher {
    public event EventHandler MyEvent;
    public void RaiseEvent() {
        MyEvent?.Invoke(this, EventArgs.Empty);
    }
}
public class EventSubscriber {
    public void Subscribe(EventPublisher publisher) {
        publisher.MyEvent += HandleEvent;
    }
    private void HandleEvent(object sender, EventArgs e) {
        Console.WriteLine("Event handled.");
    }
}
```

### Custom Events and Event Arguments (C# 2.0+)
```csharp
public class CustomEventArgs : EventArgs {
    public string Message { get; }
    public CustomEventArgs(string message) {
        Message = message;
    }
}
public class CustomEventPublisher {
    public event EventHandler<CustomEventArgs> CustomEvent;
    public void RaiseCustomEvent() {
        CustomEvent?.Invoke(this, new CustomEventArgs("Custom event raised."));
    }
}
public class CustomEventSubscriber {
    public void Subscribe(CustomEventPublisher publisher) {
        publisher.CustomEvent += HandleCustomEvent;
    }
    private void HandleCustomEvent(object sender, CustomEventArgs e) {
        Console.WriteLine("Custom event handled: " + e.Message);
    }
}
```

### Delegates and Multicast Delegates (C# 2.0+)
```csharp
public delegate void MathOperation(int a, int b);
public static void Add(int a, int b) {
    Console.WriteLine("Addition: " + (a + b));
}
public static void Subtract(int a, int b) {
    Console.WriteLine("Subtraction: " + (a - b));
}
MathOperation mathDel = Add;
mathDel += Subtract;
mathDel(10, 5); // Calls both Add and Subtract
```

### Asynchronous Programming with async/await (C# 5.0+)
```csharp
using System;
using System.Threading.Tasks;
async Task<int> LongRunningOperationAsync() {
    await Task.Delay(2000);
    return 42;
}
async Task Main() {
    int result = await LongRunningOperationAsync();
    Console.WriteLine(result);
}
```

### Asynchronous Streams (C# 8.0+)
```csharp
using System;
using System.Collections.Generic;
using System.Linq;
async IAsyncEnumerable<int> GenerateNumbersAsync() {
    for (int i = 0; i < 5; i++) {
        await Task.Delay(1000);
        yield return i;
    }
}
await foreach (var number in GenerateNumbersAsync()) {
    Console.WriteLine(number);
}
```

### Value Tuples (C# 7.0+)
```csharp
var person = ("Alice", 25);
Console.WriteLine($"Name: {person.Item1}, Age: {person.Item2}");
```

###  Pattern Matching (C# 7.0+)
```csharp
object data = "Hello, World!";
if (data is string text) {
    Console.WriteLine($"Length: {text.Length}");
}
```

### Discards (C# 7.0+)
```csharp
_ = PerformOperation();
```

### Null Conditional Operator (C# 6.0+)
```csharp
string name = person?.Name;
```

### Expression-Bodied Members (C# 6.0+)
```csharp
public class Calculator {
    public int Add(int a, int b) => a + b;
}
```

### Tuple Deconstruction (C# 7.0+)
```csharp
var (x, y) = GetCoordinates();
```

### C# Records (C# 9.0+)
```csharp
public record Person(string Name, int Age);
var person1 = new Person("Alice", 25);
var person2 = new Person("Alice", 25);
bool areEqual = person1 == person2;
```

### Interpolated Strings (C# 6.0+)
```csharp
string name = "Alice";
int age = 25;
Console.WriteLine($"Name: {name}, Age: {age}");
```

### C# 8.0 Nullable Reference Types
```csharp
#nullable enable
string? nullableString = null;
string nonNullableString = "Hello, World!";
```

### Using Statements with IDisposable (C# 8.0+)
```csharp
using var disposableResource = new DisposableResource();
// Resource is automatically disposed when leaving this block
```

### Asynchronous Disposal (C# 8.0+)
```csharp
await using var asyncDisposable = new AsyncDisposableResource();
await asyncDisposable.DisposeAsync();
```