# ListView in Flutter

The **ListView** widget in Flutter is used to display a **scrollable list of widgets**. It is one of the most commonly used widgets for showing lists like product catalogs, messages, or notifications in apps.

---

## Types of ListView

1. **ListView()** – Default constructor for a simple list.
2. **ListView.builder()** – Creates a **dynamic, lazy-loaded list** for better performance.
3. **ListView.separated()** – Creates a list with **separators** between items.
4. **ListView.custom()** – Advanced customization using a `SliverChildDelegate`.

---

## Example: ListView.builder (E-commerce Product List)

```dart
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  final List<String> products = [
    'Shoes', 'T-shirt', 'Watch', 'Bag', 'Sunglasses', 'Hat'
  ];

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: Text('Product List')),
        body: ListView.builder(
          itemCount: products.length,
          itemBuilder: (context, index) {
            return Card(
              margin: EdgeInsets.all(10),
              child: ListTile(
                leading: Icon(Icons.shopping_bag),
                title: Text(products[index]),
                subtitle: Text('Price: \$${(index + 1) * 10}'),
                trailing: Icon(Icons.add_shopping_cart),
              ),
            );
          },
        ),
      ),
    );
  }
}
````

**Explanation:**

* `ListView.builder` efficiently creates a scrollable list.
* `itemBuilder` generates each list item on demand.
* Commonly used in **e-commerce apps** to display products, orders, or cart items.

---

## Key Points

* Use **ListView.builder** for large or dynamic lists for performance.
* Wrap with **Expanded** if inside a Column to avoid layout issues.
* Combine with **InkWell** or **GestureDetector** for tappable list items.
