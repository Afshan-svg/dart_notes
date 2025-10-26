# Rows and Columns in Flutter

**Rows** and **Columns** are basic layout widgets in Flutter used to arrange child widgets **horizontally or vertically**.

---

## Row Widget

- Arranges children **horizontally**.
- Main properties:
  - `mainAxisAlignment` – Aligns children horizontally.
  - `crossAxisAlignment` – Aligns children vertically.

```dart
Row(
  mainAxisAlignment: MainAxisAlignment.spaceAround,
  children: [
    Icon(Icons.shopping_cart, size: 40),
    Text('Cart'),
    ElevatedButton(onPressed: () {}, child: Text('Checkout')),
  ],
)
````

---

## Column Widget

* Arranges children **vertically**.
* Main properties:

  * `mainAxisAlignment` – Aligns children vertically.
  * `crossAxisAlignment` – Aligns children horizontally.

```dart
Column(
  mainAxisAlignment: MainAxisAlignment.center,
  children: [
    Text('Product Name', style: TextStyle(fontSize: 20, fontWeight: FontWeight.bold)),
    SizedBox(height: 10),
    Text('Price: \$50', style: TextStyle(fontSize: 18, color: Colors.green)),
    ElevatedButton(onPressed: () {}, child: Text('Add to Cart')),
  ],
)
```

---

## E-commerce Example: Product Card

```dart
Card(
  child: Padding(
    padding: EdgeInsets.all(10),
    child: Row(
      children: [
        Image.network('https://example.com/shoes.png', width: 80),
        SizedBox(width: 10),
        Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text('Running Shoes', style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold)),
            Text('\$50', style: TextStyle(fontSize: 16, color: Colors.green)),
            ElevatedButton(onPressed: () {}, child: Text('Add to Cart')),
          ],
        ),
      ],
    ),
  ),
)
```

**Explanation:**

* `Row` arranges **image and product details** side by side.
* `Column` arranges **product name, price, and button** vertically.
* Rows and Columns are essential for **building responsive e-commerce layouts**.
