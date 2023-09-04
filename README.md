<div align="center">
    <h1>Snippet Vault</h1>
    <i>Your go-to collection of code snippets in various programming languages for quick reference and learning.</i>
</div>

<br />

---

<br />

## Index

* [Python](#python)
* [Java](#java)
* [JavaScript](#javascript)
* C++
* C#
* Ruby
* Go (Golang)
* Swift
* PHP
* Rust
* SQL
* TypeScript
* Kotlin
* Scala
* Perl
* Haskell
* Swift
* HTML
* CSS
* R
* MATLAB
* Assembly

<br />

---

<br />

## Python

### Hello World
```python
print("Hello, World!")
```
### Variables
```python
name = "John"
age = 30
```
### User Input
```python
user_input = input("Enter something: ")
```

### String Concatenation
```python
first_name = "John"
last_name = "Doe"
full_name = first_name + " " + last_name
```

### List Creation
```python
my_list = [1, 2, 3, 4, 5]
```

### List Slicing
```python
subset = my_list[1:3]
```

### List comprehension
```python
squared_numbers = [x**2 for x in my_list]
```

### Conditional Statements
```python
if age > 18:
    print("You are an adult.")
elif age == 18:
    print("You are 18.")
else:
    print("You are under 18.")
```

### For loop
```python
for i in range(10):
    print(i)
```

### While loop
```python
count = 0
while count < 10:
    print(count)
    count += 1
```

### Functions
```python
def greet(name):
    return "Hello, " + name + "!"
```

### File reading
```python
with open("file.txt", "r") as file:
    content = file.read()
```

### File writing
```python
with open("output.txt", "w") as file:
    file.write("Hello, World!")
```

### Exception handling
```python
try:
    print(1/0)
except ZeroDivisionError:
    print("Cannot divide by zero.")
```

### Dictionaries
```python
my_dict = {
    "name": "John",
    "age": 30
}
```

### Dictionary access
```python
name = my_dict["name"]
```

### Dictionary iteration
```python
for key, value in my_dict.items():
    print(key, value)
```

### Sets
```python
my_set = {1, 2, 3, 4, 5}
```

### Set operations
```python
intersection = my_set.intersection({4, 5, 6})
```

### Tuples
```python
coordinates = (10, 20)
```

### Lambda functions
```python
square = lambda x: x**2
```

### List Sorting
```python
my_list.sort()
```

### String Manipulation
```python
my_string = "Hello, World!"
upper_text = my_string.upper()
```

### List reversal
```python
reversed_list = my_list[::-1]
```

### Finding Maximum
```python
max_value = max(my_list)
```

### Finding Minimum
```python
min_value = min(my_list)
```

### List Length
```python
length = len(my_list)
```

### List removal
```python
my_list.remove(3)
```

### List Appending
```python
my_list.append(6)
```

### List copying
```python
my_list_copy = my_list.copy()
```

### List clearing
```python
my_list.clear()
```

### String Splitting
```python
words = my_string.split(", ")
```

### String Joining
```python
my_string = ", ".join(words)
```

### String Formatting
```python
name = "John"
age = 30
my_string = f"Hello, my name is {name} and I am {age} years old."
```

### Math Operations
```python
result = abs(-5)
```

### Random number generation
```python
import random
random_number = random.randint(1, 10)
```

### Date and Time
```python
from datetime import datetime
current_time = datetime.now()
```

### List unique values
```python
unique_values = list(set(my_list))
```

### Checking if a file exists
```python
import os
if os.path.exists("file.txt"):
    print("File exists.")
```

### Removing duplicates from a list
```python
unique_values = list(dict.fromkeys(my_list))
```

### List flattening
```python
flat_list = [item for sublist in my_list for item in sublist]
```

### List filtering
```python
filtered_list = list(filter(lambda x: x > 5, my_list))
```

### List mapping
```python
mapped_list = list(map(lambda x: x**2, my_list))
```

### List comprehension with condition
```python
even_numbers = [x for x in range(10) if x % 2 == 0]
```

### Using generators
```python
def squares(n):
    for i in range(n):
        yield i**2
```

### Handling JSON data
```python
import json
data = {"name": "John", "age": 30}
json_data = json.dumps(data)
```

### Reading JSON data
```python
import json
with open("data.json", "r") as file:
    data = json.load(file)
```

### Reading and writting CSV files
```python
import csv

# Reading CSV
with open("data.csv", "r") as csvfile:
    reader = csv.DictReader(csvfile)
    for row in reader:
        print(row["name"], row["age"])

# Writing CSV
data = [{"name": "Alice", "age": 25}, {"name": "Bob", "age": 32}]
with open("output.csv", "w", newline="") as csvfile:
    fieldnames = ["name", "age"]
    writer = csv.DictWriter(csvfile, fieldnames=fieldnames)
    writer.writeheader()
    for row in data:
        writer.writerow(row)
```

### Object-Oriented Programming (OOP)
```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def greet(self):
        return f"Hello, my name is {self.name}."

person = Person("Alice", 28)
print(person.greet())
```

### Decorators
```python
def log_function_call(func):
    def wrapper(*args, **kwargs):
        result = func(*args, **kwargs)
        print(f"Calling {func.__name__} with arguments {args} returned {result}.")
        return result
    return wrapper

@log_function_call
def add(a, b):
    return a + b
```

### Threading
```python
import threading

def print_numbers():
    for i in range(1, 6):
        print(f"Number {i}")

def print_letters():
    for letter in "abcde":
        print(f"Letter {letter}")

thread1 = threading.Thread(target=print_numbers)
thread2 = threading.Thread(target=print_letters)
```

### Exception Handling with Custom Exceptions:
```python
class CustomError(Exception):
    def __init__(self, message):
        super().__init__(message)

try:
    raise CustomError("This is a custom exception.")
except CustomError as e:
    print(e)
```

### Working with Context Managers:
```python
class MyContext:
    def __enter__(self):
        print("Entering the context")
        return self

    def __exit__(self, exc_type, exc_value, traceback):
        print("Exiting the context")

with MyContext() as context:
    print("Inside the context")
```

### Multithreading with the concurrent.futures module:
```python
import concurrent.futures

def square(x):
    return x**2

with concurrent.futures.ThreadPoolExecutor() as executor:
    results = executor.map(square, [1, 2, 3, 4, 5])
```

### Working with Regular Expressions:
```python
import re

pattern = r'\b\d{3}-\d{2}-\d{4}\b'
text = "My SSN is 123-45-6789."
match = re.search(pattern, text)
```

### Sending Email with the smtplib module:
```python
import smtplib
from email.mime.text import MIMEText

server = smtplib.SMTP("smtp.example.com")
msg = MIMEText("This is a test email.")
msg["Subject"] = "Test Email"
msg["From"] = "sender@example.com"
msg["To"] = "recipient@example.com"
server.sendmail("sender@example.com", "recipient@example.com", msg.as_string())
server.quit()
```

### Working with REST APIs using the requests library
```python
import requests

response = requests.get("https://jsonplaceholder.typicode.com/posts/1")
data = response.json()
```

### Database Connection with sqlite3
```python
import sqlite3

conn = sqlite3.connect("mydatabase.db")
cursor = conn.cursor()
cursor.execute("CREATE TABLE IF NOT EXISTS users (id INTEGER PRIMARY KEY, name TEXT, age INTEGER)")
```

### Object Serialization with the pickle module
```python
import pickle

data = {"name": "Alice", "age": 30}
with open("data.pickle", "wb") as file:
    pickle.dump(data, file)
```

### Asynchronous Programming with asyncio
```python
import asyncio

async def hello_world():
    await asyncio.sleep(1)
    print("Hello, World!")

asyncio.run(hello_world())
```

### Working with Contextlib and the @contextmanager decorator
```python
from contextlib import contextmanager

@contextmanager
def my_context():
    print("Entering the context")
    yield
    print("Exiting the context")

with my_context():
    print("Inside the context")

```

### Working with bytes and Hexadecimal
```python
data = b'Hello, World!'
hex_data = data.hex()
```

### Using collections module
```python
from collections import Counter

word_count = Counter(["apple", "banana", "apple", "cherry"])
```

### Sending POST Request with the requests library
```python
import requests

data = {"name": "Alice", "age": 25}
response = requests.post("https://example.com/api", json=data)
```

## Java

### Hello World
```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

### Variables
```java
String name = "John";
int age = 30;
```

### Conditional Statements
```java
if (age >= 18) {
    System.out.println("You are an adult.");
} else {
    System.out.println("You are a minor.");
}
```

### For loop
```java
for (int i = 0; i < 10; i++) {
    System.out.println(i);
}
```

### While loop
```java
int count = 0;
while (count < 10) {
    System.out.println(count);
    count++;
}
```

### Arrays
```java
int[] myArray = {1, 2, 3, 4, 5};
```

### Array access
```java
int firstElement = myArray[0];
```

### List (ArrayList)
```java
import java.util.ArrayList;
ArrayList<String> names = new ArrayList<>();
```

### List (ArrayList) Operations
```java
names.add("Alice");
names.remove("Bob");
```

### Functions (Methods)
```java
public static int add(int a, int b) {
    return a + b;
}
```

### File reading(Java 7+)
```java
import java.nio.file.*;
String content = Files.readString(Paths.get("file.txt"));
```

### File writing(Java 7+)
```java
import java.nio.file.*;
Files.write(Paths.get("output.txt"), "Hello, World!".getBytes());
```

### Exeption Handling
```java
try {
    int result = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Error: Division by zero");
}
```

### Classes and Objects
```java
public class Person {
    String name;
    int age;
}
```

### Object creation
```java
Person person = new Person();
person.name = "Alice";
person.age = 25;
```

### Object methods
```java
public void greet() {
    System.out.println("Hello, my name is " + name);
}
```

### Inheritance
```java
public class Student extends Person {
    String school;
}
```

### Interfaces
```java
public interface Drawable {
    void draw();
}
```

### Lambda Expressions (Java 8+)
```java
Runnable runnable = () -> {
    System.out.println("Running a task");
};
```

### Sorting arrays
```java
import java.util.Arrays;
int[] sortedNumbers = Arrays.copyOf(numbers, numbers.length);
Arrays.sort(sortedNumbers);
```

### String Manipulation
```java
String text = "Hello, World!";
String upperText = text.toUpperCase();
```

### List reversal
```java
Collections.reverse(numbersList);
```

### Finding Maximum
```java
int max = Collections.max(numbersList);
```

### Finding Minimum
```java
int min = Collections.min(numbersList);
```

### List Length
```java
int listSize = numbersList.size();
```

### List removal
```java
numbersList.remove(3);
```

### List Appending
```java
numbersList.add(6);
```

### List copying
```java
ArrayList<Integer> copiedList = new ArrayList<>(numbersList);
```

### List clearing
```java
numbersList.clear();
```

### String Splitting
```java
String[] words = text.split(", ");
```

### String Joining
```java
String joinedText = String.join(", ", words);
```

### String Formatting
```java
String formattedText = String.format("My name is %s and I am %d years old.", name, age);
```

### Math Operations
```java
int absoluteValue = Math.abs(-5);
```

### Random number generation
```java
import java.util.Random;
Random random = new Random();
int randomNumber = random.nextInt(100);
```

### Date and Time (Java 8+)
```java
import java.time.LocalDateTime;
LocalDateTime currentTime = LocalDateTime.now();
```

### Set (HashSet)
```java
import java.util.HashSet;
HashSet<String> uniqueNames = new HashSet<>();
```

### Set operations
```java
uniqueNames.add("Alice");
uniqueNames.remove("Bob");
```

### Map (HashMap)
```java
import java.util.HashMap;
HashMap<String, Integer> scoreMap = new HashMap<>();
```

### Map operations
```java
scoreMap.put("Alice", 95);
int aliceScore = scoreMap.get("Alice");
```

### List Comprehension with Streams (Java 8+) 
```java
List<Integer> evenNumbers = numbersList.stream()
    .filter(n -> n % 2 == 0)
    .collect(Collectors.toList());
```

### Multithreading with Thread class
```java
Thread thread1 = new Thread(() -> {
    for (int i = 0; i < 5; i++) {
        System.out.println("Thread 1: " + i);
    }
});
thread1.start();
```

### Multithreading with ExecutorService
```java
ExecutorService executorService = Executors.newFixedThreadPool(2);
executorService.submit(() -> System.out.println("Task 1"));
executorService.submit(() -> System.out.println("Task 2"));
executorService.shutdown();
```

### Exception Handling with Custom Exceptions:
```java
class CustomException extends Exception {
    public CustomException(String message) {
        super(message);
    }
}

try {
    throw new CustomException("This is a custom exception.");
} catch (CustomException e) {
    System.out.println(e.getMessage());
}
```

### Working with Date and Time using the java.time package:
```java
import java.time.LocalDate;
LocalDate today = LocalDate.now();
```

### File reading with buffered reader
```java
import java.io.BufferedReader;
import java.io.FileReader;
try (BufferedReader br = new BufferedReader(new FileReader("file.txt"))) {
    String line;
    while ((line = br.readLine()) != null) {
        System.out.println(line);
    }
}
```

### File writing with buffered writer
```java
import java.io.BufferedWriter;
import java.io.FileWriter;
try (BufferedWriter bw = new BufferedWriter(new FileWriter("output.txt"))) {
    bw.write("This is some text.");
}
```

### Serializing and Deserializing Objects
```java
import java.io.*;
class Person implements Serializable {
    String name;
    int age;
}
// Serialization
Person person = new Person();
try (ObjectOutputStream out = new ObjectOutputStream(new FileOutputStream("person.ser"))) {
    out.writeObject(person);
}
// Deserialization
try (ObjectInputStream in = new ObjectInputStream(new FileInputStream("person.ser"))) {
    Person deserializedPerson = (Person) in.readObject();
}
```

### Database connection with JDBC
```java
import java.sql.*;
String url = "jdbc:mysql://localhost:3306/mydb";
String user = "username";
String password = "password";
try (Connection connection = DriverManager.getConnection(url, user, password);
     Statement statement = connection.createStatement()) {
    ResultSet resultSet = statement.executeQuery("SELECT * FROM users");
    while (resultSet.next()) {
        String name = resultSet.getString("name");
        int age = resultSet.getInt("age");
    }
}
```

### Working with regular expressions
```java
import java.util.regex.*;
Pattern pattern = Pattern.compile("\\b\\d{3}-\\d{2}-\\d{4}\\b");
Matcher matcher = pattern.matcher("My SSN is 123-45-6789.");
boolean found = matcher.find();
```

### Sending email with JavaMail API
```java
import javax.mail.*;
import javax.mail.internet.*;
Properties properties = new Properties();
properties.put("mail.smtp.host", "smtp.example.com");
Session session = Session.getInstance(properties);
MimeMessage message = new MimeMessage(session);
message.setFrom(new InternetAddress("sender@example.com"));
message.addRecipient(Message.RecipientType.TO, new InternetAddress("recipient@example.com"));
message.setSubject("Test Email");
message.setText("This is a test email.");
Transport.send(message);
```

### Working with JSON using Gson (Google JSON library)
```java
import com.google.gson.*;
JsonObject jsonObject = new JsonObject();
jsonObject.addProperty("name", "Alice");
jsonObject.addProperty("age", 25);
String jsonString = jsonObject.toString();
```

### Creating and using Enums:
```java
enum DaysOfWeek {
    MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY
}
```

### Working with Collections (Java Collections Framework)
```java
List<String> names = new ArrayList<>();
Map<String, Integer> scores = new HashMap<>();
Set<String> uniqueNames = new HashSet<>();
```

### Using try-with-resources for Auto-Closable Resources
```java
try (BufferedReader br = new BufferedReader(new FileReader("file.txt"));
     BufferedWriter bw = new BufferedWriter(new FileWriter("output.txt"))) {
    String line;
    while ((line = br.readLine()) != null) {
        bw.write(line);
    }
}
```

### Sorting Collections (e.g.,'Collections.sort()')
```java
List<Integer> numbers = new ArrayList<>();
Collections.sort(numbers);
```

### Using Java Streams and Collectors (Java 8+)
```java
List<String> fruits = Arrays.asList("apple", "banana", "cherry");
List<String> filteredFruits = fruits.stream()
    .filter(fruit -> !fruit.equals("banana"))
    .collect(Collectors.toList());
```

### Functional interfaces and Lambdas (Java8+)
```java
@FunctionalInterface
interface MathOperation {
    int operate(int a, int b);
}
MathOperation addition = (a, b) -> a + b;
```

### Working with threads and synchronization
```java
class Counter {
    private int count = 0;
    public synchronized void increment() {
        count++;
    }
}
```

### Handling Date and Time Zones (Java 8+)
```java
import java.time.ZoneId;
ZoneId zoneId = ZoneId.of("America/New_York");
```

## JavaScript

