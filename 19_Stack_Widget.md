# Stack Widget in Flutter

The **Stack** widget in Flutter allows you to **place widgets on top of each other**, similar to layers. It is useful for creating overlapping designs, badges, or custom layouts.

---

## Key Points

- Children are positioned **from bottom to top**.
- Can be combined with **Positioned** widget for precise placement.
- Useful for **badges, overlay buttons, and image effects**.

---

## Syntax

```dart
Stack(
  children: [
    Widget1(),
    Widget2(),
    Positioned(
      top: 10,
      left: 10,
      child: Widget3(),
    ),
  ],
)
````

---

## Example: E-commerce Product with Discount Badge

```dart
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: Text('Stack Widget Example')),
        body: Center(
          child: Stack(
            children: [
              Container(
                width: 200,
                height: 250,
                decoration: BoxDecoration(
                  color: Colors.white,
                  borderRadius: BorderRadius.circular(15),
                  boxShadow: [BoxShadow(color: Colors.grey, blurRadius: 5)],
                ),
                child: Column(
                  mainAxisAlignment: MainAxisAlignment.center,
                  children: [
                    Image.network('https://example.com/shoes.png', height: 120),
                    SizedBox(height: 10),
                    Text('Running Shoes', style: TextStyle(fontWeight: FontWeight.bold)),
                    Text('\$50', style: TextStyle(color: Colors.green)),
                  ],
                ),
              ),
              Positioned(
                top: 10,
                right: 10,
                child: Container(
                  padding: EdgeInsets.all(8),
                  decoration: BoxDecoration(
                    color: Colors.red,
                    borderRadius: BorderRadius.circular(8),
                  ),
                  child: Text('20% OFF', style: TextStyle(color: Colors.white)),
                ),
              ),
            ],
          ),
        ),
      ),
    );
  }
}
```

**Explanation:**

* The main product card is the **base widget**.
* `Positioned` places the **discount badge** on top-right of the card.
* Stack is useful in **e-commerce apps** for overlapping elements like badges, sale labels, or custom overlays.
