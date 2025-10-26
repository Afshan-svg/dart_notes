# GridView in Flutter

The **GridView** widget in Flutter is used to display items in a **grid layout**. It is useful for showing products, images, or cards in rows and columns, commonly used in e-commerce apps.

---

## Types of GridView

1. **GridView.count** – Creates a grid with a fixed number of columns.
2. **GridView.builder** – Creates a grid dynamically using a builder function.
3. **GridView.extent** – Creates a grid with a maximum cross-axis extent for each item.

---

## Example: GridView.count (E-commerce Product Grid)

```dart
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: Text('Product Grid')),
        body: GridView.count(
          crossAxisCount: 2, // 2 columns
          padding: EdgeInsets.all(10),
          crossAxisSpacing: 10,
          mainAxisSpacing: 10,
          children: List.generate(6, (index) {
            return Card(
              elevation: 5,
              child: Column(
                mainAxisAlignment: MainAxisAlignment.center,
                children: [
                  Icon(Icons.shopping_bag, size: 50, color: Colors.blue),
                  SizedBox(height: 10),
                  Text('Product ${index + 1}', style: TextStyle(fontWeight: FontWeight.bold)),
                  Text('\$${(index + 1) * 10}'),
                ],
              ),
            );
          }),
        ),
      ),
    );
  }
}
````

**Explanation:**

* `crossAxisCount: 2` means **2 columns**.
* `crossAxisSpacing` and `mainAxisSpacing` add space between grid items.
* `List.generate` creates multiple product cards dynamically.
* Commonly used in **e-commerce apps** to display products in a grid layout.

---

## Key Points

* Use **GridView.count** for fixed columns.
* Use **GridView.builder** for large or dynamic lists to improve performance.
* Customize item size, spacing, and aspect ratio using **GridView** properties.
