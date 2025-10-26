# Card Widget in Flutter

The **Card** widget in Flutter is used to create a **material design styled container** with rounded corners, shadows, and elevation. It is commonly used to display related information like product details, user profiles, or articles.

## Features

- Rounded corners
- Shadow (elevation)
- Padding and margin support
- Can contain any child widget

## Syntax

```dart
Card({
  Key? key,
  double? elevation,
  Color? color,
  ShapeBorder? shape,
  Widget? child,
})
````

## Example: E-commerce Product Card

```dart
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: Text('Product Card')),
        body: Center(
          child: Card(
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
                  Image.network(
                    'https://example.com/shoes.png',
                    height: 100,
                  ),
                  SizedBox(height: 10),
                  Text(
                    'Running Shoes',
                    style: TextStyle(
                      fontSize: 18,
                      fontWeight: FontWeight.bold,
                    ),
                  ),
                  SizedBox(height: 5),
                  Text(
                    '\$50',
                    style: TextStyle(
                      fontSize: 16,
                      color: Colors.green,
                    ),
                  ),
                  SizedBox(height: 10),
                  ElevatedButton(
                    onPressed: () {},
                    child: Text('Add to Cart'),
                  ),
                ],
              ),
            ),
          ),
        ),
      ),
    );
  }
}
```

**Explanation:**

* `Card` provides a **shadow and rounded edges** for the container.
* Inside the card, we used a `Column` to display **image, title, price, and button**.
* Commonly used in **e-commerce apps** to display products in a visually appealing way.

```
