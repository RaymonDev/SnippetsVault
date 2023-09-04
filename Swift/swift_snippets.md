## Swift

### Hello World
```swift
print("Hello, World!")
```

### Variabels and Constants
```swift
let constantValue = 10
var variableValue = 5
```

### Type inference
```swift
let myString = "Hello, Swift!" // Inferred as String
```

### Type annotation
```swift
let age: Int = 30
```

### Arrays
```swift
var fruits = ["Apple", "Banana", "Orange"]
fruits.append("Mango")
```

### Dictionaries
```swift
var person = ["name": "John", "age": 25]
person["city"] = "New York"
```

### Conditional statements
```swift
if age >= 18 {
    print("You are an adult.")
} else {
    print("You are a minor.")
}
```

### For-in
```swift
for number in 1...5 {
    print(number)
}
```

### While
```swift
var count = 0
while count < 5 {
    print(count)
    count += 1
}
```

### Functions
```swift
func greet(name: String) -> String {
    return "Hello, \(name)!"
}
```

### Optional binding
```swift
var optionalValue: Int? = 42
if let value = optionalValue {
    print("Value is \(value)")
} else {
    print("Value is nil")
}
```

### Guard statement
```swift
func checkAge(age: Int?) {
    guard let age = age else {
        print("Age is nil")
        return
    }
    print("Age is \(age)")
}
```

### Enumerations
```swift
enum CompassDirection {
    case north, south, east, west
}
let direction = CompassDirection.north
```

### Structs
```swift
struct Point {
    var x: Double
    var y: Double
}
let origin = Point(x: 0.0, y: 0.0)
```

### Classes
```swift
class Person {
    var name: String = ""
    var age: Int = 0
}
let person = Person()
person.name = "Alice"
person.age = 30
```

### Inheritance
```swift
class Student: Person {
    var studentID: String = ""
}
let student = Student()
student.studentID = "12345"
```

### Protocols
```swift
protocol Animal {
    func makeSound()
}
```

### Extensions
```swift
extension String {
    func capitalize() -> String {
        return self.capitalized
    }
}
let capitalizedString = "hello".capitalize()
```

### Closures
```swift
let addNumbers: (Int, Int) -> Int = { (a, b) in
    return a + b
}
let result = addNumbers(5, 3)
```

### Optionals
```swift
var name: String? = "John"
if let unwrappedName = name {
    print("Hello, \(unwrappedName)!")
} else {
    print("Name is nil")
}
```

### Error Handling
```swift
enum MyError: Error {
    case someError
}

func throwError() throws {
    throw MyError.someError
}

do {
    try throwError()
} catch {
    print("An error occurred: \(error)")
}
```

### Tuples
```swift
let personInfo = (name: "Alice", age: 25)
print(personInfo.name)
print(personInfo.age)
```

### Type casting
```swift
class Animal {}
class Dog: Animal {}

let myDog = Dog()
if myDog is Animal {
    print("It's an animal")
}
```

### Deinitialization
```swift
class MyClass {
    deinit {
        print("Object deallocated")
    }
}
var object: MyClass? = MyClass()
object = nil // Deinitialization message printed
```

### Acces control
```swift
public class MyPublicClass {}
internal class MyInternalClass {}
private class MyPrivateClass {}
```

### Property observers
```swift
var temperature: Double = 0.0 {
    didSet {
        print("Temperature is now \(temperature) degrees.")
    }
}
temperature = 25.0 // Prints the observer message
```

### Computed properties
```swift
struct Circle {
    var radius: Double
    var area: Double {
        return 3.14 * radius * radius
    }
}
```

### Lazy properties
```swift
class ImageLoader {
    lazy var image: UIImage = {
        // Load and return an image
        return UIImage(named: "image.png")!
    }()
}
```

### Equatable and Comparable
```swift
struct Person: Equatable, Comparable {
    var name: String
    var age: Int

    static func < (lhs: Person, rhs: Person) -> Bool {
        return lhs.age < rhs.age
    }
}
```

### Codable
```swift
struct Product: Codable {
    var name: String
    var price: Double
}
let jsonData = """
{
    "name": "iPhone",
    "price": 999.99
}
""".data(using: .utf8)!
let product = try JSONDecoder().decode(Product.self, from: jsonData)
```

### Date formatting
```swift
let dateFormatter = DateFormatter()
dateFormatter.dateFormat = "yyyy-MM-dd HH:mm:ss"
let date = dateFormatter.date(from: "2023-09-04 15:30:00")
```

### NotificationCenter
```swift
NotificationCenter.default.addObserver(self, selector: #selector(handleNotification(_:)), name: Notification.Name("MyNotification"), object: nil)
```

### Dispatch queues
```swift
let queue = DispatchQueue(label: "com.myapp.myqueue")
queue.async {
    // Code to execute asynchronously
}
```

### User Defaults
```swift
UserDefaults.standard.set("John", forKey: "username")
let username = UserDefaults.standard.string(forKey: "username")
```

### File Manager
```swift
let fileManager = FileManager.default
if let documentsDir = fileManager.urls(for: .documentDirectory, in: .userDomainMask).first {
    // Work with the documents directory
}
```

### Core Data
```swift
import CoreData

let appDelegate = UIApplication.shared.delegate as! AppDelegate
let context = appDelegate.persistentContainer.viewContext

let entity = NSEntityDescription.entity(forEntityName: "Person", in: context)
let person = NSManagedObject(entity: entity!, insertInto: context)
person.setValue("John", forKey: "name")

do {
    try context.save()
} catch {
    print("Failed to save data: \(error)")
}
```

