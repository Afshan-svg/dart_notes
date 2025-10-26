# Expanded Widget in Flutter

The **Expanded** widget in Flutter is used inside a **Row, Column, or Flex** widget to **fill available space**. It helps in creating flexible layouts that automatically adjust according to the screen size.

## Key Points

- Expands a child to fill the remaining space in the main axis.
- Can be combined with multiple children using the `flex` property.
- Helps in **responsive UI** design.

## Syntax

```dart
Expanded({
  Key? key,
  int flex = 1,
  required Widget child,
})
````

* `flex`: Determines how much space the child will take relative to other Expanded widgets.
* `child`: The widget to expand.

## Example: E-commerce Layout with Expanded

```dart
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: Text('Expanded Widget Example')),
        body: Row(
          children: [
            Expanded(
              flex: 2,
              child: Container(
                color: Colors.blue,
                height: 100,
                child: Center(child: Text('Product Image', style: TextStyle(color: Colors.white))),
              ),
            ),
            Expanded(
              flex: 3,
              child: Container(
                color: Colors.green,
                height: 100,
                child: Column(
                  mainAxisAlignment: MainAxisAlignment.center,
                  children: [
                    Text('Product Name', style: TextStyle(fontSize: 16, fontWeight: FontWeight.bold)),
                    Text('\$50', style: TextStyle(fontSize: 14, color: Colors.white)),
                  ],
                ),
              ),
            ),
          ],
        ),
      ),
    );
  }
}
```

**Explanation:**

* The **Row** has two children wrapped in `Expanded`.
* `flex: 2` makes the first container take 2 parts of the available space, and `flex: 3` makes the second container take 3 parts.
* Useful in **e-commerce apps** to create responsive product cards where images and details share space proportionally.

```
