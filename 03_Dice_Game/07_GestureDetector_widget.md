When a user wants to play with the dice, he/she needs to trigger the play function. Let’s add another functionality that randomizes the dice when the user clicks the dice image :)

17. Wrap the **Container** of the dice image widget with the **GestureDetector** widget.

```dart
  // a
GestureDetector(
      //b
      onTap: play,
      child: Container(
        padding: EdgeInsets.all(10),
        child: Image.asset(
          'assets/images/dice_$randomNum1.png', // <- Here
          width: 120,
          height: 120,
        ),
      ),
    ),
```

a. **GestureDetector** helps us add some events to the widget that wraps it.
b. We used an **onTap** named argument to add a tap event to the dice image.

Now, the user can play with the dice by clicking the play button or by clicking the dice image.

![screenshot](https://lh5.googleusercontent.com/xUs0j-xHJhmIpXAe_OhlQGu0NqJzXprySV20smFU89o4xY46LAHcZi_A6y9IVyKX3FEkXCv4Yt0UiG6vVjqD7jVTFW0ZWp-mwx6Zs7Mxf4e3nFYik7VrBmcn_18ZbmN_3Ckruaw5)
