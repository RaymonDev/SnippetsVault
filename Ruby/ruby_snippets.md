## Ruby

### Hello World
```ruby
puts "Hello World!"
```

### Variables
```ruby
age = 30
name = "John"
```

### User input
```ruby
print "Enter something: "
user_input = gets.chomp
```

### If-else
```ruby
if age >= 18
  puts "You are an adult."
else
  puts "You are a minor."
end
```

### For loop
```ruby
for i in 0..4
  puts i
end
```

### While loop
```ruby
count = 0
while count < 5
  puts count
  count += 1
end
```

### Arrays
```ruby
numbers = [1, 2, 3, 4, 5]
```

### Array access
```ruby
first_number = numbers[0]
```

### Functions
```ruby
def add(a, b)
  a + b
end
```

### Object oriented programming
```ruby
class Person
  attr_accessor :name, :age
  def greet
    puts "Hello, my name is #{@name}."
  end
end
```

### Contructors and Object Initialization
```ruby
class Person
  attr_accessor :name, :age
  def initialize(name, age)
    @name = name
    @age = age
  end
end
```

### Inheritance
```ruby
class Student < Person
  attr_accessor :school
end
```

### List (Arrays)
```ruby
fruits = ["apple", "banana", "cherry", "date", "fig"]
```

### List operations (Add, Remove)
```ruby
fruits.push("grape")
fruits.delete("cherry")
```

### List iteration
```ruby
fruits.each do |fruit|
  puts fruit
end
```

### Hashes (dictionaries)
```ruby
scores = {"Alice" => 95, "Bob" => 88, "Charlie" => 72}
```

### Hash access and iteration
```ruby
scores.each do |name, score|
  puts "#{name}: #{score}"
end
```

### String Manipulation
```ruby
text = "Hello, World!"
substring = text[0..4]
```

### String concatenation
```ruby
greeting = "Hello"
name = "Alice"
message = "#{greeting}, #{name}!"
```

### DateTime
```ruby
current_time = Time.now
```

### Exception Handling (begin-rescue)
```ruby
begin
  result = 10 / 0
rescue => e
  puts "Error: #{e.message}"
end
```

### File reading
```ruby
file = File.open("example.txt", "r")
content = file.read
file.close
```

###File writing
```ruby
file = File.open("output.txt", "w")
file.puts "This is some text."
file.close
```

### Working with Enums
```ruby
module DaysOfWeek
  MONDAY = 0
  TUESDAY = 1
  WEDNESDAY = 2
  THURSDAY = 3
  FRIDAY = 4
  SATURDAY = 5
  SUNDAY = 6
end
```

### Regular Expressions
```ruby
text = "My email is example@example.com."
email_regex = /\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}\b/
is_email = email_regex.match?(text)
```

### Working with sets
```ruby
require 'set'
unique_numbers = Set.new([1, 2, 3, 4, 5])
```

### Set operations (intersection)
```ruby
set1 = Set.new([1, 2, 3])
set2 = Set.new([2, 3, 4])
intersection = set1 & set2
```

### command-line arguments
```ruby
if ARGV.length > 0
  arg1 = ARGV[0]
  # Process command-line arguments
end
```

### Random number generation
```ruby
random_number = rand(1..10)
```

### Working with symbols
```ruby
status = :success
```

### Enumerable methods (maps)
```ruby
numbers = [1, 2, 3, 4, 5]
squared_numbers = numbers.map { |n| n * n }
```

### Enumerable methods (select)
```ruby
numbers = [1, 2, 3, 4, 5]
even_numbers = numbers.select { |n| n.even? }
```

### Enumerable methods (reduce)
```ruby
numbers = [1, 2, 3, 4, 5]
sum = numbers.reduce(0) { |total, n| total + n }
```

### Blocks and Yield
```ruby
def custom_each(arr)
  for item in arr
    yield(item)
  end
end
custom_each([1, 2, 3]) { |x| puts x }
```

### Procs and Lambdas
```ruby
add = Proc.new { |a, b| a + b }
result = add.call(3, 4)
```

### Modules and Mixins
```ruby
module Greetable
  def greet
    puts "Hello!"
  end
end
class Person
  include Greetable
end
```

### Custom exceptions
```ruby
class CustomException < StandardError
  def initialize(message)
    super(message)
  end
end
begin
  raise CustomException.new("Custom exception occurred.")
rescue CustomException => e
  puts "Error: #{e.message}"
end
```

### JSON serialization and deserialization
```ruby
require 'json'
data = { "name" => "Alice", "age" => 30 }
json_string = data.to_json
parsed_data = JSON.parse(json_string)
```

