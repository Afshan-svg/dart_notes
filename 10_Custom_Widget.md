# Custom Widget in Flutter

A **Custom Widget** in Flutter is a user-defined widget that helps **reusable and organized UI components**. Instead of writing the same UI code multiple times, you can create a custom widget and use it anywhere in the app.

## Creating a Custom Widget

There are two types of custom widgets:

1. **Stateless Widget** – UI does not change over time.
2. **Stateful Widget** – UI can change based on user interaction or data.

## Example: E-commerce Product Card as Custom Widget

```dart
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

// Main App
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: Text('Custom Widget Example')),
        body: Center(
          child: ProductCard(
            name: 'Running Shoes',
            price: 50.0,
            imageUrl: 'https://example.com/shoes.png',
          ),
        ),
      ),
    );
  }
}

// Custom ProductCard Widget
class ProductCard extends StatelessWidget {
  final String name;
  final double price;
  final String imageUrl;

  ProductCard({
    required this.name,
    required this.price,
    required this.imageUrl,
  });

  @override
  Widget build(BuildContext context) {
    return Card(
      elevation: 5,
      shape: RoundedRectangleBorder(
        borderRadius: BorderRadius.circular(15),
      ),
      child: Container(
        width: 200,
        padding: EdgeInsets.all(16),
        child: Column(
          mainAxisSize: MainAxisSize.min,
          children: [
            Image.network(imageUrl, height: 100),
            SizedBox(height: 10),
            Text(
              name,
              style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold),
            ),
            SizedBox(height: 5),
            Text(
              '\$${price}',
              style: TextStyle(fontSize: 16, color: Colors.green),
            ),
            SizedBox(height: 10),
            ElevatedButton(
              onPressed: () {},
              child: Text('Add to Cart'),
            ),
          ],
        ),
      ),
    );
  }
}
````

**Explanation:**

* `ProductCard` is a **custom widget** that takes `name`, `price`, and `imageUrl` as inputs.
* Using this widget, you can easily create multiple product cards without repeating code.
* Custom widgets are essential in **e-commerce apps** to build modular and reusable UI components.

```
