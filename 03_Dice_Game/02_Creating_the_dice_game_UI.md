5. The first thing that we will add on the screen is the dice image, to add it `replace // TODO: #1 add dice image` with

```dart
		//1
         Container(
              //1
              padding: EdgeInsets.all(10),

              //2
              child: Image.asset(
                'assets/images/dice_1.png',
                //3
                width: 120,
                height: 120,
              ),
            ),
```

1. We wrap the dice image widget with Container to add some padding.
2. Here we used Image.asset to get images from the assets images folder by adding an image path.
3. Specifying width and height for image widget.

![screenshot](https://lh6.googleusercontent.com/i7-uanlfQ4yK8jU7GXZziw1EgKWFENkud8NvcVzq0slalbszj6P2uwarUQBRGZPMoclHbSxdfae775IJY2IxJX_PrclMXQUf3g0cZ5W3L4JYAqNt7B7ep8bomGuCjkbUGqD3cBv9)

6. Adding play button, replace ` // TODO: #2 add play button` with

```dart
           // 1
            Container(
              height: 45,
              width: 100,

              // 2
              child: ElevatedButton(
                //3
                style: ButtonStyle(
                  backgroundColor: MaterialStateProperty.all(Colors.red),
                ),
                // 4
                child: Text(
                  'Play',
                  style: TextStyle(
                    fontSize: 20,
                    color: Colors.white,
                  ),
                ),
                // 5
                onPressed: () {},
              ),
            )
```

1. Wrapping the play button widget with **Container** to specify the height and width for the play button widget.
2. Adding the button by using the **ElevatedButton** widget.
3. Change the background color for the play button.
4. Adding play text inside the button by using the **Text** widget.
5. Here, we used an anonymous function to add an event when the user clicks this play button.

![screenshot](https://lh3.googleusercontent.com/Oe5Lormy00RPcfFBnljueIx49qCoJMmg4u8LxFi7iIiOlHe_qNEs8U0biT74qV1_FyzoiztkUqXMNLxerY8AyuzTcMuTwdaWznRrAa-KKfo5aV5ZBazsjaJVyCUQYklNHYhxFGVn)

7. Now let’s change the layout for our widgets, we want to keep the dice image widget and the play button widget on the center of the screen. We will use the **mainAxisAlignment** named argument inside the **Column** widget, and we will use the **MainAxisAlignment.center** option to keep our widget on the center.

![screenshot](https://lh3.googleusercontent.com/U7XaxuqkFFpb6HNPRrafV93KMGzNI_hi1TslgNfBOJAAy_xTUgHGsu5WmBfgvLshokOxiUOJw1btkV7Kt3-CEzq_YqYtaUzxLNgGCbH_G7xvJaYkZdxLJREuVKsys1EDybhixIL_)

8. Also, we want to add some space between the dice image widget and the play button. We will add the space by using the **Container** widget. Add these codes inside the **Column** widget children between the Dice image widget and the play button.

   ```dart
   Container(height: 100),
   ```
