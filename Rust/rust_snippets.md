## Rust

### Hello World
```rust
fn main() {
    println!("Hello, World!");
}
```

### Variables and constants
```rust
let variable = 10;
const CONSTANT_VALUE: i32 = 5;
```

### Data types
```rust
let integer: i32 = 42;
let float: f64 = 3.14;
let character: char = 'A';
let boolean: bool = true;
```

### Arrays
```rust
let fruits = ["Apple", "Banana", "Orange"];
```

### Vectors
```rust
let mut numbers = vec![1, 2, 3];
numbers.push(4);
```

### Conditional statements
```rust
if age >= 18 {
    println!("You are an adult.");
} else {
    println!("You are a minor.");
}
```

### For loop
```rust
for number in 1..=5 {
    println!("{}", number);
}
```

### While loop
```rust
let mut count = 0;
while count < 5 {
    println!("{}", count);
    count += 1;
}
```

### Functions
```rust
fn greet(name: &str) {
    println!("Hello, {}!", name);
}
```

### Option and result
```rust
let maybe_value: Option<i32> = Some(42);
let result: Result<i32, String> = Ok(42);
```

### Pattern matching
```rust
match age {
    0 => println!("You're a baby"),
    1..=17 => println!("You're a minor"),
    18..=64 => println!("You're an adult"),
    _ => println!("You're a senior"),
}
```

### Enumerations
```rust
enum Color {
    Red,
    Green,
    Blue,
}
let my_color = Color::Green;
```

### Structs
```rust
struct Point {
    x: f64,
    y: f64,
}
let origin = Point { x: 0.0, y: 0.0 };
```

### Ownership and borrowing
```rust
let s1 = String::from("Hello");
let s2 = s1.clone();
```

### References and lifetimes
```rust
fn longest<'a>(s1: &'a str, s2: &'a str) -> &'a str {
    if s1.len() > s2.len() {
        s1
    } else {
        s2
    }
}
```

### Methods on structs
```rust
impl Point {
    fn distance(&self, other: &Point) -> f64 {
        ((self.x - other.x).powi(2) + (self.y - other.y).powi(2)).sqrt()
    }
}
```

### Traits and implementations
```rust
trait Shape {
    fn area(&self) -> f64;
}

struct Circle {
    radius: f64,
}

impl Shape for Circle {
    fn area(&self) -> f64 {
        std::f64::consts::PI * self.radius * self.radius
    }
}
```

### Error handling with `Result`
```rust
fn divide(a: i32, b: i32) -> Result<f64, String> {
    if b == 0 {
        return Err("Division by zero".to_string());
    }
    Ok(a as f64 / b as f64)
}
```

### Option and `unwrap`
```rust
let result = some_option.unwrap_or_default();
```

### Closures
```rust
let add_numbers = |a: i32, b: i32| -> i32 {
    a + b
};
let sum = add_numbers(5, 3);
```

### Pattern matching with Enums
```rust
enum Coin {
    Penny,
    Nickel,
    Dime,
    Quarter,
}

fn value_in_cents(coin: Coin) -> i32 {
    match coin {
        Coin::Penny => 1,
        Coin::Nickel => 5,
        Coin::Dime => 10,
        Coin::Quarter => 25,
    }
}
```

### File I/O
```rust
use std::fs::File;
use std::io::prelude::*;

fn main() -> std::io::Result<()> {
    let mut file = File::create("hello.txt")?;
    file.write_all(b"Hello, Rust!")?;
    Ok(())
}
```

### Command line arguments
```rust
use std::env;

fn main() {
    let args: Vec<String> = env::args().collect();
    println!("{:?}", args);
}
```

### Concurrency with Threads
```rust
use std::thread;

fn main() {
    let handle = thread::spawn(|| {
        println!("Hello from the thread!");
    });

    handle.join().unwrap();
}
```

### Mutexes and shared data
```rust
use std::sync::{Arc, Mutex};

fn main() {
    let counter = Arc::new(Mutex::new(0));

    let mut handles = vec![];

    for _ in 0..10 {
        let counter = Arc::clone(&counter);
        let handle = thread::spawn(move || {
            let mut num = counter.lock().unwrap();
            *num += 1;
        });
        handles.push(handle);
    }

    for handle in handles {
        handle.join().unwrap();
    }

    println!("Result: {}", *counter.lock().unwrap());
}
```

