# Get Current Date in Dart/Flutter

In Dart, you can get the **current date and time** using the `DateTime` class. This is useful in apps for timestamps, order dates, or logs.

## Getting Current Date and Time

```dart
void main() {
  DateTime now = DateTime.now();
  print(now); // Example: 2025-10-26 20:45:30.123
}
````

* `DateTime.now()` returns the **current date and time** in local time.

---

## Getting Only Date or Time

```dart
void main() {
  DateTime now = DateTime.now();

  String currentDate = "${now.year}-${now.month}-${now.day}";
  String currentTime = "${now.hour}:${now.minute}:${now.second}";

  print("Date: $currentDate"); // Date: 2025-10-26
  print("Time: $currentTime"); // Time: 20:45:30
}
```

---

## Formatting Date Using `intl` Package

To display a date in a **readable format**, you can use the `intl` package.

```dart
import 'package:intl/intl.dart';

void main() {
  DateTime now = DateTime.now();
  String formattedDate = DateFormat('dd-MM-yyyy').format(now);
  String formattedTime = DateFormat('hh:mm a').format(now);

  print("Date: $formattedDate"); // Date: 26-10-2025
  print("Time: $formattedTime"); // Time: 08:45 PM
}
```

* `DateFormat('dd-MM-yyyy')` formats the date.
* `DateFormat('hh:mm a')` formats the time in 12-hour format with AM/PM.

---

## E-commerce Example

```dart
void main() {
  DateTime now = DateTime.now();
  String orderDate = DateFormat('dd/MM/yyyy').format(now);

  print("Order placed on: $orderDate"); // Order placed on: 26/10/2025
}
```

* Useful to display **order date, delivery date, or transaction time** in e-commerce apps.
