## C++

### Hello World
```cpp
#include <iostream>
int main() {
    std::cout << "Hello, World!" << std::endl;
    return 0;
}
```

### Variables
```cpp
int age = 30;
std::string name = "John";
```

### if-else
```cpp
if (age >= 18) {
    std::cout << "You are an adult." << std::endl;
} else {
    std::cout << "You are a minor." << std::endl;
}
```

### For loop
```cpp
for (int i = 0; i < 5; i++) {
    std::cout << i << std::endl;
}
```

### Arrays
```cpp
int numbers[] = {1, 2, 3, 4, 5};
```

### Array access
```cpp
int firstNumber = numbers[0];
```

### Functions
```cpp
int add(int a, int b) {
    return a + b;
}
```

### Function overloading
```cpp
int add(int a, int b) {
    return a + b;
}

double add(double a, double b) {
    return a + b;
}
```

### Object oriented programming (OOP)
```cpp
class Person {
public:
    std::string name;
    int age;
    void greet() {
        std::cout << "Hello, my name is " << name << "." << std::endl;
    }
};
```

### Constructors and object initialization
```cpp
class Person {
public:
    std::string name;
    int age;
    Person(std::string n, int a) : name(n), age(a) {}
};
```

### Inheritance
```cpp
class Student : public Person {
public:
    std::string school;
};
```

### Function templates
```cpp
template <typename T>
T add(T a, T b) {
    return a + b;
}
```

### Exepction handling
```cpp
try {
    int result = 10 / 0;
} catch (const std::exception& e) {
    std::cerr << "Error: " << e.what() << std::endl;
}
```

### File reading
```cpp
#include <fstream>
std::ifstream file("example.txt");
std::string content;
if (file.is_open()) {
    while (std::getline(file, content)) {
        std::cout << content << std::endl;
    }
    file.close();
}
```

### File writing
```cpp
#include <fstream>
std::ofstream file("output.txt");
if (file.is_open()) {
    file << "This is some text." << std::endl;
    file.close();
}
```

### Working with pointers 
```cpp
int number = 42;
int* ptr = &number;
```

### Dynamic memory allocation (new and delete)
```cpp
int* dynamicArray = new int[10];
delete[] dynamicArray;
```

### Standard template library (STL) vectors
```cpp
#include <vector>
std::vector<int> numbers = {1, 2, 3, 4, 5};
```

### Vector operations (push_back and pop_back)
```cpp
numbers.push_back(6);
numbers.pop_back();
```

### Vector iteration (for-each loop)
```cpp
for (int num : numbers) {
    std::cout << num << std::endl;
}
```

### Map(std::map)
```cpp
#include <map>
std::map<std::string, int> scores;
scores["Alice"] = 95;
```

### Map acces and iteration
```cpp
for (const auto& pair : scores) {
    std::cout << pair.first << ": " << pair.second << std::endl;
}
```

### String manipulation
```cpp
std::string text = "Hello, World!";
std::string substring = text.substr(0, 5);
```

### Sorting 
```cpp
#include <algorithm>
std::vector<int> numbers = {5, 2, 9, 1, 3};
std::sort(numbers.begin(), numbers.end());
```

### Lambda expressions (c++11+)
```cpp
auto add = [](int a, int b) -> int { return a + b; };
```

### Multithreading (c++11+)
```cpp
#include <thread>
void threadFunction() {
    // Thread logic here
}
std::thread t(threadFunction);
```

### Object Serialization (Cereal library)
```cpp
#include <cereal/archives/json.hpp>
#include <fstream>
struct Person {
    std::string name;
    int age;
    template <class Archive>
    void serialize(Archive& archive) {
        archive(name, age);
    }
};
Person person;
{
    std::ofstream os("person.json");
    cereal::JSONOutputArchive archive(os);
    archive(person);
}
```

