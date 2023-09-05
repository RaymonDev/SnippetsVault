## PHP

### Hello World
```php
echo "Hello, World!";
```

### Variables and constants
```php
$variable = 10;
define("CONSTANT_VALUE", 5);
```

### Data types
```php
$integer = 42;
$float = 3.14;
$string = "Hello, PHP!";
$boolean = true;
$array = array(1, 2, 3);
$object = new stdClass();
$null = null;
```

### Arrays
```php
$fruits = ["Apple", "Banana", "Orange"];
array_push($fruits, "Mango");
```

### Associative arrays
```php
$person = ["name" => "John", "age" => 25];
$person["city"] = "New York
```

### Conditional statements
```php
if ($age >= 18) {
    echo "You are an adult.";
} else {
    echo "You are a minor.";
}
```

### For loop
```php
for ($i = 0; $i < 5; $i++) {
    echo $i;
}
```

### While loop
```php
$count = 0;
while ($count < 5) {
    echo $count;
    $count++;
}
```

### Functions
```php
function greet($name) {
    return "Hello, $name!";
}
```

### Include and require
```php
include "header.php";
require "config.php";
```

### Working with files
```php
$file = fopen("data.txt", "r");
$content = fread($file, filesize("data.txt"));
fclose($file);
```

### Error handling
```php
try {
    // Code that may throw an exception
} catch (Exception $e) {
    echo "An error occurred: " . $e->getMessage();
}
```

### Cookies
```php
setcookie("username", "John", time() + 3600, "/");
$username = $_COOKIE["username"];
```

### Sessions
```php
session_start();
$_SESSION["user_id"] = 123;
```

### Forms and POST Data
```php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $username = $_POST["username"];
    $password = $_POST["password"];
}
```

### MySQL Database Connection
```php
$servername = "localhost";
$username = "root";
$password = "password";
$database = "mydb";

$conn = new mysqli($servername, $username, $password, $database);
```

### SQL Queries
```php
$sql = "SELECT * FROM users WHERE username='$username'";
$result = $conn->query($sql);
```

### Fetching data from MySQL
```php
while ($row = $result->fetch_assoc()) {
    echo "Name: " . $row["name"];
}
```

### Inserting data into MySQL
```php
$sql = "INSERT INTO users (username, password) VALUES ('$username', '$password')";
$conn->query($sql);
```

### Updating data in MySQL
```php
$sql = "UPDATE users SET email='$email' WHERE id=$user_id";
$conn->query($sql);
```

### Deleting data from MySQL
```php
$sql = "DELETE FROM users WHERE id=$user_id";
$conn->query($sql);
```

### Object-oriented programming
```php
class Person {
    public $name;
    public $age;
    
    public function greet() {
        echo "Hello, my name is $this->name.";
    }
}
```

### Inheritance
```php
class Student extends Person {
    public $studentID;
}
```

### Namespaces
```php
namespace MyProject;
```

### Composer (Dependency Manager)
```php
// Install a package
composer require vendor/package

// Autoload packages
require 'vendor/autoload.php';
```

### Regular Expressions
```php
$pattern = "/[0-9]{4}-[0-9]{2}-[0-9]{2}/";
$validDate = preg_match($pattern, "2023-09-04");
```

### Sending emails
```php
$to = "recipient@example.com";
$subject = "Hello";
$message = "This is a test email.";
$headers = "From: sender@example.com";

mail($to, $subject, $message, $headers);
```

### RESTful api
```php
// Handle GET request
if ($_SERVER["REQUEST_METHOD"] == "GET") {
    $data = ["message" => "GET request received"];
    echo json_encode($data);
}
```

### File upload
```php
if ($_FILES["file"]["error"] == 0) {
    move_uploaded_file($_FILES["file"]["tmp_name"], "uploads/" . $_FILES["file"]["name"]);
}
```

### JSON Handling
```php
$data = '{"name": "John", "age": 30}';
$decodedData = json_decode($data);
```

### Date and time
```php
$currentDate = date("Y-m-d H:i:s");
```

### Templating with PHP
```php
// Include a template file
include "template.php";
```

### URL parameters
```php
$id = $_GET["id"];
```

### File writing
```php
$file = fopen("data.txt", "w");
fwrite($file, "Hello, PHP!");
fclose($file);
```

### Sessions and User Authentication
```php
session_start();
if (!isset($_SESSION["user_id"])) {
    // Redirect to login page
}
```

### URL redirection
```php
header("Location: https://example.com");
```

### Content-Type Headers
```php
header("Content-Type: application/json");
```

### Creating and Using Classes
```php
class Car {
    private $make;
    private $model;
    
    public function __construct($make, $model) {
        $this->make = $make;
        $this->model = $model;
    }
    
    public function getInfo() {
        return "Make: $this->make, Model: $this->model";
    }
}
```

### File deletion
```php
if (file_exists("oldfile.txt")) {
    unlink("oldfile.txt");
}
```

### Working with XML
```php
$xml = simplexml_load_string("<book><title>PHP Basics</title></book>");
$title = $xml->title;
```

### Namespaces in Autoloading
```php
// Autoloading classes within a namespace
spl_autoload_register(function ($className) {
    $className = str_replace("\\", DIRECTORY_SEPARATOR, $className);
    require_once __DIR__ . "/{$className}.php";
});
```

### Exception handling and custom exception classes
```php
class MyCustomException extends Exception {}

try {
    // Some code that may throw an exception
    throw new MyCustomException("This is a custom exception.");
} catch (MyCustomException $e) {
    echo "Caught exception: " . $e->getMessage();
}
```

### Dependency injection in classes
```php
class Database {
    public function __construct($hostname, $username, $password, $database) {
        // Database connection setup
    }
}

$database = new Database("localhost", "username", "password", "mydb");
```

### Namespaces for code organization
```php
namespace MyNamespace;

class MyClass {
    // Class code here
}
```

### PDO (PHP Data objects) for database access
```php
try {
    $pdo = new PDO("mysql:host=localhost;dbname=mydb", "username", "password");
    $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
} catch (PDOException $e) {
    echo "Connection failed: " . $e->getMessage();
}
```

### Dependency injection in functions
```php
function calculateTotal($price, $taxRate) {
    return $price * (1 + $taxRate);
}

$total = calculateTotal(100, 0.1);
```

### Namespaces for third-party libraries
```php
use Vendor\Library\Class;

$instance = new Class();
```

### Composer autoload
```php
require 'vendor/autoload.php';
```

### Singleton pattern
```php
class Singleton {
    private static $instance;
    
    private function __construct() {}
    
    public static function getInstance() {
        if (self::$instance === null) {
            self::$instance = new Singleton();
        }
        return self::$instance;
    }
}
```

### File download
```php
$file = 'example.txt';
header('Content-Description: File Transfer');
header('Content-Type: application/octet-stream');
header('Content-Disposition: attachment; filename="'.basename($file).'"');
readfile($file);
```





