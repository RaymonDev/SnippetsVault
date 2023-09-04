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

### Goroutines and Channels (Fan-out, Fan-in)
```go
func worker(id int, jobs <-chan int, results chan<- int) {
    for j := range jobs {
        results <- j * 2
    }
}

func main() {
    jobs := make(chan int, 100)
    results := make(chan int, 100)
    
    // Start workers
    for w := 1; w <= 3; w++ {
        go worker(w, jobs, results)
    }
    
    // Send jobs
    for j := 1; j <= 9; j++ {
        jobs <- j
    }
    close(jobs)
    
    // Collect results
    for a := 1; a <= 9; a++ {
        <-results
    }
}
```

### Mutexes and Synchronization (Mutex)
```go
import "sync"

var counter int
var mu sync.Mutex

func increment() {
    mu.Lock()
    counter++
    mu.Unlock()
}

func main() {
    var wg sync.WaitGroup
    for i := 0; i < 1000; i++ {
        wg.Add(1)
        go func() {
            defer wg.Done()
            increment()
        }()
    }
    wg.Wait()
    println("Counter:", counter)
}
```

### Defer Statement and Recovery (Panic and Recover)
```go
func recoverDemo() {
    defer func() {
        if r := recover(); r != nil {
            fmt.Println("Recovered:", r)
        }
    }()
    
    panic("Panic!")
}

func main() {
    recoverDemo()
    fmt.Println("After panic")
}
```

### Reflection (reflect package)
```go
import (
    "fmt"
    "reflect"
)

type Person struct {
    Name string
    Age  int
}

func main() {
    p := Person{"Alice", 30}
    valueType := reflect.TypeOf(p)
    fmt.Println("Type:", valueType)
    
    value := reflect.ValueOf(p)
    fmt.Println("Fields:")
    for i := 0; i < value.NumField(); i++ {
        field := value.Field(i)
        fmt.Printf("%s: %v\n", valueType.Field(i).Name, field.Interface())
    }
}
```

### Function Closure
```go
func generateAdder(a int) func(int) int {
    return func(b int) int {
        return a + b
    }
}

func main() {
    add5 := generateAdder(5)
    result := add5(10)
    fmt.Println("Result:", result)
}
```

### Custom errors
```go
type MyError struct {
    Message string
}

func (e *MyError) Error() string {
    return e.Message
}

func myFunction() error {
    return &MyError{"Custom error message"}
}

func main() {
    if err := myFunction(); err != nil {
        fmt.Println("Error:", err)
    }
}
```

### Context Package (Cancellation and Timeout)
```go
import (
    "context"
    "fmt"
    "time"
)

func myFunction(ctx context.Context) {
    select {
    case <-time.After(2 * time.Second):
        fmt.Println("Task completed")
    case <-ctx.Done():
        fmt.Println("Task canceled")
    }
}

func main() {
    ctx, cancel := context.WithTimeout(context.Background(), 1*time.Second)
    defer cancel()
    myFunction(ctx)
}
```

### Working with JSON (Unmarshalling into Structs)
```go
import (
    "encoding/json"
    "fmt"
)

type Person struct {
    Name string `json:"name"`
    Age  int    `json:"age"`
}

func main() {
    jsonString := `{"name":"Alice","age":25}`
    var person Person
    if err := json.Unmarshal([]byte(jsonString), &person); err != nil {
        fmt.Println("Error:", err)
        return
    }
    fmt.Printf("Name: %s, Age: %d\n", person.Name, person.Age)
}
```

### Working with Time (time package)
```go
import (
    "fmt"
    "time"
)

func main() {
    currentTime := time.Now()
    fmt.Println("Current Time:", currentTime)
    
    tomorrow := currentTime.Add(24 * time.Hour)
    fmt.Println("Tomorrow:", tomorrow)
}
```

### HTTP Server and Client (net/http package)
```go
import (
    "fmt"
    "net/http"
)

func helloHandler(w http.ResponseWriter, r *http.Request) {
    fmt.Fprintln(w, "Hello, World!")
}

func main() {
    http.HandleFunc("/hello", helloHandler)
    http.ListenAndServe(":8080", nil)
}
```

