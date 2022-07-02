To generate a random number from 1 to 6, use the **Random** class. To do that, you need to import the math library.

10. Replace `// TODO: #5 import dart math` with the code below to add the math library to the project.

```dart
import 'dart:math';
```

After we import the math dart file, we will use the **nextInt()** method, which helps us generate a random number. This method takes one argument which is the maximum number. We will store the generated random number inside the **randomNum1** variable.

### Tapping to generate random values (printing)

11. Replace the code below to generate a random number within a range from 1 to 6.

```dart
void play() {
    randomNum1 = Random().nextInt(6) + 1;

    print(randomNum1);
  }
```

> **Note:** We increased the random number by one to avoid getting the zero value.

12. Open the **DEBUG CONSOLE**.

![screenshot](https://lh3.googleusercontent.com/yhicjcSkzIZR19XoRMkqwjWAQePwfgoqVqsKlsH9OcRPQif91llUuuzWIQD9OQtAC2OeF2emj-EFuh8ygs7vaH17-mw_i2A7ZOoRTdEQLfJu5p76c4o3uJX4pWS92fQBhlDEUAmA)

13. Try clicking the play button many times, you will see random numbers in the **DEBUG CONSOLE** because we used the print method inside the play function to print the value of the **randomNum1** variable.

![screenshot](https://lh3.googleusercontent.com/rYKzypvMB4zvdl6HI-Z9qF5ohmzViE33E7PKMdMDXWLZUNCQc7NDxZQSoEDRPdcsqNN0drwxo0wZ4F7zURG8WyvphcZLSwDwwh4KCSE0Zqc-Y8BaIti7aCqUNbJMJHGbLlLh6bEA)

Even though we created a variable number that was linked to the **Image** widget, generated a random number, we did not see any changes on the home screen app. That is because we did not change the state of our dice image widget.
