# Get User Input in Dart/Flutter

Getting user input is essential for interactive apps, such as forms, search bars, or login screens in e-commerce apps.

---

## 1. User Input in Console (Dart)

For simple Dart programs running in the console, use the `dart:io` library.

```dart
import 'dart:io';

void main() {
  print('Enter your name:');
  String? name = stdin.readLineSync();

  print('Hello, $name!');
}
````

* `stdin.readLineSync()` reads a line of input from the user.
* Returns a `String?` which may be `null` if no input is provided.

---

## 2. User Input in Flutter (TextField)

In Flutter apps, use a `TextField` widget to get input from users.

```dart
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: Text('User Input Example')),
        body: UserInputForm(),
      ),
    );
  }
}

class UserInputForm extends StatefulWidget {
  @override
  _UserInputFormState createState() => _UserInputFormState();
}

class _UserInputFormState extends State<UserInputForm> {
  TextEditingController nameController = TextEditingController();

  @override
  Widget build(BuildContext context) {
    return Padding(
      padding: EdgeInsets.all(16),
      child: Column(
        children: [
          TextField(
            controller: nameController,
            decoration: InputDecoration(
              labelText: 'Enter your name',
              border: OutlineInputBorder(),
            ),
          ),
          SizedBox(height: 20),
          ElevatedButton(
            onPressed: () {
              String name = nameController.text;
              print('Hello, $name!');
            },
            child: Text('Submit'),
          ),
        ],
      ),
    );
  }
}
```

**Explanation:**

* `TextField` collects user input.
* `TextEditingController` manages the input value.
* `ElevatedButton` triggers the action to read and use the input.

**Use Case in E-commerce:**

* Collect user name, email, or shipping address in checkout forms.
* Search products using a TextField input.
