---

# Dart Data Types and Variables

Flutter apps are written in **Dart**, and variables are used to **store data** like text, numbers, lists, etc.
Data type batata hai ki variable kis type ka data store karega.

---

## 1. What is a Variable?

Variable ek **memory space** hota hai jahan hum data store karte hain.
Dart mein variable declare karne ke liye `var`, `final`, `const`, ya specific data type (like `int`, `String`, etc.) use karte hain.

### Example (E-commerce App):

```dart
var productName = "Shoes";
int productPrice = 1500;
bool isAvailable = true;
```

---

## 2. Data Types in Dart

### 2.1 **int** — Integer Numbers

Whole numbers store karta hai (without decimals).

```dart
int quantity = 5;
int price = 1200;
int total = quantity * price; // 6000
```

**Use Case:** Product quantity, stock count, etc.

---

### 2.2 **double** — Decimal Numbers

Decimal (floating point) values ke liye use hota hai.

```dart
double rating = 4.5;
double discount = 10.25;
```

**Use Case:** Product rating, discounts, etc.

---

### 2.3 **String** — Text Data

Text ya characters store karne ke liye.

```dart
String productName = "Wireless Earbuds";
String category = "Electronics";
```

**Use Case:** Product name, user name, email, etc.

---

### 2.4 **bool** — Boolean

Sirf two values: `true` or `false`.

```dart
bool isAvailable = true;
bool isInCart = false;
```

**Use Case:** Availability check, toggle features, etc.

---

### 2.5 **List** — Collection of Multiple Values

Multiple items ek variable mein store karne ke liye.

```dart
List<String> categories = ["Shoes", "Clothes", "Accessories"];
List<int> productIds = [101, 102, 103];
```

**Use Case:** Product lists, categories, etc.

---

### 2.6 **Map** — Key-Value Pairs

Data ko key aur value ke form mein store karta hai.

```dart
Map<String, dynamic> product = {
  "name": "Sneakers",
  "price": 2999,
  "inStock": true
};
```

**Use Case:** Product details, user info, etc.

---

### 2.7 **var** — Type Inferred Variables

`var` use karte hain jab type Dart khud detect kar le.

```dart
var userName = "Afshan"; // Dart automatically knows it's a String
var price = 500;         // Dart knows it's an int
```

**Note:** Once assigned, `var` type change nahi hoti.
Example:

```dart
var data = "Shoes";
data = 100;
```

---

### 2.8 **dynamic** — Changeable Type Variable

`dynamic` use karne par variable ka type runtime par change ho sakta hai.

```dart
dynamic value = "Shoes";
value = 100;
```

**Use Case:** Jab variable ka data type uncertain ho.

---

### 2.9 **final** — Value Assigned Once

Ek baar assign hone ke baad value change nahi kar sakte.

```dart
final orderId = 12345;
```

**Use Case:** Order ID, constant session token, etc.

---

### 2.10 **const** — Compile-Time Constant

`const` ka value compile-time par fix hota hai (final se bhi strict).

```dart
const appName = "MyShop";
```

**Use Case:** App-wide constants like names, API keys, etc.

---

## 3. Variable Declaration Summary

| Keyword | Can Change?      | Type Fixed? | Evaluated At | Example Use      |
| ------- | ---------------- | ----------- | ------------ | ---------------- |
| var     |  (after assign) |            | Runtime      | Common variables |
| dynamic |                 |            | Runtime      | Flexible types   |
| final   |                 |            | Runtime      | Order IDs        |
| const   |                 |            | Compile time | App constants    |

---

## 4. Example — Combine All in E-commerce Context

```dart
void main() {
  // Basic product details
  String productName = "Smart Watch";
  int price = 2499;
  double rating = 4.7;
  bool inStock = true;

  // Category list
  List<String> categories = ["Electronics", "Wearables", "Gadgets"];

  // Product info map
  Map<String, dynamic> product = {
    "name": productName,
    "price": price,
    "rating": rating,
    "available": inStock
  };

  // Display info
  print("Product: ${product['name']}");
  print("Price: ₹${product['price']}");
  print("Rating: ${product['rating']}");
  print("Available: ${product['available'] ? 'In Stock' : 'Out of Stock'}");
}
```

**Output:**

```
Product: Smart Watch
Price: ₹2499
Rating: 4.7
Available: In Stock
```

---

## 5. Tips for Beginners

* Use **var** for normal variables when type is clear.
* Use **final** when value won’t change.
* Use **const** for permanent constants.
* Avoid **dynamic** unless necessary.
* Always name variables meaningfully (`productName`, not `p`).

---
