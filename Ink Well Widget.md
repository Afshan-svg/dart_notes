# InkWell Widget in Flutter

The **InkWell** widget in Flutter is used to make any widget **clickable or tappable**. It provides a **ripple effect** when the user taps on it, following Material Design guidelines.

---

## Key Features

- Adds **tap functionality** to any widget.
- Provides **visual feedback** like ripple effects.
- Can handle gestures like `onTap`, `onDoubleTap`, `onLongPress`.

---

## Syntax

```dart
InkWell({
  required Widget child,
  void Function()? onTap,
  void Function()? onDoubleTap,
  void Function()? onLongPress,
})
````

* `child`: The widget that will be tappable.
* `onTap`: Function executed when the widget is tapped.
* `onDoubleTap`: Function executed on double tap.
* `onLongPress`: Function executed on long press.

---

## Example: E-commerce Add to Cart Button

```dart
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: Text('InkWell Example')),
        body: Center(
          child: InkWell(
            onTap: () {
              print('Product Added to Cart');
            },
            borderRadius: BorderRadius.circular(8),
            splashColor: Colors.blue.withOpacity(0.3),
            child: Container(
              padding: EdgeInsets.symmetric(vertical: 15, horizontal: 25),
              decoration: BoxDecoration(
                color: Colors.green,
                borderRadius: BorderRadius.circular(8),
              ),
              child: Text(
                'Add to Cart',
                style: TextStyle(color: Colors.white, fontSize: 16),
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

* `InkWell` wraps the container and makes it **tappable**.
* `splashColor` defines the ripple effect color.
* Useful in **e-commerce apps** for clickable product cards, buttons, or icons.