### Object Deserialization (Cereal library)
```cpp
#include <cereal/archives/json.hpp>
#include <fstream>
struct Person {
    std::string name;
    int age;
    template <class Archive>
    void serialize(Archive& archive) {
        archive(name, age);
    }
};
Person person;
{
    std::ifstream is("person.json");
    cereal::JSONInputArchive archive(is);
    archive(person);
}
```

### Date and time (C++11+)
```cpp
#include <chrono>
auto currentTime = std::chrono::system_clock::now();
```

### Regular expressions (std::regex)
```cpp
#include <regex>
std::string text = "My email is example@example.com.";
std::regex emailRegex(R"(\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}\b)");
bool isEmail = std::regex_search(text, emailRegex);
```

### Working with sets (std::set)
```cpp
#include <set>
std::set<int> uniqueNumbers = {1, 2, 3, 4, 5};
```

### Set operations (intersection)
```cpp
std::set<int> set1 = {1, 2, 3};
std::set<int> set2 = {2, 3, 4};
std::set<int> intersection;
std::set_intersection(set1.begin(), set1.end(), set2.begin(), set2.end(),
                      std::inserter(intersection, intersection.begin()));
```

### Handling command-line arguments
```cpp
int main(int argc, char* argv[]) {
    if (argc > 1) {
        std::string arg1 = argv[1];
        // Process command-line arguments
    }
    return 0;
}
```

### Binary File Reading and Writing
```cpp
#include <fstream>
struct Data {
    int value;
    double decimal;
};
Data data = {42, 3.14159};
std::ofstream binaryFile("data.bin", std::ios::binary);
binaryFile.write(reinterpret_cast<const char*>(&data), sizeof(data));
binaryFile.close();
```

### Template metaprogramming
```cpp
template <int N>
struct Factorial {
    static constexpr int value = N * Factorial<N - 1>::value;
};
template <>
struct Factorial<0> {
    static constexpr int value = 1;
};
```

### Smart pointers (std::shared_ptr)
```cpp
#include <memory>
std::shared_ptr<int> shared = std::make_shared<int>(42);
```

### Working with Multidimensional Arrays
```cpp
int matrix[3][3] = {{1, 2, 3}, {4, 5, 6}, {7, 8, 9}};
```

### Enumerations
```cpp
enum class DaysOfWeek {
    MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY
};
```

### Lambda Expressions with Capture Lists (C++11+)
```cpp
int x = 5;
auto func = [x](int y) { return x + y; };
int result = func(10);
```

### Using std::find
```cpp
#include <algorithm>
std::vector<int> numbers = {1, 2, 3, 4, 5};
auto it = std::find(numbers.begin(), numbers.end(), 3);
if (it != numbers.end()) {
    int index = std::distance(numbers.begin(), it);
}
```

### Custom iterators (begin and end)
```cpp
class MyContainer {
public:
    int data[5] = {1, 2, 3, 4, 5};
    int* begin() { return &data[0]; }
    int* end() { return &data[5]; }
};
```

### Using std::thread for Multithreading (C++11+) 
```cpp
#include <thread>
void threadFunction() {
    // Thread logic here
}
std::thread t(threadFunction);
```

### Using std::mutex for Synchronization (C++11+)
```cpp
#include <iostream>
#include <thread>
#include <mutex>
std::mutex mtx;
void printMessage() {
    std::lock_guard<std::mutex> lock(mtx);
    std::cout << "Thread-safe message" << std::endl;
}
```

### Smart Pointers (std::unique_ptr)
```cpp
#include <memory>
std::unique_ptr<int> unique = std::make_unique<int>(42);
```

### Using the std::filesystem Library (C++17+)
```cpp
#include <filesystem>
namespace fs = std::filesystem;
fs::path filePath = fs::current_path() / "file.txt";
if (fs::exists(filePath)) {
    // File exists
}
```

### Working with Variadic Templates (C++11+)
```cpp
template <typename... Args>
void print(Args... args) {
    (std::cout << ... << args) << std::endl;
}
```

