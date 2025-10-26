# Animations in Flutter

Animations in Flutter make apps more **interactive and visually appealing**. They help provide smooth transitions, movement, and feedback to users.

## Types of Animations

1. **Implicit Animations**
   - Simple and easy to use.
   - Flutter automatically handles the animation for property changes.
   - Example widgets: `AnimatedContainer`, `AnimatedOpacity`, `AnimatedPadding`.

2. **Explicit Animations**
   - More control over animation.
   - Requires `AnimationController` and `Animation` objects.
   - Example widgets: `FadeTransition`, `ScaleTransition`, `SlideTransition`.

## Example: Implicit Animation (E-commerce Button)

```dart
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(home: AnimationDemo());
  }
}

class AnimationDemo extends StatefulWidget {
  @override
  _AnimationDemoState createState() => _AnimationDemoState();
}

class _AnimationDemoState extends State<AnimationDemo> {
  bool _isAdded = false;

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Cart Animation')),
      body: Center(
        child: AnimatedContainer(
          duration: Duration(seconds: 1),
          width: _isAdded ? 200 : 150,
          height: 50,
          decoration: BoxDecoration(
            color: _isAdded ? Colors.green : Colors.blue,
            borderRadius: BorderRadius.circular(10),
          ),
          child: TextButton(
            onPressed: () {
              setState(() {
                _isAdded = !_isAdded;
              });
            },
            child: Text(
              _isAdded ? 'Added to Cart' : 'Add to Cart',
              style: TextStyle(color: Colors.white),
            ),
          ),
        ),
      ),
    );
  }
}
````

**Explanation:**

* `AnimatedContainer` changes its **size and color** smoothly when the button is pressed.
* `_isAdded` variable toggles the state, triggering the animation.
* Useful in e-commerce apps to show **adding items to the cart** with a visual effect.

## Key Points

* Use **implicit animations** for simple UI effects.
* Use **explicit animations** for complex sequences and precise control.
* Flutter provides **built-in animation widgets** for most common use-cases.

```
