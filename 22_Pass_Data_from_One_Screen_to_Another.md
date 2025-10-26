# Pass Data from One Screen to Another in Flutter

In Flutter, you can **pass data between screens** using the `Navigator` when navigating. This is commonly used in e-commerce apps to send **product details** from a product list to a product details page.

---

## Example: Passing Data Using Constructor

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

// First Screen: Product List
class HomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    String productName = 'Running Shoes';
    double price = 50.0;

    return Scaffold(
      appBar: AppBar(title: Text('Home Page')),
      body: Center(
        child: ElevatedButton(
          onPressed: () {
            Navigator.push(
              context,
              MaterialPageRoute(
                builder: (context) => ProductPage(
                  name: productName,
                  price: price,
                ),
              ),
            );
          },
          child: Text('View Product'),
        ),
      ),
    );
  }
}

// Second Screen: Product Details
class ProductPage extends StatelessWidget {
  final String name;
  final double price;

  ProductPage({required this.name, required this.price});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Product Page')),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Text('Product: $name', style: TextStyle(fontSize: 20)),
            Text('Price: \$${price}', style: TextStyle(fontSize: 18)),
          ],
        ),
      ),
    );
  }
}
````

---

## Key Points

* Pass data using **constructor parameters** when creating a new screen.
* Access the data in the new screen using the **final variables**.
* Commonly used in **e-commerce apps** to send product information, user info, or order details between screens.
