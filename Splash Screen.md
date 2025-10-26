# Splash Screen in Flutter

A **Splash Screen** is the first screen that appears when an app is launched. It is commonly used to show the **app logo, brand, or loading animation** before the main content loads.

---

## Why Use a Splash Screen?

- Provides a **professional look** to the app.
- Gives time for **initial setup or data loading**.
- Improves **user experience** by reducing perceived loading time.

---

## Example: Simple Splash Screen

```dart
import 'package:flutter/material.dart';
import 'dart:async';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: SplashScreen(),
    );
  }
}

class SplashScreen extends StatefulWidget {
  @override
  _SplashScreenState createState() => _SplashScreenState();
}

class _SplashScreenState extends State<SplashScreen> {
  @override
  void initState() {
    super.initState();
    // Navigate to HomePage after 3 seconds
    Timer(Duration(seconds: 3), () {
      Navigator.pushReplacement(
        context,
        MaterialPageRoute(builder: (context) => HomePage()),
      );
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Icon(Icons.shopping_cart, size: 100, color: Colors.blue),
            SizedBox(height: 20),
            Text('E-Commerce App', style: TextStyle(fontSize: 24, fontWeight: FontWeight.bold)),
          ],
        ),
      ),
    );
  }
}

// Main Home Page
class HomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Home Page')),
      body: Center(child: Text('Welcome to the E-Commerce App!')),
    );
  }
}
````

**Explanation:**

* `SplashScreen` shows a logo and app name for **3 seconds**.
* After the timer, it navigates to `HomePage` using `Navigator.pushReplacement`.
* Splash screens are commonly used in **e-commerce apps** to display branding before the product list loads.
