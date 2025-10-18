---

# Flutter Tutorial: Dart Class and Objects Kya Hai

Dart ek **object-oriented language** hai, jiska matlab hai ki Dart mein sab kuch ek **object** hota hai — variables, functions, widgets, sab.
Aur objects **class** se bante hain.

---

## 1. Class Kya Hai?

**Class** ek **blueprint (design)** hoti hai jisse objects banaye jaate hain.
Class ke andar hum define karte hain:

* Properties (variables)
* Methods (functions)

Simple shabdon mein:
Class ek **template** hai aur object uska **instance**.

---

### Example (E-commerce App)

```dart
class Product {
  // Properties
  String name;
  double price;
  bool inStock;

  // Constructor
  Product(this.name, this.price, this.inStock);

  // Method
  void showDetails() {
    print("Product: $name");
    print("Price: ₹$price");
    print("Available: ${inStock ? 'In Stock' : 'Out of Stock'}");
  }
}
```

---

## 2. Object Kya Hai?

**Object** ek class ka actual instance hota hai jisme real data store hota hai.
Jab aap `Product()` likhte ho, to ek naya object create hota hai.

### Example:

```dart
void main() {
  // Object creation
  Product p1 = Product("Sneakers", 2499.0, true);
  Product p2 = Product("Wrist Watch", 1999.0, false);

  // Accessing methods
  p1.showDetails();
  p2.showDetails();
}
```

**Output:**

```
Product: Sneakers
Price: ₹2499.0
Available: In Stock

Product: Wrist Watch
Price: ₹1999.0
Available: Out of Stock
```

---

## 3. Constructor Kya Hota Hai?

**Constructor** ek special function hota hai jo class ke object banate waqt call hota hai.
Ye object ke properties ko initialize karta hai.

### Example:

```dart
class Customer {
  String name;
  int age;

  // Constructor
  Customer(this.name, this.age);
}

void main() {
  Customer user = Customer("Afshan", 25);
  print("Customer: ${user.name}, Age: ${user.age}");
}
```

---

## 4. Named Constructor

Aap ek class ke andar **multiple constructors** bana sakte ho using **named constructors**.

### Example:

```dart
class Order {
  int orderId;
  String status;

  // Default constructor
  Order(this.orderId, this.status);

  // Named constructor
  Order.pending(this.orderId) : status = "Pending";
  Order.delivered(this.orderId) : status = "Delivered";
}

void main() {
  var order1 = Order.pending(101);
  var order2 = Order.delivered(102);

  print("Order ${order1.orderId} is ${order1.status}");
  print("Order ${order2.orderId} is ${order2.status}");
}
```

**Output:**

```
Order 101 is Pending
Order 102 is Delivered
```

---

## 5. Methods

Methods wo functions hote hain jo class ke andar defined hote hain.
Wo class ke properties ke saath kaam karte hain.

### Example:

```dart
class Cart {
  List<String> items = [];

  void addItem(String item) {
    items.add(item);
    print("$item added to cart");
  }

  void showCart() {
    print("Cart Items: $items");
  }
}

void main() {
  Cart cart = Cart();
  cart.addItem("Shoes");
  cart.addItem("T-shirt");
  cart.showCart();
}
```

**Output:**

```
Shoes added to cart
T-shirt added to cart
Cart Items: [Shoes, T-shirt]
```

---

## 6. this Keyword

`this` current object ko refer karta hai.
Aap jab constructor ya method ke andar property aur parameter ka naam same rakhte ho, to `this` use hota hai.

### Example:

```dart
class User {
  String name;
  String email;

  User(this.name, this.email);

  void showInfo() {
    print("Name: ${this.name}");
    print("Email: ${this.email}");
  }
}

void main() {
  User u = User("Sara", "sara@example.com");
  u.showInfo();
}
```

---

## 7. Inheritance (Ek Class Doosri Class Se)

Inheritance ka matlab hota hai ek class doosri class ke properties aur methods ko use kar sakti hai.

### Example:

```dart
class Product {
  String name;
  double price;

  Product(this.name, this.price);

  void display() {
    print("Product: $name, Price: ₹$price");
  }
}

// Child class
class Electronics extends Product {
  int warranty;

  Electronics(String name, double price, this.warranty) : super(name, price);

  void showWarranty() {
    print("Warranty: $warranty years");
  }
}

void main() {
  Electronics item = Electronics("Smartphone", 24999, 2);
  item.display();
  item.showWarranty();
}
```

**Output:**

```
Product: Smartphone, Price: ₹24999.0
Warranty: 2 years
```

---

## 8. Getters and Setters

Getter aur Setter variables ko safely access aur modify karne ke liye use hote hain.

### Example:

```dart
class Product {
  double _price = 0;

  // Setter
  set price(double value) {
    if (value > 0) {
      _price = value;
    } else {
      print("Invalid price");
    }
  }

  // Getter
  double get price => _price;
}

void main() {
  Product p = Product();
  p.price = 2000;
  print("Price: ₹${p.price}");
}
```

---

## 9. Summary

| Concept           | Description               | Example Use Case            |
| ----------------- | ------------------------- | --------------------------- |
| Class             | Blueprint or template     | Product, User, Order        |
| Object            | Instance of class         | Product item, Customer      |
| Constructor       | Initialize object data    | Product details             |
| Named Constructor | Alternative constructors  | Order status                |
| Method            | Function inside a class   | addItem(), showCart()       |
| this Keyword      | Refers to current object  | Used in constructors        |
| Inheritance       | Reuse parent class        | Electronics extends Product |
| Getters/Setters   | Controlled access to data | Validate product price      |

---

## 10. Quick Example Recap

```dart
class Product {
  String name;
  double price;

  Product(this.name, this.price);

  void display() {
    print("$name - ₹$price");
  }
}

void main() {
  Product item = Product("Headphones", 1999);
  item.display();
}
```

**Output:**

```
Headphones - ₹1999.0
```

---
