# Creating Variables



4. Under **HomeScreen** class we will create the **age** variable, and its type will be a **double**

```dart
class HomeScreen extends StatelessWidget {

// Here

```

> **Best Practice**: always when you want to use variables inside a widget, first declare the variables under the class, for example, in our case we will use the **age** variable inside the **Text** widget, so first we will create the **age** variable under the **HomeScreen** class

Under the **HomeScreen** class type

```dart
double age = 18;
```

Here, we declared a double variable, with 18 initial value



5. Under the **Hobbies** widgets, we will create a new widget that is responsible for showing the age.

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
// Here

```



6. Type this code under the **Container** widget.

```dart
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

Here, we created a **Text** widget, and we wrapped it with a **Container** widget to add padding and alignment for the Age Text widget. 







