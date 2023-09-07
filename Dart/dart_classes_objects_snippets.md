## Classes and Objects

### Class

```dart
class Cat {
    String name;

    // method
    void voice(){
        print("Meow");
    }
}
```

### Object

```dart
// instance of a class
// below myCat is Object of class Cat

void main(){
    Cat myCat = Cat();
    myCat.name = "Kitty";
    myCat.voice(); // Prints: Meow
}
```

### Constructors

```dart
class Cat {
    String name;
    Cat(this.name);
}
void main(){
    Cat myCat = Cat("Kitty");
    print(myCat.name); // Prints: Kitty
}
```

### Abstract Classes

```dart
// abstract class—a class that can’t be instantiated
// This class is declared abstract and thus can't be instantiated.
abstract class AbstractContainer {
  // Define constructors, fields, methods...

  void updateChildren(); // Abstract method.
}
```

### Getters Setters

```dart
// provide read and write access to an object’s properties
class Cat {
    String name;

    // getter
    String get catName {
        return name;
    }

    // setter
    void set catName(String name){
        this.name = name;
    }
}
```
