## Futures

### Async Await

```dart
// functionswhich are asynchronous: they return after setting up a possibly time-consuming operation
// The async and await keywords support asynchronous programming

Future<String> login() {
 String userName="Temidjoy";
 return
  Future.delayed(
    Duration(seconds: 4), () => userName);
}

// Asynchronous
main() async {
 print('Authenticating please wait...');
 print(await userName());
}
```
