


9. Now, let’s add some logic for our dice game. Since we have 6 images inside the assets/images folder, and the name of the images field is in sequence from 1 to 6. We will need to create a variable that stores a number value between 1 and 6, then we will connect this variable with the path that is inside the **Image.asset** widget. So, while the value of the variable changes, the image will change.



​	To add this variable replace `// TODO: #3 add random number1 variable` with 

```dart
int randomNum1 = 1;
```



10. We already created the variable, now we will need to connect this variable with our **Image** widget.

```dart
Image.asset(
                'assets/images/dice_$randomNum1.png', // <- Here
                width: 120,
                height: 120,
              )
```

> Here, we changed the path, and we used the $ sign to add the value of **randomNum1** inside the path, so since the initial value for the **randomNum1** is 1, the flutter will read this path as **assets/images/dice_1.png**. When we change the initial value to 2, we will see the dice two on the assets/images folder. 



11. Adding play function, replace ` // TODO: #4 add play function` with

```dart
void play() {
    
}
```

We defined the play function, to use it we will connect it with our play button widget. To do that just replace the **onPressed** named argument with the name of our function which is **play**.

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



