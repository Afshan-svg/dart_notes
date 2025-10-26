# Dart Functions

Dart mein **function** ek block of code hota hai jo **specific task** perform karta hai.
Functions reuseable hote hain aur code ko clean aur organized banate hain.

---

## 1. Function Kya Hai?

Function ko aap call karte ho jab uska task perform karna ho.

**Syntax:**

```dart
returnType functionName(parameters) {
  // code
  return value; // optional
}
```

---

## 2. Simple Function Example

```dart
void greetCustomer(String name) {
  print("Welcome, $name!");
}

void main() {
  greetCustomer("Afshan");
}
```

**Output:**

```
Welcome, Afshan!
```

**Use Case:** App launch pe user ko greet karna.

---

## 3. Function with Return Value

```dart
double calculateTotalPrice(double price, int quantity) {
  return price * quantity;
}

void main() {
  double total = calculateTotalPrice(499.0, 3);
  print("Total Price: ₹$total");
}
```

**Output:**

```
Total Price: ₹1497.0
```

**Use Case:** Shopping cart total calculation.

---

## 4. Optional Parameters

Dart mein aap function ke parameters ko **optional** bana sakte ho.

### 4.1 Positional Optional

```dart
void showProduct(String name, [double? price]) {
  if (price != null) {
    print("Product: $name, Price: ₹$price");
  } else {
    print("Product: $name");
  }
}

void main() {
  showProduct("Shoes");
  showProduct("T-shirt", 799);
}
```

**Output:**

```
Product: Shoes
Product: T-shirt, Price: ₹799
```

---

### 4.2 Named Optional

```dart
void showProductDetails({required String name, double? price}) {
  print("Product: $name");
  if (price != null) print("Price: ₹$price");
}

void main() {
  showProductDetails(name: "Bag");
  showProductDetails(name: "Jacket", price: 1999);
}
```

**Output:**

```
Product: Bag
Product: Jacket
Price: ₹1999
```

**Use Case:** Flexible function calls in product pages.

---

## 5. Arrow Function (Short Function)

Agar function sirf **ek line ka kaam** karta hai, arrow `=>` use kar sakte ho.

```dart
double discountPrice(double price, double discount) => price - discount;

void main() {
  print("Discounted Price: ₹${discountPrice(2000, 500)}");
}
```

**Output:**

```
Discounted Price: ₹1500.0
```

---

## 6. Function as First-Class Object

Dart mein functions ko **variables** ke andar store ya **pass** kar sakte ho.

```dart
double calculate(double price, double Function(double) func) {
  return func(price);
}

void main() {
  var priceWithTax = calculate(1000, (p) => p * 1.18);
  print("Price with Tax: ₹$priceWithTax");
}
```

**Output:**

```
Price with Tax: ₹1180.0
```

**Use Case:** Apply different discounts or tax rules dynamically.

---

## 7. Anonymous Function / Lambda

```dart
var applyDiscount = (double price, double discount) {
  return price - discount;
};

void main() {
  print("Discounted: ₹${applyDiscount(1500, 200)}");
}
```

**Output:**

```
Discounted: ₹1300.0
```

---

## 8. Recursive Function

Ek function khud ko call kare recursive function kehlata hai.

```dart
int factorial(int n) {
  if (n == 0) return 1;
  return n * factorial(n - 1);
}

void main() {
  print("Factorial of 5: ${factorial(5)}");
}
```

**Output:**

```
Factorial of 5: 120
```

**Use Case:** Complex calculations in app backend (discount formulas, stock calculation, etc.)

---

## 9. Function Summary

| Function Type        | Syntax Example           | Use Case               |
| -------------------- | ------------------------ | ---------------------- |
| Normal Function      | `void greet() {}`        | Greet user             |
| Function with Return | `double calculate(){}`   | Cart total             |
| Optional Parameter   | `[double? price]`        | Product price optional |
| Named Parameter      | `{required String name}` | Flexible product info  |
| Arrow Function       | `=>`                     | Short calculations     |
| Anonymous Function   | `(params) {}`            | Dynamic code, lambda   |
| Recursive Function   | `factorial()`            | Calculations           |

---

## 10. Quick E-commerce Example

```dart
double calculateTotal(List<double> prices) {
  double total = 0;
  for (var price in prices) {
    total += price;
  }
  return total;
}

void main() {
  List<double> cart = [499, 799, 1200];
  print("Cart Total: ₹${calculateTotal(cart)}");
}
```

**Output:**

```
Cart Total: ₹2498.0
```

---
