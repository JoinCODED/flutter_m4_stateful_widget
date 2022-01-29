7. To use the value of age inside **Text** widget, we will type the name of our variable inside the **Text** widget.

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

> **Note:** You’ll see red squiggles under the age variable inside the Text widget, and if we hover the mouse under the red squiggles, the VS code will tell us that “The argument type 'double' can't be assigned to the parameter type 'String”. So, this error occurs because we pass a double variable inside the Text widget, and the **Text** widget needs a String type.

8. To solve this issue we have two ways.

   1. First one, use the **toString()** method.

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

   2. Second one (Recommended), use the **$** dollar sign.

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

9. With the second approach, we can style our **Text widget** more easily, we will add Age tag before the age value.

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

<img src="https://lh5.googleusercontent.com/bEEHkVWf1QCgEXQIYhLp9vywfvyKMOv98_vfp9N0rBJrhiOE_GOE3i6c3I8ylr7WORiUqCwlUsNW3tXyT6UnF-ZsbPb6iULQHXkVK7O5rv-EJFWcfM4jm3anANPICu-j_wvb53uK" alt="img" width="300" />