### Error handling with ? operator
```rust
use std::fs::File;
use std::io::{self, Read};

fn read_file() -> Result<String, io::Error> {
    let mut file = File::open("file.txt")?;
    let mut content = String::new();
    file.read_to_string(&mut content)?;
    Ok(content)
}
```

### Traits and generic functions
```rust
trait Printable {
    fn print(&self);
}

fn print_all<T: Printable>(items: Vec<T>) {
    for item in items {
        item.print();
    }
}
```

### Lifetimes in function signatures
```rust
fn longest<'a>(s1: &'a str, s2: &'a str) -> &'a str {
    if s1.len() > s2.len() {
        s1
    } else {
        s2
    }
}
```

### Unsafe code
```rust
unsafe fn dangerous() {
    // Unsafe code here
}
```

### Match expressions for exhaustive patterns
```rust
fn main() {
    let number = Some(7);
    match number {
        Some(1) => println!("One"),
        Some(3) => println!("Three"),
        Some(7) => println!("Seven"),
        _ => println!("Other"),
    }
}
```

### Async/Await (Requires the async-std or tokio library)
```rust
use async_std::task;

async fn async_function() {
    // Async code here
}

fn main() {
    task::block_on(async_function());
}
```

### Handling JSON with serde
```rust
use serde::{Deserialize, Serialize};

#[derive(Serialize, Deserialize)]
struct Person {
    name: String,
    age: i32,
}

let person = Person {
    name: String::from("John"),
    age: 30,
};
let json = serde_json::to_string(&person).unwrap();
```

### File downloads (with rocket web framework)
```rust
use rocket::tokio::fs::NamedFile;

#[get("/download")]
async fn download() -> Option<NamedFile> {
    NamedFile::open("file.txt").await.ok()
}
```

### Web API (with Actix web framework)
```rust
use actix_web::{web, App, HttpServer, HttpResponse, Result};

async fn index() -> Result<HttpResponse> {
    Ok(HttpResponse::Ok().body("Hello, Actix!"))
}

#[actix_rt::main]
async fn main() -> std::io::Result<()> {
    HttpServer::new(|| {
        App::new()
            .route("/", web::get().to(index))
    })
    .bind("127.0.0.1:8080")?
    .run()
    .await
}
```

### Working with Database (with Diesel ORM)
```rust
use diesel::prelude::*;

#[derive(Queryable)]
struct User {
    id: i32,
    name: String,
}

fn main() {
    let connection = establish_connection();
    let results = users.filter(name.eq("Alice"))
        .load::<User>(&connection)
        .expect("Error loading users");

    for user in results {
        println!("ID: {}, Name: {}", user.id, user.name);
    }
}
```

### Unsafe Rust
```rust
unsafe fn dangerous_function() {
    // Unsafe code here
}

fn main() {
    unsafe {
        dangerous_function();
    }
}
```

### FFI (Foreign Function Interface)
```rust
extern "C" {
    fn some_external_function();
}

fn main() {
    unsafe {
        some_external_function();
    }
}
```

### Writing unit tests
```rust
#[cfg(test)]
mod tests {
    #[test]
    fn test_addition() {
        assert_eq!(2 + 2, 4);
    }
}
```

### Lifetime annotations
```rust
fn longest<'a>(s1: &'a str, s2: &'a str) -> &'a str {
    if s1.len() > s2.len() {
        s1
    } else {
        s2
    }
}
```

### Advanced Pattern Matching
```rust
match result {
    Ok(value) => println!("Value is {}", value),
    Err(error) => eprintln!("Error: {}", error),
}
```

### Option and result unwrapper
```rust
let result = calculate_result();
let value = result.unwrap_or_else(|error| {
    eprintln!("Error: {}", error);
    default_value()
});
```

### Concurrency with async-std
```rust
use async_std::task;

async fn async_function() {
    // Async code here
}

fn main() {
    task::block_on(async_function());
}
```

### Channels for concurrency
```rust
use std::sync::mpsc;
use std::thread;

let (sender, receiver) = mpsc::channel();

thread::spawn(move || {
    sender.send("Message from another thread").unwrap();
});

let received = receiver.recv().unwrap();
```






