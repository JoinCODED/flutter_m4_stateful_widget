# Random values



12. To generate a random number from 1 to 6, we will use a **Random** object, and to use this object first we will need to image `import 'dart:math';` because this object is inside the **math dart** file. To import it just replace `// TODO: #5 import dart math` with 

```dart
import 'dart:math';
```



13. After we import the math dart file, we will use the **nextInt()** method inside the Random object which will help us to generate a random number, and this method takes one argument which is the maximum number. Also, after we generated the random number we will store it inside the **randomNum1** variable. 



### Tapping to generate random values (printing)

To do that just replace the play function with this function.

```dart
void play() {
    randomNum1 = Random().nextInt(6) + 1;

    print(randomNum1);
  }
```

> Here, we store the random number inside the randomNum1 variable, and to generate this random number we use the **Random** object, and its **nextInt** method. Also, we added 6 inside the maximum argument because we don’t need to generate a random number bigger than 6 since the dice number is between one and six. In addition, we increase the random number by one because we don’t need the zero value.



14. Open the **DEBUG CONSOLE** 

<img src="https://lh3.googleusercontent.com/yhicjcSkzIZR19XoRMkqwjWAQePwfgoqVqsKlsH9OcRPQif91llUuuzWIQD9OQtAC2OeF2emj-EFuh8ygs7vaH17-mw_i2A7ZOoRTdEQLfJu5p76c4o3uJX4pWS92fQBhlDEUAmA" alt="img" width="650" />


15. Now try clicking the play button more than once. You will see random numbers on the **DEBUG CONSOLE** because we used the print function inside the play to print the value of the **randomNum1** variable.

<img src="https://lh3.googleusercontent.com/rYKzypvMB4zvdl6HI-Z9qF5ohmzViE33E7PKMdMDXWLZUNCQc7NDxZQSoEDRPdcsqNN0drwxo0wZ4F7zURG8WyvphcZLSwDwwh4KCSE0Zqc-Y8BaIti7aCqUNbJMJHGbLlLh6bEA" alt="img" width="650" />






16. Even though we created a variable number that linked with the **Image** widget, and we generated a random number, we did not see any changes on the home screen app. That is because we didn’t change the state of our dice image widget. What is the state?!!!!





