### Operator Overloading (e.g., + operator)
```cpp
class Complex {
public:
    double real, imag;
    Complex operator+(const Complex& other) {
        Complex result;
        result.real = real + other.real;
        result.imag = imag + other.imag;
        return result;
    }
};
```

### Creating and Using Custom Exceptions
```cpp
class CustomException : public std::exception {
public:
    const char* what() const noexcept override {
        return "Custom exception occurred.";
    }
};
try {
    throw CustomException();
} catch (const CustomException& e) {
    std::cerr << e.what() << std::endl;
}
```

### Function pointers and callbacks
```cpp
#include <iostream>
void callbackFunction() {
    std::cout << "Callback function called." << std::endl;
}
void performOperation(void (*callback)()) {
    callback();
}
```

### Template specialization
```cpp
template <typename T>
struct Printer {
    void print(T value) {
        std::cout << value << std::endl;
    }
};
template <>
struct Printer<std::string> {
    void print(std::string value) {
        std::cout << "String: " << value << std::endl;
    }
};
```

### Custom Deleters for std::shared_ptr
```cpp
struct CustomDeleter {
    void operator()(int* ptr) {
        delete ptr;
        std::cout << "Custom deleter called." << std::endl;
    }
};
std::shared_ptr<int> sharedWithCustomDeleter(new int(42), CustomDeleter());
```

### Using std::async for Asynchronous Execution (C++11+)
```cpp
#include <iostream>
#include <future>
int asyncFunction() {
    std::this_thread::sleep_for(std::chrono::seconds(2));
    return 42;
}
int main() {
    std::future<int> result = std::async(std::launch::async, asyncFunction);
    std::cout << "Waiting for async function..." << std::endl;
    int value = result.get();
    std::cout << "Async result: " << value << std::endl;
    return 0;
}
```

### Function Binders and std::bind (C++11+)
```cpp
#include <iostream>
#include <functional>
void printMessage(const std::string& message) {
    std::cout << message << std::endl;
}
int main() {
    auto boundFunction = std::bind(printMessage, "Hello, bound function!");
    boundFunction();
    return 0;
}
```

### Using std::chrono for High-Resolution Time (C++11+)
```cpp
#include <iostream>
#include <chrono>
int main() {
    auto start = std::chrono::high_resolution_clock::now();
    // Perform some time-consuming operation
    auto end = std::chrono::high_resolution_clock::now();
    auto duration = std::chrono::duration_cast<std::chrono::milliseconds>(end - start);
    std::cout << "Operation took " << duration.count() << " milliseconds." << std::endl;
    return 0;
}
```

### Creating and Using Custom Hash Functions
```cpp
#include <iostream>
#include <unordered_map>
struct Point {
    int x, y;
};
struct PointHash {
    std::size_t operator()(const Point& p) const {
        return std::hash<int>()(p.x) ^ std::hash<int>()(p.y);
    }
};
int main() {
    std::unordered_map<Point, std::string, PointHash> pointMap;
    Point p = {1, 2};
    pointMap[p] = "A point";
    return 0;
}
```

### Using std::any for Type-Unsafe Values (C++17+)
```cpp
#include <iostream>
#include <any>
int main() {
    std::any value = 42;
    int result = std::any_cast<int>(value);
    std::cout << "Value: " << result << std::endl;
    return 0;
}
```

### Function Pointers and std::function (C++11+)
```cpp
#include <iostream>
#include <functional>
void sayHello() {
    std::cout << "Hello, world!" << std::endl;
}
int main() {
    std::function<void()> func = sayHello;
    func();
    return 0;
}
```

### Using the std::optional Type (C++17+)
```cpp
#include <iostream>
#include <optional>
std::optional<int> divide(int a, int b) {
    if (b != 0) {
        return a / b;
    } else {
        return std::nullopt; // Indicates no value
    }
}
int main() {
    auto result = divide(10, 2);
    if (result.has_value()) {
        std::cout << "Result: " << result.value() << std::endl;
    } else {
        std::cout << "Division by zero." << std::endl;
    }
    return 0;
}
```











