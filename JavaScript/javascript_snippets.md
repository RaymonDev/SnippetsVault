
## JavaScript

### Hello World
```javascript
console.log("Hello, World!");
```

### Variables
```javascript
let name = "John";
const age = 30;
```

### User Input via prompt
```javascript
let user_input = prompt("Enter something: ");
```

### if-else
```javascript
if (age >= 18) {
    console.log("You are an adult.");
} else {
    console.log("You are a minor.");
}
```

### For loop
```javascript
for (let i = 0; i < 5; i++) {
    console.log(i);
}
```

### While loop
```javascript
let count = 0;
while (count < 5) {
    console.log(count);
    count++;
}
```

### Arrays
```javascript
let numbers = [1, 2, 3, 4, 5];
```

### Array access
```javascript
let firstNumber = numbers[0];
```

### Array iteration (forEach)
```javascript
numbers.forEach(number => {
    console.log(number);
});
```

### Functions
```javascript
function greet(name) {
    return `Hello, ${name}!`;
}
```

### Arrow functions
```javascript
const add = (a, b) => a + b;
```

### Object Literal
```javascript
const person = {
    name: "Alice",
    age: 25
};
```

### Object access
```javascript
const name = person.name;
```

### Object methods
```javascript
const greet = () => {
    console.log(`Hello, my name is ${person.name}.`);
};
```

### OBject destructuring
```javascript
const { name, age } = person;
```

### Classes and Constructors
```javascript
class Person {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }
}
```

### Class methods
```javascript
class Person {
    greet() {
        console.log(`Hello, my name is ${this.name}.`);
    }
}
```

### Inheritance
```javascript
class Student extends Person {
    constructor(name, age, school) {
        super(name, age);
        this.school = school;
    }
}
```

### Template Literals
```javascript
const message = `My name is ${name} and I am ${age} years old.`;
```

### Math Operations
```javascript
const result = Math.abs(-5);
```

### Random number generation
```javascript
const randomNum = Math.floor(Math.random() * 100);
```

### Date and Time (using Date object)
```javascript
const currentDate = new Date();
```	

### toUpperCase
```javascript
const text = "Hello, World!";
const upperText = text.toUpperCase();
```

### String Splitting
```javascript
const words = text.split(", ");
```

### String Joining
```javascript
const joinedText = words.join(", ");
```

### Working with Sets
```javascript
const mySet = new Set([1, 2, 3, 4, 5]);
```

### Set operations (intersection)
```javascript
const intersection = new Set([...mySet].filter(x => otherSet.has(x)));
```

### Working with Maps
```javascript
const myMap = new Map();
myMap.set("name", "Alice");
myMap.set("age", 25);
```

### Map operations (getting values)
```javascript
const value = myMap.get("name");
```

### Map iteration
```javascript
for (const [key, value] of myMap) {
    console.log(key, value);
}
```

### Promises (Async/Await)
```javascript
async function fetchData() {
    try {
        const response = await fetch(url);
        const data = await response.json();
        console.log(data);
    } catch (error) {
        console.error(error);
    }
}
```

### Fetch API (GET request)
```javascript
fetch(url)
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error(error));
```

### Fetch API (POST request)
```javascript
fetch(url, {
    method: "POST",
    body: JSON.stringify(data),
    headers: {
        "Content-Type": "application/json"
    }
})
.then(response => response.json())
.then(data => console.log(data))
.catch(error => console.error(error));
```

### Asynchronous Iteration (for...of with async/await)
```javascript
const fetchData = async () => {
    for (const item of items) {
        const result = await processItem(item);
        console.log(result);
    }
};
```

### Local storage (storing data)
```javascript
localStorage.setItem("key", "value");
```

### Local storage (Retrieving data)
```javascript
const data = localStorage.getItem("key");
```

### Event Listeners
```javascript
document.getElementById("myButton").addEventListener("click", () => {
    console.log("Button clicked!");
});
```

### Debouncing an input field
```javascript
const debounce = (func, delay) => {
    let timeout;
    return (...args) => {
        clearTimeout(timeout);
        timeout = setTimeout(() => func(...args), delay);
    };
};
```

### Throttling an Event
```javascript
const throttle = (func, limit) => {
    let inThrottle;
    return (...args) => {
        if (!inThrottle) {
            func(...args);
            inThrottle = true;
            setTimeout(() => (inThrottle = false), limit);
        }
    };
};
```

### Creating a custom event and handling it
```javascript
const customEvent = new Event("myEvent");
element.addEventListener("myEvent", () => {
    console.log("Custom event triggered");
});
element.dispatchEvent(customEvent);
```

### Using promises to fetch multiple resources
```javascript
const fetchData = async () => {
    const [data1, data2] = await Promise.all([fetch(url1), fetch(url2)]);
    const result1 = await data1.json();
    const result2 = await data2.json();
    console.log(result1, result2);
};
```

