Now, we need to call the **setState** method at the end of the play function. Because when a random variable gets reassigned and stored inside the **randomNum1** variable, we need to tell flutter to rebuild the widgets tree, which in our case, is the widget tree of **HomePage**.

![screenshot](https://lh3.googleusercontent.com/34XI2TT9jqmGJsmWuM6H4EZyVnE4kRkpdqEQvu9iAHC6St3TSrc7CA1XE0_kGbV1atMbWAxzq7Jf2Bgn7gYuP9FC9nDYRfzlENXVzk8modlz64LVlelNZiAt7J2A94sKVfjNR77q)

15. Replace the **play function** with the code below to call the **setState()** method to rebuild the widgets tree.

```dart
  void play() {
    randomNum1 = Random().nextInt(6) + 1;

    print(randomNum1);

    setState(() {});
  }
```

16. Restart the app, and click the play button ^\_^.

![screenshot](https://lh3.googleusercontent.com/MdeiZ9FEnvCnbTNetkIxeLE_w3TdkwNwAhcA_RDIcKt-UYlS2BrUFHYEOajano3mSP50eUpm3XrvfeD1s2uYRDeJd4m_xcfyqQxQ0zLieAi_JUZSklIw1ByxvenpFmn7gZPdeCMB)
