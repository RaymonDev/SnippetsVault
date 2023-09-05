## TypeScript

### Declare a variable
```typescript
let variableName: dataType;
```

### Initialize a variable
```typescript
let count: number = 10;
```

### Declare a constant
```typescript
const PI: number = 3.14159265359;
```

### Type annotations for functions
```typescript
function greet(name: string): string {
    return `Hello, ${name}!`;
}
```

### Optional functions parameters
```typescript
function printMessage(message: string, prefix?: string) {
    if (prefix) {
        console.log(`${prefix}: ${message}`);
    } else {
        console.log(message);
    }
}
```

### Default function parameters
```typescript
function greet(name: string, greeting: string = "Hello") {
    console.log(`${greeting}, ${name}!`);
}
```

### Arrow function (Lambda expression)
```typescript
const add = (a: number, b: number): number => a + b;
```

### Interface
```typescript
interface Person {
    name: string;
    age: number;
}
```

### Class Declaration
```typescript
class Car {
    make: string;
    constructor(make: string) {
        this.make = make;
    }
}
```

### Class inheritance
```typescript
class SportsCar extends Car {
    topSpeed: number;
    constructor(make: string, topSpeed: number) {
        super(make);
        this.topSpeed = topSpeed;
    }
}
```

### Access modifiers in classes
```typescript
class Animal {
    private name: string;
    constructor(name: string) {
        this.name = name;
    }
}
```

### Abstract classes
```typescript
abstract class Shape {
    abstract area(): number;
}
```

### Type Aliases
```typescript
type Point = { x: number; y: number };
```

### Union Types
```typescript
let result: string | number;
result = "success";
result = 42;
```

### Type assertion (type casting)
```typescript
let value: any = "Hello, TypeScript!";
let length: number = (value as string).length;
```

### Generics
```typescript
function identity<T>(arg: T): T {
    return arg;
}
```

### Enums
```typescript
enum Color {
    Red,
    Green,
    Blue,
}
```

### Array iteration with forEach
```typescript
const numbers: number[] = [1, 2, 3, 4, 5];
numbers.forEach((num) => console.log(num));
```

### Array mappping
```typescript
const doubled = numbers.map((num) => num * 2);
```

### Array filtering
```typescript
const evenNumbers = numbers.filter((num) => num % 2 === 0);
```

### Object destructuring
```typescript
const { name, age } = person;
```

### Spread operator
```typescript
const parts = [1, 2, 3];
const whole = [...parts, 4, 5];
```

### Rest parameters
```typescript
function sum(...nums: number[]): number {
    return nums.reduce((total, num) => total + num, 0);
}
```

### Promises
```typescript
const fetchData = (): Promise<Data> => {
    return fetch("https://example.com/data")
        .then((response) => response.json())
        .catch((error) => {
            throw new Error("Error fetching data");
        });
};
```

### Async/Await
```typescript
async function fetchData(): Promise<Data> {
    try {
        const response = await fetch("https://example.com/data");
        return await response.json();
    } catch (error) {
        throw new Error("Error fetching data");
    }
}
```

### Type guards for instanceof
```typescript
if (myVar instanceof MyClass) {
    // myVar is an instance of MyClass
}
```

### Type guards for typeof
```typescript
if (typeof myVar === "string") {
    // myVar is a string
}
```

### Type guards for custom types
```typescript
function isPerson(obj: any): obj is Person {
    return "name" in obj && "age" in obj;
}
```

### Nullish coallescing operator
```typescript
const result = value ?? defaultValue;
```

### Optional chaining
```typescript
const city = user?.address?.city;
```

### Non-Nullable assertion operator
```typescript
let element: HTMLElement | null = document.getElementById("example")!;
```

### Decorators
```typescript
function log(target: Object, key: string | symbol, descriptor: PropertyDescriptor) {
    const originalMethod = descriptor.value;
    descriptor.value = function (...args: any[]) {
        console.log(`Calling ${key.toString()} with arguments: ${args.join(", ")}`);
        return originalMethod.apply(this, args);
    };
}
```

### Type inference with as const
```typescript
const config = {
    API_URL: "https://api.example.com",
    MAX_RESULTS: 10,
} as const;
```

### Conditional types
```typescript
type IsString<T> = T extends string ? true : false;
```

### Indexed access types
```typescript
type PersonName = Person["name"];
```