### Higher-Order Functions (map)
```javascript
const numbers = [1, 2, 3, 4, 5];
const squaredNumbers = numbers.map(num => num ** 2);
```

### Working with Callback Functions
```javascript
function fetchData(callback) {
    setTimeout(() => {
        const data = "Some data";
        callback(data);
    }, 1000);
}
```

### Using the reduce Function
```javascript
const numbers = [1, 2, 3, 4, 5];
const sum = numbers.reduce((accumulator, currentValue) => accumulator + currentValue, 0);
```

### Closures and function factories
```javascript
function createCounter() {
    let count = 0;
    return () => {
        count++;
        return count;
    };
}
const counter = createCounter();
```

### Currying and partial application
```javascript
const multiply = a => b => a * b;
const double = multiply(2);
const result = double(5);
```

### Working with async iterators (async generator)
```javascript
async function* asyncGenerator() {
    yield 1;
    await new Promise(resolve => setTimeout(resolve, 1000));
    yield 2;
}
```

### Fetching data with Axios
```javascript
axios.get(url)
    .then(response => console.log(response.data))
    .catch(error => console.error(error));
```

### Using localStorage with JSON data
```javascript
const data = { name: "Alice", age: 25 };
localStorage.setItem("userData", JSON.stringify(data));
const retrievedData = JSON.parse(localStorage.getItem("userData"));
```

### Working with WebSockets (using WebSocket API)
```javascript
const socket = new WebSocket("ws://example.com/socket");
socket.addEventListener("open", event => {
    console.log("WebSocket connection opened.");
});
```

### Using the localStorage API for Persistence
```javascript
localStorage.setItem("key", "value");
const storedValue = localStorage.getItem("key");
```

### handling forms and forms submission
```javascript
const form = document.getElementById("myForm");
form.addEventListener("submit", event => {
    event.preventDefault();
    const formData = new FormData(form);
    // Process form data or send it to the server.
});
```

### Implementing simple javascript router
```javascript
const routes = {
    "/": () => console.log("Home Page"),
    "/about": () => console.log("About Page"),
    "/contact": () => console.log("Contact Page")
};
const navigateTo = path => {
    history.pushState({}, "", path);
    routes[path]();
};
```

### Using localstorage for User Preferences
```javascript
const darkModeEnabled = localStorage.getItem("darkMode") === "true";
if (darkModeEnabled) {
    // Enable dark mode.
}
```

###  Implementing a Simple Event Bus (Pub/Sub Pattern)
```javascript
class EventBus {
    constructor() {
        this.events = {};
    }
    subscribe(eventName, callback) {
        if (!this.events[eventName]) {
            this.events[eventName] = [];
        }
        this.events[eventName].push(callback);
    }
    publish(eventName, data) {
        if (this.events[eventName]) {
            this.events[eventName].forEach(callback => callback(data));
        }
    }
}
const eventBus = new EventBus();
eventBus.subscribe("userLoggedIn", userData => {
    console.log(`User ${userData.username} logged in.`);
});
eventBus.publish("userLoggedIn", { username: "Alice" });
```

### Working with web workers (dedicated worker)
```javascript
const worker = new Worker("worker.js");
worker.postMessage({ task: "doWork" });
worker.onmessage = event => {
    console.log(event.data);
};
```

### Using the fetch API with Error Handling (async/await)
```javascript
try {
    const response = await fetch(url);
    if (!response.ok) {
        throw new Error("HTTP error! Status: " + response.status);
    }
    const data = await response.json();
    console.log(data);
} catch (error) {
    console.error("Fetch error:", error);
}
```

### Functional Programming with map, filter, and reduce (ES6)
```javascript
const numbers = [1, 2, 3, 4, 5];
const squaredEvenNumbers = numbers
    .filter(num => num % 2 === 0)
    .map(num => num ** 2)
    .reduce((acc, val) => acc + val, 0);
```

### Using the IntersectionObserver API for Lazy Loading Images
```javascript
const observer = new IntersectionObserver(entries => {
    entries.forEach(entry => {
        if (entry.isIntersecting) {
            const lazyImage = entry.target;
            lazyImage.src = lazyImage.dataset.src;
            observer.unobserve(lazyImage);
        }
    });
});
document.querySelectorAll(".lazy-image").forEach(img => observer.observe(img));
```

### Implementing a Simple Drag-and-Drop Feature
```javascript
const draggableElement = document.getElementById("draggable");
draggableElement.addEventListener("dragstart", event => {
    event.dataTransfer.setData("text/plain", event.target.id);
});
const dropZone = document.getElementById("drop-zone");
dropZone.addEventListener("dragover", event => {
    event.preventDefault();
});
dropZone.addEventListener("drop", event => {
    event.preventDefault();
    const data = event.dataTransfer.getData("text/plain");
    const draggedElement = document.getElementById(data);
    dropZone.appendChild(draggedElement);
});
```