### Working with Timezones
```ruby
require 'tzinfo'
tz = TZInfo::Timezone.get('America/New_York')
time_in_ny = tz.utc_to_local(Time.now.utc)
```

### Working with Threads
```ruby
t1 = Thread.new { puts "Thread 1" }
t2 = Thread.new { puts "Thread 2" }
t1.join
t2.join
```

### Functional Programming (Map, Reduce, Filter)
```ruby
numbers = [1, 2, 3, 4, 5]
squared_numbers = numbers.map { |n| n * n }
total = numbers.reduce(0) { |sum, n| sum + n }
even_numbers = numbers.select(&:even?)
```

### Modules and Namespace Resolution
```ruby
module MyModule
  def self.my_method
    puts "MyModule.my_method"
  end
end
MyModule.my_method
```

### Method missing and dynamic methods
```ruby
class DynamicMethods
  def method_missing(method_name, *args)
    puts "Calling method: #{method_name}"
  end
end
obj = DynamicMethods.new
obj.some_dynamic_method
```

### Singleton classes and methods
```ruby
class MyClass
  def self.my_class_method
    puts "This is a class method."
  end
end
obj = MyClass.new
def obj.my_singleton_method
  puts "This is a singleton method."
end
```

### Metaprogramming with define_method
```ruby
class MyClass
  define_method :dynamic_method do |arg|
    puts "Dynamic method called with argument: #{arg}"
  end
end
obj = MyClass.new
obj.dynamic_method("Hello, Metaprogramming!")
```

### Custom enumerators
```ruby
class MyEnumerator
  include Enumerable
  def each
    yield 1
    yield 2
    yield 3
  end
end
enum = MyEnumerator.new
enum.each { |x| puts x }
```

### Memoization with Hashes
```ruby
def fibonacci(n, memo = {})
  return n if n <= 1
  memo[n] ||= fibonacci(n - 1, memo) + fibonacci(n - 2, memo)
end
```

### Closures with Lambdas
```ruby
def closure_example
  x = 10
  lambda { |y| puts x + y }
end
closure = closure_example
closure.call(5)
```

### Functional programming (currying)
```ruby
add = lambda { |x| lambda { |y| x + y } }
add_five = add.call(5)
result = add_five.call(3)
```

### Method chaining
```ruby
class Calculator
  attr_accessor :value
  def initialize(value)
    @value = value
  end
  def add(x)
    @value += x
    self
  end
  def subtract(x)
    @value -= x
    self
  end
end
result = Calculator.new(10).add(5).subtract(3).value
```

### Custom exceptions and error handling
```ruby
class CustomException < StandardError
  def initialize(message)
    super(message)
  end
end
begin
  raise CustomException, "Custom exception occurred."
rescue CustomException => e
  puts "Error: #{e.message}"
end
```

### Asynchronous Programming with Fibers (Fiber, Fiber.yield)
```ruby
fiber = Fiber.new do
  puts "Fiber started"
  Fiber.yield
  puts "Fiber resumed"
end
puts "Main started"
fiber.resume
puts "Main resumed"
```

### Multithreading with Threads and Mutexes
```ruby
mutex = Mutex.new
counter = 0
threads = []
10.times do
  threads << Thread.new do
    mutex.synchronize { counter += 1 }
  end
end
threads.each(&:join)
puts "Counter: #{counter}"
```

### Working with symbols
```ruby
numbers = [1, 2, 3, 4, 5]
squared_numbers = numbers.map(&:**2)
```

### File I/O with Blocks (File.open)
```ruby
File.open("example.txt", "r") do |file|
  content = file.read
end
```

### Enumerable methods (reduce with symbols)
```ruby
numbers = [1, 2, 3, 4, 5]
total = numbers.reduce(:+)
```

### Custom Operators (Overloading)
```ruby
class Complex
  attr_accessor :real, :imag
  def initialize(real, imag)
    @real = real
    @imag = imag
  end
  def +(other)
    Complex.new(@real + other.real, @imag + other.imag)
  end
end
```

### Working with Sets (Set.intersection)
```ruby
require 'set'
set1 = Set.new([1, 2, 3])
set2 = Set.new([2, 3, 4])
intersection = set1.intersection(set2)
```

### Working with Dates and Times (Time.zone)
```ruby
require 'active_support/time'
Time.zone = 'Eastern Time (US & Canada)'
current_time = Time.zone.now
```

### Using tap for Method Chaining and Debugging
```ruby
array = [1, 2, 3]
result = array.tap { |a| a << 4 }.map { |x| x * 2 }
```