# GestureDetector Widget



24. Now, when the user wants to play with the dice, he/she needs to click the play function widget. Let’s add other functionality which randomizes the dice when the user clicks the dice image :)

To do that just wrap the **Container** widget that wrapped the dice image with **GestureDetector** widge

```dart
		// 1
        GestureDetector(
              //2
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

1. **GestureDetector** helps us to add some events on the widget that wrap it. 
2. In our case, we used an **onTap** named argument to add an on tap event on the dice image.







Now the user can play with the dice by clicking the play button or by clicking the dice

<img src="https://lh5.googleusercontent.com/xUs0j-xHJhmIpXAe_OhlQGu0NqJzXprySV20smFU89o4xY46LAHcZi_A6y9IVyKX3FEkXCv4Yt0UiG6vVjqD7jVTFW0ZWp-mwx6Zs7Mxf4e3nFYik7VrBmcn_18ZbmN_3Ckruaw5" alt="img" width="350" />
