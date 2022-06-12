4. Place the **age** variable inside the **Text** widget.

```dart
Text(
  age,  // <- Here
    style: TextStyle(
      color: Colors.white,
      fontSize: 24,
      fontWeight: FontWeight.bold,
    ),
  ),
```

> **Note:** You will see red squiggles under the age variable inside the Text widget, and if you hover over it, the VS code will tell you that “The argument type 'double' can't be assigned to the parameter type 'String' ”. This error occurs because we passed a double variable to the Text widget, and the **Text** widget needs a String type.

To solve this issue, we have two options:

- First option: use the **toString()** method.

```dart
Text(
      age.toString(), // <- here
      style: TextStyle(
        color: Colors.white,
        fontSize: 24,
        fontWeight: FontWeight.bold,
      ),
    )
```

- Second option (Recommended): use the dollar sign **$**.

```dart
Text(
      '$age',  // <- Here
      style: TextStyle(
        color: Colors.white,
        fontSize: 24,
        fontWeight: FontWeight.bold,
      ),
    )
```

With the second approach, we can manipulate our **Text widget** more easily, and we can add an Age text before the age value.

```dart
Text(
      'Age: $age',
      style: TextStyle(
        color: Colors.white,
        fontSize: 24,
        fontWeight: FontWeight.bold,
      ),
    )
```

**Final result**:

![screenshot](https://lh5.googleusercontent.com/bEEHkVWf1QCgEXQIYhLp9vywfvyKMOv98_vfp9N0rBJrhiOE_GOE3i6c3I8ylr7WORiUqCwlUsNW3tXyT6UnF-ZsbPb6iULQHXkVK7O5rv-EJFWcfM4jm3anANPICu-j_wvb53uK)
