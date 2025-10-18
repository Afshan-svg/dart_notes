---

# Dart List

Dart mein **List** ek **ordered collection** hota hai jisme multiple values ek hi variable mein store ki ja sakti hain.
List ke andar **duplicate items** ho sakte hain aur index 0 se start hota hai.

---

## 1. List Kya Hai?

**Syntax:**

```dart
List<dataType> listName = [value1, value2, value3];
```

### Example (E-commerce App)

```dart
List<String> categories = ["Shoes", "Clothes", "Accessories"];
List<int> productIds = [101, 102, 103];
```

---

## 2. Accessing List Items

List ke items ko index se access karte hain.

```dart
void main() {
  List<String> categories = ["Shoes", "Clothes", "Accessories"];
  print(categories[0]); // Shoes
  print(categories[2]); // Accessories
}
```

**Use Case:** Product category display karna.

---

## 3. Modifying List

```dart
void main() {
  List<String> products = ["Shoes", "Bag", "T-shirt"];
  
  // Update an item
  products[1] = "Backpack";
  
  print(products); // [Shoes, Backpack, T-shirt]
}
```

**Use Case:** Product rename ya update karna.

---

## 4. Adding Items to List

```dart
void main() {
  List<String> cart = ["Shoes"];
  
  // Add single item
  cart.add("T-shirt");
  
  // Add multiple items
  cart.addAll(["Bag", "Hat"]);
  
  print(cart); // [Shoes, T-shirt, Bag, Hat]
}
```

**Use Case:** Add to cart functionality.

---

## 5. Removing Items from List

```dart
void main() {
  List<String> cart = ["Shoes", "T-shirt", "Bag"];
  
  // Remove by value
  cart.remove("T-shirt");
  
  // Remove by index
  cart.removeAt(1);
  
  print(cart); // [Shoes]
}
```

**Use Case:** Remove items from cart.

---

## 6. List Properties

* `length` — List ka size
* `isEmpty` — Check if list empty hai
* `isNotEmpty` — Check if list has items

```dart
void main() {
  List<String> products = ["Shoes", "Bag"];
  
  print(products.length);     // 2
  print(products.isEmpty);    // false
  print(products.isNotEmpty); // true
}
```

---

## 7. Iterating Over List

### 7.1 For Loop

```dart
void main() {
  List<String> products = ["Shoes", "Bag", "T-shirt"];
  
  for (int i = 0; i < products.length; i++) {
    print(products[i]);
  }
}
```

### 7.2 For-in Loop

```dart
void main() {
  List<String> products = ["Shoes", "Bag", "T-shirt"];
  
  for (var product in products) {
    print(product);
  }
}
```

### 7.3 forEach Method

```dart
void main() {
  List<String> products = ["Shoes", "Bag", "T-shirt"];
  
  products.forEach((product) {
    print(product);
  });
}
```

**Use Case:** Product listing on UI.

---

## 8. List Methods

| Method      | Description                    |
| ----------- | ------------------------------ |
| add()       | Add single item                |
| addAll()    | Add multiple items             |
| remove()    | Remove by value                |
| removeAt()  | Remove by index                |
| insert()    | Insert item at specific index  |
| insertAll() | Insert multiple items at index |
| clear()     | Remove all items               |
| indexOf()   | Find index of item             |
| contains()  | Check if item exists           |
| sort()      | Sort list                      |
| shuffle()   | Randomize list                 |
| join()      | Convert list to string         |

---

## 9. Example — E-commerce Cart

```dart
void main() {
  List<String> cart = [];

  // Add items
  cart.add("Shoes");
  cart.addAll(["Bag", "T-shirt"]);

  // Show cart items
  print("Cart Items: $cart");

  // Remove item
  cart.remove("Bag");
  print("After Removal: $cart");

  // Check if cart has T-shirt
  if (cart.contains("T-shirt")) {
    print("T-shirt is in cart");
  }

  // Total items
  print("Total Items: ${cart.length}");
}
```

**Output:**

```
Cart Items: [Shoes, Bag, T-shirt]
After Removal: [Shoes, T-shirt]
T-shirt is in cart
Total Items: 2
```

---

## 10. Growable vs Fixed-Length List

* **Growable List (default)** — Size badhaya ya ghata sakte ho

```dart
List<String> cart = ["Shoes", "Bag"]; // growable
cart.add("T-shirt");
```

* **Fixed-Length List** — Size fix, values change kar sakte ho

```dart
List<String> products = List.filled(3, ""); // ["", "", ""]
products[0] = "Shoes";
products[1] = "Bag";
products[2] = "T-shirt";
```

---
