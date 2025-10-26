# ScrollView in Flutter

A **ScrollView** in Flutter allows users to **scroll content** that overflows the screen. It is essential when the content cannot fit in a single view, such as long lists, forms, or product catalogs in e-commerce apps.

## Types of ScrollView

1. **SingleChildScrollView**
   - Scrolls a **single child widget**.
   - Useful for forms or content with varying height.

2. **ListView**
   - Scrolls a **list of widgets**.
   - Supports lazy loading, separators, and builders.

3. **CustomScrollView**
   - Advanced scrolling using **slivers** for complex layouts.

---

## Example: SingleChildScrollView (E-commerce Product List)

```dart
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: Text('ScrollView Example')),
        body: SingleChildScrollView(
          child: Column(
            children: List.generate(20, (index) {
              return Card(
                margin: EdgeInsets.all(10),
                child: ListTile(
                  leading: Icon(Icons.shopping_cart),
                  title: Text('Product ${index + 1}'),
                  subtitle: Text('Price: \$${(index + 1) * 5}'),
                ),
              );
            }),
          ),
        ),
      ),
    );
  }
}
````

**Explanation:**

* `SingleChildScrollView` allows the **Column** of product cards to scroll vertically.
* `List.generate` creates multiple product cards dynamically.
* Essential for **e-commerce apps** to display product lists without cutting off content.

---

## Key Points

* Use **SingleChildScrollView** for a single child that may overflow.
* Use **ListView** for long lists with many items.
* Combine with **Expanded** or **Flexible** for responsive layouts.

```
