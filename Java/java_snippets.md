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