### Mapped types
```typescript
type Optional<T> = {
    [K in keyof T]?: T[K];
};
```

### Type guards with never
```typescript
function assertNever(value: never): never {
    throw new Error(`Unexpected value: ${value}`);
}
```

### Module Imports/Exports
```typescript
// Export
export function add(a: number, b: number): number {
    return a + b;
}

// Import
import { add } from "./math";
```

### Intersectio types
```typescript
type Admin = {
    name: string;
    privileges: string[];
};

type Employee = {
    name: string;
    startDate: Date;
};

type ElevatedEmployee = Admin & Employee;
```

### Type guards for discriminated unions
```typescript
type Result<T> = { success: true; value: T } | { success: false; error: string };

function handleResult(result: Result<number>) {
    if (result.success) {
        console.log(`Result is ${result.value}`);
    } else {
        console.error(`Error: ${result.error}`);
    }
}
```

### Conditional (ternary) operator
```typescript
type User = {
    isAdmin: boolean;
};

type Permission = User["isAdmin"] extends true ? "Admin" : "User";
```

### Keyof and Lookup Types
```typescript
type User = {
    id: number;
    name: string;
    email: string;
};

type UserKeys = keyof User;
type UserType = User["name"];
```

### Type inference with Generics
```typescript
function firstElement<T>(arr: T[]): T {
    return arr[0];
}

const element = firstElement([1, 2, 3]); // element is inferred as number
```

### Conditional types with generics
```typescript
type TypeName<T> = T extends string ? "string" : T extends number ? "number" : "other";
```

### Template literal types
```typescript
type Greeting = `Hello, ${string}!`;
const greeting: Greeting = "Hello, TypeScript!";
```

### Using mapped types with partial
```typescript
type PartialUser = Partial<User>;
```

### Using mapped types with record
```typescript
type CountryPopulation = Record<"USA" | "Canada" | "Mexico", number>;
```

### Type-safe Event Handling
```typescript
class EventEmitter<T> {
    private listeners: Record<string, ((data: T) => void)[]> = {};

    on(event: string, listener: (data: T) => void) {
        if (!this.listeners[event]) {
            this.listeners[event] = [];
        }
        this.listeners[event].push(listener);
    }

    emit(event: string, data: T) {
        const eventListeners = this.listeners[event];
        if (eventListeners) {
            eventListeners.forEach((listener) => listener(data));
        }
    }
}
```

### Indexed access with tuples
```typescript
type Tuple = [string, number, boolean];
type SecondElement = Tuple[1]; // number
```

### Recursive types
```typescript
type TreeNode<T> = {
    value: T;
    left?: TreeNode<T>;
    right?: TreeNode<T>;
};
```

### Type-safe object merging
```typescript
type Merge<T, U> = {
    [K in keyof T]: K extends keyof U ? U[K] : T[K];
};

const mergedObj = merge({ a: 1, b: "string" }, { b: 2, c: true });
```

### using the keyof operator for object keys
```typescript
function getProperty<T, K extends keyof T>(obj: T, key: K) {
    return obj[key];
}

const user = { id: 1, name: "John" };
const id = getProperty(user, "id");
```

### Function overloading
```typescript
function createElement(tag: "div"): HTMLDivElement;
function createElement(tag: "span"): HTMLSpanElement;
function createElement(tag: string): HTMLElement {
    return document.createElement(tag);
}
```

### Discriminated Union with Function Types
```typescript
type Shape =
    | { kind: "circle"; radius: number }
    | { kind: "rectangle"; width: number; height: number };

function calculateArea(shape: Shape): number {
    switch (shape.kind) {
        case "circle":
            return Math.PI * shape.radius ** 2;
        case "rectangle":
            return shape.width * shape.height;
    }
}
```

### Conditional type inference with infer
```typescript
type ExtractReturnType<T> = T extends (...args: any[]) => infer R ? R : never;
```

### Using TypeScript with React
```typescript
interface Props {
    name: string;
}

const MyComponent: React.FC<Props> = ({ name }) => {
    return <div>Hello, {name}!</div>;
};
```

### Type-safe Axios Requests (Example)
```typescript
import axios from "axios";

interface ApiResponse<T> {
    data: T;
    status: number;
}

async function fetchData<T>(url: string): Promise<T> {
    const response = await axios.get<ApiResponse<T>>(url);
    return response.data.data;
}
```







