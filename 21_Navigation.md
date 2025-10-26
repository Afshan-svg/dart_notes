# Navigation in Flutter

Navigation in Flutter allows you to **move between different screens or pages** in your app. It is essential for multi-page apps like e-commerce apps with product pages, cart, and checkout screens.

---

## 1. Using Navigator

Flutter uses the **Navigator widget** to manage routes (screens). You can **push** a new screen or **pop** back to the previous screen.

---

### Example: Basic Navigation

```dart
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: HomePage(),
    );
  }
}

// First Screen
class HomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Home Page')),
      body: Center(
        child: ElevatedButton(
          onPressed: () {
            Navigator.push(
              context,
              MaterialPageRoute(builder: (context) => ProductPage()),
            );
          },
          child: Text('Go to Product Page'),
        ),
      ),
    );
  }
}

// Second Screen
class ProductPage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Product Page')),
      body: Center(
        child: ElevatedButton(
          onPressed: () {
            Navigator.pop(context); // Go back to HomePage
          },
          child: Text('Back to Home'),
        ),
      ),
    );
  }
}
````

**Explanation:**

* `Navigator.push` opens a new screen.
* `Navigator.pop` returns to the previous screen.
* `MaterialPageRoute` defines the transition animation between screens.

---

## 2. Named Routes (Optional)

You can define **named routes** in `MaterialApp` for cleaner navigation.

```dart
MaterialApp(
  initialRoute: '/',
  routes: {
    '/': (context) => HomePage(),
    '/product': (context) => ProductPage(),
  },
);

// Navigate using
Navigator.pushNamed(context, '/product');
```

---

## Use Case in E-commerce

* Navigate from **product list** → **product details** → **checkout page**.
* Helps maintain a smooth user experience in **multi-screen apps**.
