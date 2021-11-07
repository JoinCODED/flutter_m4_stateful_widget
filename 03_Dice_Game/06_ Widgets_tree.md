#  Widgets tree



20. Then inside play function you need to call **setState()** function at the end of the function, because after you reassign the random number, and store it inside the **randomNum1** variable, you need to tell flutter to rebuild the widgets tree, in our case the widget tree of **HomePage** widget is the widgets that inside the build method.

    

![img](https://lh3.googleusercontent.com/34XI2TT9jqmGJsmWuM6H4EZyVnE4kRkpdqEQvu9iAHC6St3TSrc7CA1XE0_kGbV1atMbWAxzq7Jf2Bgn7gYuP9FC9nDYRfzlENXVzk8modlz64LVlelNZiAt7J2A94sKVfjNR77q)



21. Now let’s call the **setState()** function to rebuild the widgets tree, and see the changes after the value of the **randomNum1** variable was changed. Replace **play function** with

```dart
  void play() {
    randomNum1 = Random().nextInt(6) + 1;

    print(randomNum1);

    setState(() {});
  }
```





22. Now, try to restart the app, and click the play button ^_^.



23. Now let’s call the **setState()** function to rebuild the widgets tree, and see the changes after the value of the **randomNum1** variable was changed. Replace **play function** with

![img](https://lh3.googleusercontent.com/MdeiZ9FEnvCnbTNetkIxeLE_w3TdkwNwAhcA_RDIcKt-UYlS2BrUFHYEOajano3mSP50eUpm3XrvfeD1s2uYRDeJd4m_xcfyqQxQ0zLieAi_JUZSklIw1ByxvenpFmn7gZPdeCMB)





































































