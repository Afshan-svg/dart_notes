---

#  All Types of Buttons in Flutter (with E-commerce Example)

Flutter mein buttons UI ka important part hote hain — jaise “Add to Cart”, “Buy Now”, “Login”, “Wishlist” etc.
Neeche sabse common button types explain kiye gaye hain with examples 👇

---

## 1. **ElevatedButton**

> Ye button thoda raised (3D effect) lagta hai — jaise “Buy Now” button.

###  Example (E-Commerce App):

```dart
ElevatedButton(
  onPressed: () {
    print("Buy Now clicked");
  },
  style: ElevatedButton.styleFrom(
    backgroundColor: Colors.green,
    padding: EdgeInsets.symmetric(horizontal: 40, vertical: 15),
    shape: RoundedRectangleBorder(
      borderRadius: BorderRadius.circular(10),
    ),
  ),
  child: Text(
    "Buy Now",
    style: TextStyle(fontSize: 18, color: Colors.white),
  ),
);
```

**Use Case:** Payment screen ya product details page pe.

---

## 2. **TextButton**

> Ye simple flat button hota hai — mostly links ya light actions ke liye.

###  Example:

```dart
TextButton(
  onPressed: () {
    print("View Details tapped");
  },
  child: Text("View Details"),
);
```

**Use Case:** Product card ke neeche “View Details” link.

---

## 3. **OutlinedButton**

> Ye transparent button hota hai with a border — classy look deta hai.

###  Example:

```dart
OutlinedButton(
  onPressed: () {
    print("Add to Wishlist clicked");
  },
  style: OutlinedButton.styleFrom(
    side: BorderSide(color: Colors.orange, width: 2),
    shape: RoundedRectangleBorder(
      borderRadius: BorderRadius.circular(10),
    ),
  ),
  child: Text("Add to Wishlist"),
);
```

**Use Case:** Product ke saath “Add to Wishlist” option.

---

## 4. **IconButton**

> Ye button sirf ek icon hota hai — jaise cart icon, heart icon, search icon.

###  Example:

```dart
IconButton(
  icon: Icon(Icons.shopping_cart),
  color: Colors.blue,
  iconSize: 30,
  onPressed: () {
    print("Cart icon tapped");
  },
);
```

**Use Case:** App bar mein cart icon, wishlist heart icon, etc.

---

## 5. **FloatingActionButton (FAB)**

> Ye circular button hota hai, mostly screen ke bottom right mein floating karta hai.

###  Example:

```dart
FloatingActionButton(
  onPressed: () {
    print("Add new product clicked");
  },
  backgroundColor: Colors.pink,
  child: Icon(Icons.add),
);
```

**Use Case:** Admin dashboard ya seller app mein “Add Product” ka shortcut.

---

## 6. **DropdownButton**

> Ye button ek dropdown open karta hai with multiple choices.

###  Example:

```dart
String selectedSize = 'M';

DropdownButton<String>(
  value: selectedSize,
  items: ['S', 'M', 'L', 'XL'].map((String size) {
    return DropdownMenuItem<String>(
      value: size,
      child: Text(size),
    );
  }).toList(),
  onChanged: (newValue) {
    print("Selected size: $newValue");
  },
);
```

**Use Case:** Product page pe “Select Size”.

---

## 7. **PopupMenuButton**

> Ye button pe click karte hi ek chhota popup menu aata hai.

###  Example:

```dart
PopupMenuButton<String>(
  onSelected: (value) {
    print("Selected: $value");
  },
  itemBuilder: (BuildContext context) => [
    PopupMenuItem(value: 'Edit', child: Text('Edit Product')),
    PopupMenuItem(value: 'Delete', child: Text('Delete Product')),
  ],
);
```

**Use Case:** Seller ke product list mein “...” options button.

---

## 8. **GestureDetector / InkWell**

> Ye widget kisi bhi area ko tappable bana deta hai — custom button banane ke liye.

###  Example:

```dart
InkWell(
  onTap: () {
    print("Product image tapped");
  },
  child: Container(
    padding: EdgeInsets.all(10),
    decoration: BoxDecoration(
      color: Colors.grey[200],
      borderRadius: BorderRadius.circular(8),
    ),
    child: Row(
      mainAxisAlignment: MainAxisAlignment.center,
      children: [
        Icon(Icons.shopping_bag, color: Colors.black),
        SizedBox(width: 8),
        Text("Add to Cart"),
      ],
    ),
  ),
);
```

**Use Case:** Custom-designed “Add to Cart” button with animation or gradient.

---

## 9. **BackButton**

> Ye predefined button hota hai for navigation back action.

###  Example:

```dart
AppBar(
  leading: BackButton(
    color: Colors.black,
  ),
  title: Text("Product Details"),
);
```

**Use Case:** Product details page se back jane ke liye.

---

## 10. **CloseButton**

> Ye ‘X’ shaped button hota hai — dialog ya modal close karne ke liye.

###  Example:

```dart
AlertDialog(
  title: Row(
    mainAxisAlignment: MainAxisAlignment.spaceBetween,
    children: [
      Text("Cart"),
      CloseButton(onPressed: () => Navigator.pop(context)),
    ],
  ),
  content: Text("Your items are here!"),
);
```

**Use Case:** Cart dialog ya popup close karne ke liye.

---

##  Summary Table

| Button Type          | Look/Feel       | Common Use Case  |
| -------------------- | --------------- | ---------------- |
| ElevatedButton       | Raised / 3D     | Buy Now / Login  |
| TextButton           | Flat / Simple   | View Details     |
| OutlinedButton       | Bordered        | Add to Wishlist  |
| IconButton           | Icon Only       | Cart / Search    |
| FloatingActionButton | Floating Circle | Add Product      |
| DropdownButton       | List Options    | Select Size      |
| PopupMenuButton      | Popup Menu      | Edit/Delete menu |
| GestureDetector      | Custom Area     | Custom Button    |
| BackButton           | Navigation Back | Go Back          |
| CloseButton          | Close Icon      | Close Dialog     |

---
