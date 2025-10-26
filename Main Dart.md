# Use of main.dart in Flutter

In Flutter, the **`main.dart`** file is the **entry point** of the application. Every Flutter app starts executing from the `main()` function defined in this file.

---

## Key Points

- Contains the **`main()` function** where the app starts.
- Usually imports other Dart files, widgets, and packages.
- Sets up the **root widget** using `runApp()`.
- Central place to configure **theme, routes, and global settings**.

---

## Syntax

```dart
void main() {
  runApp(MyApp());
}
````

* `runApp()` takes a **widget** (usually `MaterialApp` or `CupertinoApp`) as the root of the widget tree.
* `MyApp` is the root widget of the application.

---

## Example: main.dart in E-commerce App

```dart
import 'package:flutter/material.dart';
import 'home_page.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'E-commerce App',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: HomePage(), // Root page of the app
    );
  }
}
```

**Explanation:**

* `main()` starts the app.
* `MyApp` defines the **theme** and **home page**.
* All other widgets and screens are connected through this file.
* Essential for organizing and launching a **Flutter e-commerce app**.
