# Dart

## Getting Started

### Hello World

```dart
// top-level function where app execution starts
void main(){
    print("Hello World!"); // Print to console
}
```

### Variables

```dart
int x = 2; // explicitly typed
var p = 5; // type inferred - Generic var with type inference

dynamic z = 8; // variable can take on any type
z = "cool"; // cool

// if you never intend to change a variable use final or const. Something like this:

final email = "temid@gmail.com"; // Same as var but cannot be reassigned
final String email = "temid@gmail.com"; // you can't change the value

const qty = 5; // Compile-time constant
```

### Data types

```dart
int age = 20; // integers, range -2^63 to 2^63 - 1
double height = 1.85; // floating-point numbers

// You can also declare a variable as a num
num x = 1;  // x can have both int and double values
num += 2.5;
print(num); //Print: 3.5

String name = "Nicola";

bool isFavourite = true;
bool isLoaded = false;
```

### String interpolation

```dart
// can use single or double qoutes for String type
var firstName = 'Nicola';
var lastName = "Tesla";

//can embed variables in string with $
String fullName = "$firstName $lastName";

// concatenate with +
var name = "Albert " + "Einstein";

String upperCase = '${firstName.toUpperCase()}';
print(upperCase); //Print: NICOLA
```

### Comments

```dart
// This is a normal, one-line comment.

/// This is a documentation comment, used to document libraries,
/// classes, and their members. Tools like IDEs and dartdoc treat
/// doc comments specially.

/* Comments like these are also supported. */
```

### Imports

```dart
// Importing core libraries
import 'dart:math';

// Importing libraries from external packages
import 'package:test/test.dart';

// Importing files
import 'path/to/my_other_file.dart';
```
