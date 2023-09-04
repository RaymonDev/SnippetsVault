## Go (Golang)

### Hello World
```go
package main
import "fmt"
func main() {
    fmt.Println("Hello, World!")
}
```

### Variables
```go
var age int = 30
var name string = "John"
```

### User input
```go
import "fmt"
func main() {
    var userInput string
    fmt.Print("Enter something: ")
    fmt.Scanln(&userInput)
    fmt.Println("You entered:", userInput)
}
```

### If-else
```go
if age >= 18 {
    fmt.Println("You are an adult.")
} else {
    fmt.Println("You are a minor.")
}
```

### For loop
```go
for i := 0; i < 5; i++ {
    fmt.Println(i)
}
```

### While loop
```go
count := 0
for count < 5 {
    fmt.Println(count)
    count++
}
```

### Arrays
```go
numbers := [5]int{1, 2, 3, 4, 5}
```

### Array access
```go
firstNumber := numbers[0]
```

### Functions
```go
func add(a, b int) int {
    return a + b
}
```

### Structs (Custom data types)
```go
type Person struct {
    Name string
    Age  int
}
```

### Struct initialization
```go
person := Person{Name: "Alice", Age: 25}
```

### Slices(Dynamic arrays)
```go
numbers := []int{1, 2, 3, 4, 5}
```

### Slice operations (Append, Remove)
```go
numbers = append(numbers, 6)
numbers = append(numbers[:2], numbers[3:]...)
```

### Slice iteration (range)
```go
for index, value := range numbers {
    fmt.Printf("Index: %d, Value: %d\n", index, value)
}
```

### Maps (key-value pairs)
```go
scores := map[string]int{"Alice": 95, "Bob": 88}
```

### Map operations (Insert, Delete)
```go
scores["Charlie"] = 72
delete(scores, "Bob")
```

### Map iteration
```go
for name, score := range scores {
    fmt.Printf("Name: %s, Score: %d\n", name, score)
}
```

### String manipulation
```go
text := "Hello, World!"
substring := text[0:5]
```

### String concatenation
```go
greeting := "Hello"
name := "Alice"
message := greeting + ", " + name + "!"
```

### Time formatting
```go
import "time"
currentTime := time.Now()
formattedTime := currentTime.Format("2006-01-02 15:04:05")
```

### Error handling (panic and recover)
```go
func example() {
    defer func() {
        if r := recover(); r != nil {
            fmt.Println("Recovered:", r)
        }
    }()
    panic("Something went wrong!")
}
```

### File Reading (io/ioutil)
```go
import "io/ioutil"
content, err := ioutil.ReadFile("example.txt")
if err != nil {
    fmt.Println("Error:", err)
}
```

### File Writing (os)
```go
import "os"
file, err := os.Create("output.txt")
if err != nil {
    fmt.Println("Error:", err)
}
defer file.Close()
file.WriteString("This is some text.")
```

### Working with enums
```go
const (
    Monday = iota
    Tuesday
    Wednesday
    Thursday
    Friday
    Saturday
    Sunday
)
```

### Regular expressions (regexp)    
```go
import "regexp"
text := "My email is example@example.com."
pattern := `\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}\b`
isEmail, _ := regexp.MatchString(pattern, text)
```

### Working with Interfaces
```go
type Shape interface {
    Area() float64
}
```

### Goroutines (Concurrent Execution)
```go
import "fmt"
import "time"
func main() {
    go func() {
        fmt.Println("Goroutine started")
    }()
    time.Sleep(time.Second)
}
```

### Channels (Communication Between Goroutines)
```go
ch := make(chan int)
go func() {
    ch <- 42
}()
value := <-ch
```

### Wait Groups (Synchronization)
```go
import "sync"
var wg sync.WaitGroup
wg.Add(2)
go func() {
    defer wg.Done()
    // Task 1
}()
go func() {
    defer wg.Done()
    // Task 2
}()
wg.Wait()
```

### Error handling (Custom errors)
```go
type CustomError struct {
    Message string
}
func (e *CustomError) Error() string {
    return e.Message
}
```

### JSON Serialization and Deserialization
```go
import "encoding/json"
data := struct {
    Name string `json:"name"`
    Age  int    `json:"age"`
}{Name: "Alice", Age: 25}
jsonString, _ := json.Marshal(data)
```

### Working with Timezones (time.LoadLocation)
```go
import "time"
location, _ := time.LoadLocation("America/New_York")
current_time := time.Now().In(location)
```

### Command-Line Arguments (os.Args)
```go
import "os"
if len(os.Args) > 1 {
    arg := os.Args[1]
    // Process command-line argument
}
```

### Reflection (reflect package)
```go
import "reflect"
value := 42
valueType := reflect.TypeOf(value)
```

### Function variadic parameters
```go
func sum(numbers ...int) int {
    total := 0
    for _, num := range numbers {
        total += num
    }
    return total
}
```

### Working with time durations
```go
import "time"
duration := 5 * time.Second
time.Sleep(duration)
```

### Defer Statement
```go
func main() {
    defer fmt.Println("Deferred statement")
    fmt.Println("Main function")
}
```

### Custom String Formatting
```go
type Person struct {
    Name string
    Age  int
}
func (p Person) String() string {
    return fmt.Sprintf("%s (%d years old)", p.Name, p.Age)
}
```

### Multiple Return Values
```go
func divide(a, b int) (int, error) {
    if b == 0 {
        return 0, fmt.Errorf("Division by zero")
    }
    return a / b, nil
}
```

### Reading from Standard Input (fmt.Scan)
```go
import "fmt"
var input string
fmt.Print("Enter something: ")
fmt.Scan(&input)
fmt.Println("You entered:", input)
```

### Anonymous Functions (Closures)
```go
func main() {
    x := 10
    func() {
        fmt.Println("Closure value:", x)
    }()
}
```
















