## Functions

### Functions

```dart
// functions in dart are objects and have a type
int add(int a, int b){
    return a+b;
}

// functions can be assigned to variables
int sum = add(2,3); // returns: 5

// can be passed as arguments to other functions
int totalSum = add(2, add(2,3)); // returns : 7
```

### Arrow Syntax (=>)

```dart
// functions that contain just one expression, you can use a shorthand syntax
bool isFav(Product product) => favProductsList.contains(product);
```

### Anonymous (lambda) functions

```dart
// small one line functions that dont have name
int add(a,b) => a+b;

// lambda functions mostly passed as parameter to other functions
const list = ['apples', 'bananas', 'oranges'];
list.forEach(
(item) => print('${list.indexOf(item)}: $item'));
//Prints: 0: apples 1: bananas 2: oranges
```
