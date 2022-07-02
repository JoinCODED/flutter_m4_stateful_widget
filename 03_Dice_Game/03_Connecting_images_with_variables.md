Since we have 6 images inside the assets/images folder, and the name of the images field is in sequence from 1 to 6, we need to create a variable that stores a number between 1 and 6, and connect this variable to the path inside the **Image.asset** widget. Every time the value of the variable changes, the image will change.

6. Replace `// TODO: #3 add random number1 variable` with the code below to create a variable that stores a number.

```dart
int randomNum1 = 1;
```

7. Connect the `randomNum1` variable to the **Image** widget.

```dart
Image.asset(
            'assets/images/dice_$randomNum1.png', // <- Here
            width: 120,
            height: 120,
          )
```

> Here, we used the $ sign to manipulate the path of the image to add the value of **randomNum1**. Since the initial value of **randomNum1** is 1, the flutter reads this path as **assets/images/dice_1.png**. If we change the initial value to 2, we will see the dice_2 inside the assets/images folder.

8. Replace ` // TODO: #4 add play function` with the code below to add the play function:

```dart
void play() {

}
```

9. Pass the **play** function to the `onPressed` named argument .

```dart
TextButton(
          style: ButtonStyle(
            backgroundColor: MaterialStateProperty.all(Colors.red),
          ),
          child: Text(
            'Play',
            style: TextStyle(
              fontSize: 20,
              color: Colors.white,
            ),
          ),
          onPressed: play, // <- Here
        )
```