### UIAlertController
```swift
let alertController = UIAlertController(title: "Alert", message: "This is an alert message.", preferredStyle: .alert)
let okAction = UIAlertAction(title: "OK", style: .default, handler: nil)
alertController.addAction(okAction)
present(alertController, animated: true, completion: nil)
```

### Segues (Storyboard)
```swift
performSegue(withIdentifier: "showDetail", sender: self)
```

### Gesture Recognizers
```swift
let tapGesture = UITapGestureRecognizer(target: self, action: #selector(handleTap(_:)))
view.addGestureRecognizer(tapGesture)
```

### Core Location (Location Services)
```swift
import CoreLocation

let locationManager = CLLocationManager()
locationManager.requestWhenInUseAuthorization()
locationManager.startUpdatingLocation()
```

### Generics
```swift
func swap<T>(_ a: inout T, _ b: inout T) {
    let temp = a
    a = b
    b = temp
}
```

### Higher-order functions-map
```swift
let numbers = [1, 2, 3, 4, 5]
let squaredNumbers = numbers.map { $0 * $0 }
```

### Higher-order functions-filter
```swift
let evenNumbers = numbers.filter { $0 % 2 == 0 }
```

### Higher-order functions-reduce
```swift
let sum = numbers.reduce(0, +)
```

### Async/Await (iOS 15+)
```swift
async {
    let data = await fetchData()
    process(data)
}
```

### Result Type (Error Handling)
```swift
func divide(_ a: Int, by b: Int) -> Result<Int, MyError> {
    if b == 0 {
        return .failure(MyError.divisionByZero)
    }
    return .success(a / b)
}
```

### Custom operators
```swift
infix operator **: MultiplicationPrecedence

func **(base: Double, exponent: Double) -> Double {
    return pow(base, exponent)
}
```

### Key-Value Observing (KVO)
```swift
class MyClass: NSObject {
    @objc dynamic var value: Int = 0
}
let myObject = MyClass()
myObject.addObserver(self, forKeyPath: "value", options: .new, context: nil)
```

### Codable with Custom Keys
```swift
struct Person: Codable {
    enum CodingKeys: String, CodingKey {
        case firstName = "first_name"
        case lastName = "last_name"
    }
    var firstName: String
    var lastName: String
}
```

### Core animation
```swift
let animation = CABasicAnimation(keyPath: "position")
animation.fromValue = CGPoint(x: 0, y: 0)
animation.toValue = CGPoint(x: 100, y: 100)
animation.duration = 2.0
layer.add(animation, forKey: "positionAnimation")
```

### Concurrency with DispatchGroup
```swift
let group = DispatchGroup()

group.enter()
fetchData { data in
    // Process data
    group.leave()
}

group.enter()
fetchImage { image in
    // Process image
    group.leave()
}

group.notify(queue: .main) {
    // All tasks are done
}
```

### Core graphics drawing
```swift
class CustomView: UIView {
    override func draw(_ rect: CGRect) {
        let context = UIGraphicsGetCurrentContext()
        context?.setFillColor(UIColor.blue.cgColor)
        context?.fillEllipse(in: CGRect(x: 50, y: 50, width: 100, height: 100))
    }
}
```

### Autolayout Programmatically
```swift
let redView = UIView()
redView.backgroundColor = .red
redView.translatesAutoresizingMaskIntoConstraints = false
view.addSubview(redView)

redView.leadingAnchor.constraint(equalTo: view.leadingAnchor, constant: 20).isActive = true
redView.topAnchor.constraint(equalTo: view.topAnchor, constant: 20).isActive = true
redView.widthAnchor.constraint(equalToConstant: 100).isActive = true
redView.heightAnchor.constraint(equalToConstant: 100).isActive = true
```

### Core Data Relationships
```swift
class Author: NSManagedObject {
    @NSManaged var name: String
    @NSManaged var books: NSSet
}

class Book: NSManagedObject {
    @NSManaged var title: String
    @NSManaged var author: Author?
}
```

### Dependency Injection
```swift
class DataManager {
    func fetchData() -> [String] {
        // Fetch data from a source
        return ["Item 1", "Item 2", "Item 3"]
    }
}

class MyViewController {
    let dataManager: DataManager
    
    init(dataManager: DataManager) {
        self.dataManager = dataManager
    }
}
```

### Swift Package Manager
```swift
// Create a Swift package
swift package init --type library

// Add dependencies to Package.swift
dependencies: [
    .package(url: "https://github.com/example/package.git", from: "1.0.0")
],
targets: [
    .target(name: "MyPackage", dependencies: ["ExamplePackage"]),
]
```

### Keychain Access
```swift
import KeychainAccess

let keychain = Keychain(service: "com.myapp")
keychain["username"] = "John"
let storedUsername = keychain["username"]
```

### Unit Testing with XCTest
```swift
import XCTest

class MyTests: XCTestCase {
    func testAddition() {
        let result = add(2, 3)
        XCTAssertEqual(result, 5)
    }
}
```

### Custom Property Wrappers
```swift
@propertyWrapper
struct Trimmed {
    private(set) var value: String = ""

    var wrappedValue: String {
        get { value }
        set { value = newValue.trimmingCharacters(in: .whitespacesAndNewlines) }
    }
}

struct MyStruct {
    @Trimmed var text: String
}
```

### SwiftUI
```swift
import SwiftUI

struct ContentView: View {
    var body: some View {
        Text("Hello, SwiftUI!")
            .font(.largeTitle)
            .foregroundColor(.blue)
    }
}
```