# Flutter Widgets

In Flutter, **everything is a widget**. Widgets are the **building blocks of a Flutter app's UI**. They define the structure, appearance, and behavior of the app.

## Types of Widgets

1. **Stateless Widget**
   - Immutable; its properties **cannot change** once created.
   - Used for static UI elements.

```dart
class MyText extends StatelessWidget {
  final String text;

  MyText({required this.text});

  @override
  Widget build(BuildContext context) {
    return Text(text, style: TextStyle(fontSize: 18));
  }
}
````

2. **Stateful Widget**

   * Mutable; can **change its state** during runtime.
   * Used for dynamic UI, e.g., buttons, counters, forms.

```dart
class Counter extends StatefulWidget {
  @override
  _CounterState createState() => _CounterState();
}

class _CounterState extends State<Counter> {
  int count = 0;

  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        Text('Count: $count'),
        ElevatedButton(
          onPressed: () {
            setState(() {
              count++;
            });
          },
          child: Text('Increment'),
        ),
      ],
    );
  }
}
```

---

## Common Flutter Widgets

| Widget           | Purpose                                        |
| ---------------- | ---------------------------------------------- |
| `Container`      | A box for styling, padding, margin, background |
| `Row` & `Column` | Arrange children horizontally or vertically    |
| `Text`           | Display text                                   |
| `Image`          | Display images                                 |
| `ListView`       | Scrollable list of widgets                     |
| `Stack`          | Layer widgets on top of each other             |
| `Card`           | Material design styled container               |
| `Expanded`       | Fill available space in Row/Column             |
| `Padding`        | Add space around widgets                       |
| `ElevatedButton` | Button with elevation                          |

---

## E-commerce Example

```dart
Column(
  children: [
    Image.network('https://example.com/shoes.png', height: 100),
    Text('Running Shoes', style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold)),
    Text('\$50', style: TextStyle(color: Colors.green)),
    ElevatedButton(onPressed: () {}, child: Text('Add to Cart')),
  ],
)
```

**Explanation:**

* `Column` arranges product image, name, price, and button vertically.
* Widgets can be **combined and nested** to build complex UIs.
* Understanding widgets is key to designing **responsive and modern e-commerce apps**.

```
