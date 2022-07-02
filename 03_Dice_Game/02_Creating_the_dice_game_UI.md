2.  Replace `// TODO: #1 add dice image` with the code below to display the dice image on the screen.

```dart
		//a
    Container(
        //b
        padding: EdgeInsets.all(10),

        //c
        child: Image.asset(
          'assets/images/dice_1.png',
          //d
          width: 120,
          height: 120,
        ),
      ),
```

a. We wrapped the dice image widget with `Container` to add some padding.
b. We used `Image.asset` to display the images on the screen.
c. We added width and height to the image widget.

![screenshot](https://lh6.googleusercontent.com/i7-uanlfQ4yK8jU7GXZziw1EgKWFENkud8NvcVzq0slalbszj6P2uwarUQBRGZPMoclHbSxdfae775IJY2IxJX_PrclMXQUf3g0cZ5W3L4JYAqNt7B7ep8bomGuCjkbUGqD3cBv9)

3. Replace ` // TODO: #2 add play button` with the code below to add the play button.

```dart
      // a
      Container(
        height: 45,
        width: 100,

        // b
        child: ElevatedButton(
          //c
          style: ButtonStyle(
            backgroundColor: MaterialStateProperty.all(Colors.red),
          ),
          // d
          child: Text(
            'Play',
            style: TextStyle(
              fontSize: 20,
              color: Colors.white,
            ),
          ),
          // c
          onPressed: () {},
        ),
      )
```

a. We wrapped the play button widget with a **Container** to specify the height and width of the button.
b. We added the button using the **ElevatedButton** widget.
c. We changed the background color of the play button.
d. We added play text inside the button using the **Text** widget.
e. We used an anonymous function to add an event when the user clicks the play button.

![screenshot](https://lh3.googleusercontent.com/Oe5Lormy00RPcfFBnljueIx49qCoJMmg4u8LxFi7iIiOlHe_qNEs8U0biT74qV1_FyzoiztkUqXMNLxerY8AyuzTcMuTwdaWznRrAa-KKfo5aV5ZBazsjaJVyCUQYklNHYhxFGVn)

4. Use the **mainAxisAlignment** named argument inside the **Column** widget and pass to it **MainAxisAlignment.center** to Change the layout of the widgets to keep the dice image and play button widgets on the center of the screen.

![screenshot](https://lh3.googleusercontent.com/U7XaxuqkFFpb6HNPRrafV93KMGzNI_hi1TslgNfBOJAAy_xTUgHGsu5WmBfgvLshokOxiUOJw1btkV7Kt3-CEzq_YqYtaUzxLNgGCbH_G7xvJaYkZdxLJREuVKsys1EDybhixIL_)

5. Use the `Container` widget inside the `Column`'s `children` between the Dice image and the play button widgets to add some space between them. Pass height of 100 to the container widget.

   ```dart
   Container(height: 100),
   ```
