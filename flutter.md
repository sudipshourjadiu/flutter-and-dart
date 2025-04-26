## **Flutter UI Basics**  

### **1️⃣ Widgets - The Building Blocks of Flutter**
Everything in Flutter is a **widget**. There are two types:
- **StatelessWidget**: UI that doesn’t change.
- **StatefulWidget**: UI that changes dynamically.

### **2️⃣ Creating a Basic UI**
Here's a simple Flutter app with a text and button:

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,  // Removes debug banner
      home: HomeScreen(),
    );
  }
}

class HomeScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Flutter UI')),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Text('Hello, Flutter!', style: TextStyle(fontSize: 24)),
            SizedBox(height: 20),
            ElevatedButton(
              onPressed: () {
                print('Button Pressed');
              },
              child: Text('Click Me'),
            ),
          ],
        ),
      ),
    );
  }
}
```

### **3️⃣ Understanding the Code**
- `MaterialApp`: The main wrapper for a Flutter app.
- `Scaffold`: Provides a basic screen structure (app bar, body, etc.).
- `Column`: Arranges widgets vertically.
- `Text`: Displays text.
- `ElevatedButton`: A button with an action.

---

### **4️⃣ Adding Icons and Images**
Let's add an icon and an image:

```dart
Icon(Icons.star, size: 50, color: Colors.amber),
Image.network('https://flutter.dev/images/flutter-logo-sharing.png', width: 100),
```

---

### **5️⃣ Making UI Interactive with StatefulWidget**
A **StatefulWidget** allows dynamic updates. Let's create a counter app:

```dart
class CounterScreen extends StatefulWidget {
  @override
  _CounterScreenState createState() => _CounterScreenState();
}

class _CounterScreenState extends State<CounterScreen> {
  int count = 0;

  void increment() {
    setState(() {
      count++;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Counter App')),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Text('Counter: $count', style: TextStyle(fontSize: 24)),
            SizedBox(height: 20),
            ElevatedButton(
              onPressed: increment,
              child: Text('Increment'),
            ),
          ],
        ),
      ),
    );
  }
}
```
- `setState()`: Updates UI when the button is pressed.
