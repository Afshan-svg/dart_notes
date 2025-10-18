Sure. Here’s your **`Dart Var Vs Dynamic.md`** file — explained in **Hinglish**, with **e-commerce examples**, no emojis, formatted for GitHub.

---

# Dart: var vs dynamic

Dart mein variables define karne ke liye `var` aur `dynamic` use hote hain. Dono ka behavior thoda alag hai.

---

## 1. var Kya Hai?

* `var` se variable create karte waqt **Dart compiler automatically type infer kar leta hai**.
* Ek baar type set ho gaya, to **type change nahi kar sakte**.

### Example

```dart
void main() {
  var productName = "Shoes"; // String type automatically set
  print(productName);

  // productName = 100; //  Error: type String cannot be assigned int
}
```

**Use Case:** Jab aapko **ek type ka value** store karna ho aur type change nahi hoga.

**E-commerce Example:**

```dart
var price = 499; // int
var name = "T-shirt"; // String
```

---

## 2. dynamic Kya Hai?

* `dynamic` variable ka type **runtime par change ho sakta hai**.
* Dart **type checking** runtime par karta hai.

### Example

```dart
void main() {
  dynamic data = "Shoes";
  print(data); // Shoes

  data = 100; // Type change allowed
  print(data); // 100
}
```

**Use Case:** Jab aapko **alagalag types ka value store karna ho** ya data type unknown ho.

**E-commerce Example:**

```dart
dynamic productInfo = "Bag";
productInfo = 2000; // price assign kar diya
```

---

## 3. Summary Table

| Feature              | var                      | dynamic                  |
| -------------------- | ------------------------ | ------------------------ |
| Type inference       | Compiler infer karta hai | Runtime decide karta hai |
| Type change allowed? | No                       | Yes                      |
| Type checking        | Compile time             | Runtime                  |
| Use case             | Fixed type variables     | Flexible type variables  |

---

## 4. Example Comparison

```dart
void main() {
  // var example
  var productName = "Shoes";
  // productName = 100; //  Error

  // dynamic example
  dynamic productInfo = "T-shirt";
  productInfo = 499; //  Allowed
  productInfo = true; //  Allowed
}
```

**Explanation:**

* `var` ka type **fix ho jata hai** jab assign karte hain.
* `dynamic` ka type **badal sakta hai**, jo runtime par check hota hai.

---

## 5. E-commerce Practical Example

```dart
void main() {
  var productName = "Sneakers"; // Fixed type
  dynamic productDetail = "Color: Red"; // Can change later

  print("Product: $productName");
  print("Detail: $productDetail");

  // Change dynamic value
  productDetail = {"price": 2999, "stock": true};
  print("Updated Detail: $productDetail");
}
```

**Output:**

```
Product: Sneakers
Detail: Color: Red
Updated Detail: {price: 2999, stock: true}
```

**Use Case:**

* `var` for product name, price, quantity
* `dynamic` for flexible data like product attributes (size, color, stock status, etc.)

---