### Creating and using interfaces
```go
type Shape interface {
    Area() float64
}

type Circle struct {
    Radius float64
}

func (c Circle) Area() float64 {
    return 3.14 * c.Radius * c.Radius
}

type Square struct {
    SideLength float64
}

func (s Square) Area() float64 {
    return s.SideLength * s.SideLength
}

func main() {
    c := Circle{Radius: 5}
    s := Square{SideLength: 4}
    
    shapes := []Shape{c, s}
    for _, shape := range shapes {
        fmt.Printf("Area: %f\n", shape.Area())
    }
}
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

func main() {
    result := sum(1, 2, 3, 4, 5)
    fmt.Println("Sum:", result)
}
```

### Working with Templates (html/template package)
```go
import (
    "html/template"
    "os"
)

type Person struct {
    Name string
    Age  int
}

func main() {
    tmpl, _ := template.New("example").Parse("Name: {{.Name}}, Age: {{.Age}}\n")
    person := Person{Name: "Alice", Age: 25}
    tmpl.Execute(os.Stdout, person)
}
```

### Web Routing with Gorilla Mux (gorilla/mux package)
```go
import (
    "fmt"
    "net/http"
    "github.com/gorilla/mux"
)

func helloHandler(w http.ResponseWriter, r *http.Request) {
    fmt.Fprintln(w, "Hello, World!")
}

func main() {
    r := mux.NewRouter()
    r.HandleFunc("/hello", helloHandler)
    
    http.Handle("/", r)
    http.ListenAndServe(":8080", nil)
}
```

### Custom Middleware in HTTP Handlers
```go
import (
    "fmt"
    "net/http"
)

func loggingMiddleware(next http.Handler) http.Handler {
    return http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) {
        fmt.Println("Request received:", r.URL.Path)
        next.ServeHTTP(w, r)
    })
}

func helloHandler(w http.ResponseWriter, r *http.Request) {
    fmt.Fprintln(w, "Hello, World!")
}

func main() {
    r := http.NewServeMux()
    r.HandleFunc("/hello", helloHandler)
    
    http.Handle("/", loggingMiddleware(r))
    http.ListenAndServe(":8080", nil)
}
```

### Database Access with SQL (database/sql package)
```go
import (
    "database/sql"
    "fmt"
    _ "github.com/go-sql-driver/mysql"
)

func main() {
    db, err := sql.Open("mysql", "user:password@tcp(localhost:3306)/database")
    if err != nil {
        fmt.Println("Error:", err)
        return
    }
    defer db.Close()
    
    rows, err := db.Query("SELECT name FROM users WHERE age > ?", 25)
    if err != nil {
        fmt.Println("Error:", err)
        return
    }
    defer rows.Close()
    
    for rows.Next() {
        var name string
        err := rows.Scan(&name)
        if err != nil {
            fmt.Println("Error:", err)
            return
        }
        fmt.Println("Name:", name)
    }
}
```

### Concurrent Map Access (sync.Map)
```go
import (
    "fmt"
    "sync"
)

func main() {
    var m sync.Map
    
    m.Store("key1", "value1")
    m.Store("key2", "value2")
    
    value, ok := m.Load("key1")
    if ok {
        fmt.Println("Value:", value)
    }
    
    m.Delete("key2")
}
```

### Panic and Recover in Goroutines
```go
import (
    "fmt"
    "time"
)

func recoverInGoroutine() {
    defer func() {
        if r := recover(); r != nil {
            fmt.Println("Recovered in goroutine:", r)
        }
    }()
    
    panic("Goroutine panic")
}

func main() {
    go recoverInGoroutine()
    time.Sleep(time.Second)
}
```

### Custom Sort Function (sort package)
```go
import (
    "fmt"
    "sort"
)

type Person struct {
    Name string
    Age  int
}

type ByAge []Person

func (a ByAge) Len() int           { return len(a) }
func (a ByAge) Swap(i, j int)      { a[i], a[j] = a[j], a[i] }
func (a ByAge) Less(i, j int) bool { return a[i].Age < a[j].Age }

func main() {
    people := []Person{
        {"Alice", 30},
        {"Bob", 25},
        {"Charlie", 35},
    }
    
    sort.Sort(ByAge(people))
    
    for _, p := range people {
        fmt.Printf("Name: %s, Age: %d\n", p.Name, p.Age)
    }
}
```
