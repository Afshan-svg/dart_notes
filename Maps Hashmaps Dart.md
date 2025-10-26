# Maps and HashMaps in Dart

In Dart, a **Map** is a collection of **key-value pairs**. It is similar to a dictionary in other languages. Maps allow you to store and retrieve data using **unique keys**.

---

## Creating a Map

```dart
void main() {
  // Map with String keys and dynamic values
  Map<String, dynamic> product = {
    'name': 'Shoes',
    'price': 50.0,
    'inStock': true,
  };

  print(product); // {name: Shoes, price: 50.0, inStock: true}
}
````

---

## Accessing Values

```dart
void main() {
  Map<String, dynamic> product = {
    'name': 'T-shirt',
    'price': 25.0,
    'inStock': true,
  };

  print(product['name']);   // T-shirt
  print(product['price']);  // 25.0
}
```

---

## Modifying Maps

```dart
void main() {
  Map<String, dynamic> product = {
    'name': 'Watch',
    'price': 100.0,
  };

  // Add a new key-value pair
  product['inStock'] = true;

  // Update an existing value
  product['price'] = 90.0;

  // Remove a key-value pair
  product.remove('inStock');

  print(product); // {name: Watch, price: 90.0}
}
```

---

## Iterating Over a Map

```dart
void main() {
  Map<String, dynamic> product = {
    'name': 'Bag',
    'price': 60.0,
    'inStock': false,
  };

  // Iterate through keys and values
  product.forEach((key, value) {
    print('$key: $value');
  });
}
```

---

## E-commerce Example: Shopping Cart

```dart
void main() {
  List<Map<String, dynamic>> cart = [
    {'name': 'Shoes', 'price': 50.0, 'quantity': 2},
    {'name': 'T-shirt', 'price': 25.0, 'quantity': 3},
  ];

  double total = 0;
  for (var item in cart) {
    total += item['price'] * item['quantity'];
  }

  print('Total Cart Price: \$${total}'); // Total Cart Price: $175.0
}
```

**Explanation:**

* Each product is represented as a **Map** with keys like `name`, `price`, and `quantity`.
* `List<Map>` allows multiple products in a cart.
* Maps are commonly used in **e-commerce apps** for storing product details, user data, and orders.
