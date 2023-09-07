## Implicit interfaces

### A basic interface

```dart
// A person. The implicit interface contains greet().
class Person {
  // In the interface, but visible only in this library.
  final String _name;

  // Not in the interface, since this is a constructor.
  Person(this._name);

  // In the interface.
  String greet(String who) => 'Hello, $who. I am $_name.';
}

// An implementation of the Person interface.
class Impostor implements Person {
  String get _name => '';

  String greet(String who) => 'Hi $who. Do you know who I am?';
}

String greetBob(Person person) => person.greet('Bob');

void main() {
  print(greetBob(Person('Kathy'))); // Hello, Bob. I am Kathy.
  print(greetBob(Impostor())); // Hi Bob. Do you know who I am?
}
```

### Extending a class

```dart
class Phone {

    void use(){
        _call();
        _sendMessage();
    }
}
// Use extends to create a subclass
class SmartPhone extends Phone {
    void use(){
        // use super to refer to the superclass
        super.use();
        _takePhotos();
        _playGames();
    }
}
```
