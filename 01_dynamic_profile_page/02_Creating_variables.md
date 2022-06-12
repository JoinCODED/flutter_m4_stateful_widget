1. Open the **main.dart** file

2. Under the **HomeScreen** class, create a **double** variable named **age**.

```dart
class HomeScreen extends StatelessWidget {

// Here

```

> **Best Practice**: When you want to use variables inside a widget, always start by declaring them under the class, then call them once you need them.

For example, in our case, we will use the **age** variable inside the **Text** widget, so we will create the **age** variable under the **HomeScreen** class:

```dart
class HomeScreen extends StatelessWidget {
double age = 18;
.
.
.
```

We declared a double variable, and set it to an initial value of 18.

3. Below the **Hobbies**'s Text widget, create a new `Text` widget responsible for showing the age.

```dart
Container(
        alignment: Alignment.centerLeft,
        padding: EdgeInsets.only(left: 20),
        child: Text(
          'Hobbies: Acting and Fencing',
          style: TextStyle(
            color: Colors.white,
            fontSize: 24,
            fontWeight: FontWeight.bold,
          ),
        ),
      ),
// Here ↓
Container(
        alignment: Alignment.centerLeft,
        padding: EdgeInsets.only(left: 20, top: 15),
        child: Text(
          '',
          style: TextStyle(
            color: Colors.white,
            fontSize: 24,
            fontWeight: FontWeight.bold,
          ),
        ),
      ),
```

Here, we created a **Text** widget and wrapped it with a **Container** to add padding and alignment.
