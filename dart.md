## **1️⃣ Dart Basics**

### **Variables & Data Types**
Dart is strongly typed, but it supports type inference.

```dart
void main() {
  int age = 25;
  double height = 5.9;
  String name = 'Alice';
  bool isStudent = true;

  print('Name: $name, Age: $age, Height: $height, Student: $isStudent');
}
```

You can also use `var` or `dynamic`:
```dart
var city = 'New York';  // Automatically inferred as String
dynamic anything = 42;   // Can hold any type
```

---

### **2️⃣ Control Flow (if, for, while, switch)**

#### **if-else**
```dart
void main() {
  int score = 85;
  
  if (score >= 90) {
    print('Grade: A');
  } else if (score >= 80) {
    print('Grade: B');
  } else {
    print('Grade: C');
  }
}
```

#### **Loops**
```dart
// For loop
for (int i = 1; i <= 5; i++) {
  print('Count: $i');
}

// While loop
int j = 1;
while (j <= 3) {
  print('While loop: $j');
  j++;
}
```

#### **Switch Statement**
```dart
void main() {
  String grade = 'B';

  switch (grade) {
    case 'A':
      print('Excellent!');
      break;
    case 'B':
      print('Good Job!');
      break;
    default:
      print('Keep Trying!');
  }
}
```

---

### **3️⃣ Functions**
Functions help organize code.

```dart
void greet(String name) {
  print('Hello, $name!');
}

int add(int a, int b) {
  return a + b;
}

void main() {
  greet('Alice');
  int sum = add(5, 3);
  print('Sum: $sum');
}
```

**Arrow Function (Shorter Syntax)**
```dart
int multiply(int x, int y) => x * y;
```

---

### **4️⃣ Lists (Arrays)**
Dart lists are similar to arrays.

```dart
void main() {
  List<String> fruits = ['Apple', 'Banana', 'Cherry'];

  print(fruits[0]);  // Apple

  // Add an item
  fruits.add('Mango');

  // Loop through the list
  for (var fruit in fruits) {
    print(fruit);
  }
}
```

---

### **5️⃣ Maps (Key-Value Pairs)**
Similar to dictionaries in Python.

```dart
void main() {
  Map<String, String> user = {
    'name': 'Alice',
    'email': 'alice@example.com'
  };

  print(user['name']);  // Alice

  user['age'] = '25';  // Adding a new key

  user.forEach((key, value) {
    print('$key: $value');
  });
}
```

---

### **6️⃣ Classes & Objects (OOP in Dart)**
Dart is object-oriented.

```dart
class Car {
  String brand;
  int year;

  Car(this.brand, this.year);

  void display() {
    print('Car: $brand, Year: $year');
  }
}

void main() {
  Car myCar = Car('Tesla', 2023);
  myCar.display();
}
```

---

### **7️⃣ Null Safety (Important for Flutter)**
Dart has **null safety** to avoid null errors.

```dart
String? nullableText;  // Can be null
nullableText = 'Hello';
print(nullableText?.length);  // Safe access
```

Use `!` when you're sure a variable is not null:
```dart
String? name;
print(name!);  // Throws error if name is null
```
