# Stateless vs Stateful Widgets in Flutter

In Flutter, widgets are the **building blocks of the UI**. They can be **stateless** or **stateful**, depending on whether they maintain **dynamic data**.

---

## 1. Stateless Widget

- Immutable: **cannot change its state** after being built.
- Useful for **static UI elements**.
- Built once and does not rebuild unless parent widget changes.

### Example: Product Name Display

```dart
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: Text('Stateless Widget Example')),
        body: Center(
          child: ProductName(name: 'Running Shoes'),
        ),
      ),
    );
  }
}

class ProductName extends StatelessWidget {
  final String name;

  ProductName({required this.name});

  @override
  Widget build(BuildContext context) {
    return Text(name, style: TextStyle(fontSize: 20, fontWeight: FontWeight.bold));
  }
}
````

---

## 2. Stateful Widget

* Mutable: **can change its state** during runtime.
* Useful for **dynamic UI**, e.g., counters, forms, cart quantity.
* Can rebuild itself using `setState()` when the state changes.

### Example: Product Quantity Selector

```dart
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: Text('Stateful Widget Example')),
        body: Center(
          child: QuantitySelector(),
        ),
      ),
    );
  }
}

class QuantitySelector extends StatefulWidget {
  @override
  _QuantitySelectorState createState() => _QuantitySelectorState();
}

class _QuantitySelectorState extends State<QuantitySelector> {
  int quantity = 1;

  @override
  Widget build(BuildContext context) {
    return Row(
      mainAxisAlignment: MainAxisAlignment.center,
      children: [
        IconButton(
          onPressed: () {
            setState(() {
              if (quantity > 1) quantity--;
            });
          },
          icon: Icon(Icons.remove),
        ),
        Text('$quantity', style: TextStyle(fontSize: 18)),
        IconButton(
          onPressed: () {
            setState(() {
              quantity++;
            });
          },
          icon: Icon(Icons.add),
        ),
      ],
    );
  }
}
```

---

## Key Differences

| Feature  | Stateless Widget       | Stateful Widget                |
| -------- | ---------------------- | ------------------------------ |
| State    | Immutable              | Mutable                        |
| Rebuild  | Only if parent changes | Can rebuild using `setState()` |
| Use Case | Static UI              | Dynamic UI, user interactions  |

**Use Case in E-commerce:**

* **Stateless:** Display product name, price, or static images.
* **Stateful:** Update cart quantity, toggle favorite products, or handle forms.
