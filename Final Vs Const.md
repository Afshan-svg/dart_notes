---

# Dart: Final vs Const

Dart mein `final` aur `const` ka use immutable variables banane ke liye hota hai. Dono variables ki value change nahi hoti, lekin dono ka behavior alag hai.

---

## 1. Final Kya Hai?

* `final` variable ki value once assign ho jati hai, uske baad change nahi kar sakte.
* Value runtime par assign hoti hai.
* Agar runtime mein value calculate karni ho, to `final` use karo.

### Example

```dart
void main() {
  final price = 499;
  print(price);

  // price = 599; // Error: Cannot assign value to final variable
}
```

**E-commerce Example:**

```dart
final orderId = 101; // Order ID fix, change nahi hoga
final productName = "Shoes"; // Fixed product name
```

---

## 2. Const Kya Hai?

* `const` variable ki value compile-time par fix hoti hai.
* Compile-time ka matlab hai: jab app build ho raha ho, tab value fixed ho.
* Const variable ko hamesha constant value assign karni hoti hai.

### Example

```dart
void main() {
  const appName = "MyShop";
  print(appName);

  // appName = "YourShop"; // Error: Cannot assign value to const variable
}
```

**E-commerce Example:**

```dart
const taxRate = 0.18; // Tax rate fixed at compile-time
const currency = "₹";  // Currency symbol constant
```

---

## 3. Key Differences

| Feature                          | Final                   | Const                        |
| -------------------------------- | ----------------------- | ---------------------------- |
| Value assignment                 | Runtime                 | Compile-time                 |
| Can be changed?                  | No                      | No                           |
| Must know value at compile-time? | No                      | Yes                          |
| Example use case                 | Order ID, product price | Tax rate, app name, currency |

---

## 4. Final with Objects

```dart
class Product {
  final String name;
  final double price;

  Product(this.name, this.price);
}

void main() {
  final product = Product("Shoes", 499);
  print("${product.name} costs ₹${product.price}");
}
```

Note: Object properties ko change nahi kar sakte, lekin object ka reference mutable ho sakta hai agar properties non-final ho.

---

## 5. Const with Objects / Lists

```dart
void main() {
  const taxRates = [0.05, 0.12, 0.18];
  print(taxRates);

  // taxRates.add(0.28); // Error: Cannot modify const list
}
```

Use Case: Fixed constants like tax slabs, discount slabs, fixed categories.

---

## 6. Summary Example — E-commerce

```dart
void main() {
  final orderId = 101;       // assigned at runtime, unique per order
  final productName = "Bag"; // product name fixed once assigned
  const taxRate = 0.18;      // compile-time constant

  print("Order $orderId: $productName");
  print("Tax Rate: $taxRate");
}
```

Output:

```
Order 101: Bag
Tax Rate: 0.18
```

Takeaways:

* Use `final` jab value runtime par decide hoti ho.
* Use `const` jab value compile-time par fix ho.

---

