### S2: Flutter & Dart Basics  

---

## 🚀 Importance of Files in a Flutter Project  
- **`lib`**: Main folder where we write the app’s code.  
- **`android`, `ios`, `web`, etc.**: Platform-specific files that Flutter uses to make your app run everywhere.  
- **`build`**: Temporary and output files for running the app.  
- **`test`**: Code for testing the app.  
- **Dot folders/files (`.xyz`)**: Extra configurations.  
- **`pubspec.yaml`**: Manages third-party packages for your app.  

---

## 🔄 How Dart Code Runs  
1. Dart reads and analyzes your code from top to bottom (parsing).  
2. Flutter compiles it into native machine code for iOS or Android.  

---

## ⚡ How Flutter Apps Become Active  
- The `main()` function is **automatically executed** by Dart.  
- Inside `main()`, the `runApp()` function tells Flutter what to display.  
- `runApp()` takes a **widget tree**, which is a combination of Flutter widgets that build the UI.  

---

## 📌 Positional & Named Arguments  

### 💡 What Are Arguments?  
Arguments pass values into a function for processing (e.g., display, calculation, etc.).  

### 🌀 Two Types of Arguments in Dart  
1. **Positional Arguments**: The position of the argument matters.  
   ```dart
   void add(a, b) {
     print(a + b);
   }
   add(5, 10); // 5 -> a, 10 -> b
   ```
2. **Named Arguments**: The name of the argument matters.  
   ```dart
   void add({a, b}) {
     print(a + b);
   }
   add(b: 5, a: 10); // 5 -> b, 10 -> a
   ```

---

### 🔑 Key Differences  
- **Positional Arguments**: Required by default; must be provided in order.  
- **Named Arguments**: Optional by default; can be provided in any order.  

---

### ✨ Making Arguments Optional or Required  
1. **Optional Positional Arguments**: Use square brackets `[]`.  
   ```dart
   void add(a, [b]) {
     print(a + (b ?? 0)); // Defaults to 0 if b is null.
   }
   add(10); // Valid
   add(10, 5); // Valid
   ```

2. **Default Values for Optional Arguments**: Assign a value directly.  
   ```dart
   void add(a, [b = 5]) {
     print(a + b);
   }
   add(10); // Output: 15
   ```

3. **Default Values for Named Arguments**: Same approach.  
   ```dart
   void add({a, b = 5}) {
      print(a + b);
   }
   add(b: 10); // a = null, Output: Error unless handled
   ```

4. **Required Named Arguments**: Use `required`.  
   ```dart
   void add({required a, required b}) {
     print(a + b);
   }
   add(a: 10, b: 5); // Valid
   add(a: 10); // Error
   add(b:12);
   add(b:6,a:12);

   ```

--- 

### 🚀 **`const` in Dart**  
- **Purpose**: Helps optimize runtime performance.  
- **How?**: By creating **compile-time constants**—values that are fixed and determined at compile time, not runtime.  
- **Key Benefit**: Reduces memory usage by reusing the same instance of immutable data.  

### Example:  
```dart
const pi = 3.14; // Value is fixed at compile time.
const area = pi * 5 * 5; // Also a constant because it depends only on other constants.  
```

💡 Use `const` for values that never change and can be evaluated at compile time.  

---

### Value Types
- **int**: Integer numbers (e.g., 29, -15)
- **double**: Fractional numbers (e.g., 3.91, -12.81)
- **num**: Integer or fractional numbers (e.g., 15, 15.01, -2.91)
- **boolean**: Boolean values (`true`, `false`)
- **string**: Text (e.g., `'Text'`)
- **Object**: Any kind of object

### Dart Overview
- Dart is **object-oriented**.
- **Widgets = Objects = Data Structures**
- **Classes**: Blueprints for creating objects.

### Custom Widgets
Custom widgets can be created in Dart/Flutter.

---

### Variables in Dart

1. **var**:  
   - Holds a variable, which can be reassigned different values.
   - Example: `var x = 5; x = "Text";`

2. **dynamic**:  
   - Can hold any type of data but should be avoided to reduce bugs.

3. **final**:  
   - Holds a fixed value and cannot be reassigned.
   - Example: `final x = 5;`

4. **const**:  
   - Compile-time constant, cannot be reassigned.

---

### Flutter Layout Widgets

#### Column()
- **Main Axis**: Vertical
- **Cross Axis**: Horizontal
- **Default behavior**: Takes up entire height, but width only as required by its children.

#### Row()
- **Main Axis**: Horizontal
- **Cross Axis**: Vertical
- **Default behavior**: Takes up entire width, but height only as required by its children.

---

### Button Types in Flutter

1. **Elevated Button**:  
   - Background color with shadow.
   - Example: `ElevatedButton(onPressed: () {}, child: Text("Press me"))`

2. **Outlined Button**:  
   - No background color but has a border.
   - Example: `OutlinedButton(onPressed: () {}, child: Text("Press me"))`

3. **Text Button**:  
   - Only pressable text, no background.
   - Example: `TextButton(onPressed: () {}, child: Text("Press me"))`

---

### Stateful vs Stateless Widgets

- **Stateful Widgets**:  
  - Can change their state during runtime.
  - Example: `StatefulWidget` with dynamic behavior.
  
- **Stateless Widgets**:  
  - Cannot change their state after creation.
  - Example: `StatelessWidget` for static UI.