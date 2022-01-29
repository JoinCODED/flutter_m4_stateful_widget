1. We already declared the two **TextField** widgets, but to use them we will need to declare a controller.

Replace ` // TODO: #2 Add textEditingController` with

```dart
  final heightController = TextEditingController();
  final weightController = TextEditingController();
```

Here we created two **TextEditingController** variables, one for the height textfield, and the other for the weight textfield.

2. After we created the two **TextEditingController**, we need to link them with our text fields, So, to link them, we will use **controller** named argument, and we will pass the name of our controller variable, for example, in the height textfield, we will pass **heightController**.

```dart
TextField(
  controller: heightController,  // <- Here
  keyboardType: TextInputType.number,
  decoration: InputDecoration(
    hintText: 'Height (m)',
    border: OutlineInputBorder(),
  ),
),
```

3. We will link the **weightController** with the other **weight** **TextField** widget.

```dart
TextField(
  controller: weightController, // <- Here
  keyboardType: TextInputType.number,
  decoration: InputDecoration(
    hintText: 'Weight (kg)',
    border: OutlineInputBorder(),
  ),
)
```

4. Also, we will need to declare a new variable that will store the result, and show it inside the **Text** widget that has the empty value.

So, replace ` // TODO: #3 Add result variable` with

```dart
 String result = '';
```

> Here, we declared a new String variable; the name of the variable is **result**, and it has an empty value; later we will store the result inside it when the user presses the calculate button.

5. We will pass the result value inside the **Text** widget that has the empty value.

```dart
Text(
            result, // <- Here
            style: TextStyle(
              fontWeight: FontWeight.bold,
              color: Colors.amber[700],
              fontSize: 40,
            ),
          )
```

6. Now, let's add some logic for our BMI calculator, so when the user clicks the button it will calculate the BMI, and show the result inside the **Text** widget.

Inside the **onPressed** named argument inside the **ElevatedButton**, we will declare two variables one for the **height** and the other for the **weight**, and to get the input from the TextField widget we will use the **text** object inside the **TextEditingController**.

So, now we will type codes that take the height from the heightController, and since the **heightController.text** is **String** type we need to parse it to **double** type. To do this we will use the **double.parse()** method, and we will pass the **heightController.text** string inside it.

```dart
ElevatedButton.icon(
   icon: Icon(Icons.sentiment_dissatisfied_outlined),
   label: Text(
    'Calculate',
    style: TextStyle(
      fontWeight: FontWeight.bold,
    ),
   ),
   onPressed: () {

    var height = double.parse(heightController.text); // <- Here


   },
   )
```

7. Also, we will need to repeat this step for the weight.

   ```dart
   var weight = double.parse(weightController.text);
   ```

   > Note: this time we use **weightController** not the **heightController**

8. To calculate the bmi we will use this formula,

   > bmi = weight / (height \* height)

Also, we will store it inside the **bmi** variable.

8. Since our result variable is String, we will need to add conditions for the bmi status, so we will create a function that takes the **bmi** variable, and convert it to a status such as Fat, Normal, Thin.

Replace, `// TODO: #4 bmiStatus function` with

```dart
  String bmiStatus(double bmi) {
    if (bmi <= 20) {
      return 'Thin';
    } else if (bmi < 25 && bmi > 20) {
      return 'Normal';
    } else if (bmi >= 25) {
      return 'Fat';
    } else {
      return '';
    }
  }
```

> Here we created a function that takes one double argument, and return the String, So, in our case, it will take the bmi value, and check if it is less than or equal to 20, if so it will return ‘Thin’ String, or if it between 25 and 20, it will return ‘Normal’ String, or if the bmi bigger than 25 it will return ‘Fat’.

9. After we create **bmiStatus**, we will use it inside the onPressed function, so we will reassign the return value inside the result variable.

   ```dart
   result = bmiStatus(bmi);
   ```

10. Now, save the main.dart, and try to click the button, see if you can see the result ^\_^.

11. You didn’t see any change on the screen right ^\_^, because we need to tell Flutter to rebuild the widget tree again. So, to do this we will need to convert the **HomePage StatelessWidget** to **HomePage statefulwidget**.

> To do this very quickly we can use the shortcut that is inside the VS Code. Hover **HomePage StatelessWidget**, and click
>
> - Mac: **Command + .**
>
> - Windows: **Ctrl + .** >
>
> ![screenshot](https://lh6.googleusercontent.com/8EGAOrVnkv5CjdacaGE4DVpHZ5Xi8wc2kxJgX2Jqh8FY9RjIujeyCtPNhd6C_A0hEYH2qlBXx3jz5jvZ1uGaTOW72LYq6yzygs7TnHVZy3CzsW18ynqnNKeyId5Ze1Ba5ga0WR6j)
>
> Then click, Convert to **StatefulWidget**

12. Later we will know more about the difference between Stateless and Stateful widgets. Right now, just know that **StatefulWidget** can change its state, so it can rebuild its widgets tree inside the build method.

13. After we convert the HomePage to **StatefulWidget**, we will use **setState()**, which comes with the **StatefulWidget**.

> so when we type **setState()**, the HomePage widget will rebuild (repaint) the build method again, but this time it will use the new value inside the **result** variable.

```dart
ElevatedButton.icon(
    icon: Icon(Icons.sentiment_dissatisfied_outlined),
    label: Text(
      'Calculate',
      style: TextStyle(
        fontWeight: FontWeight.bold,
      ),
    ),
    onPressed: () {
      var height = double.parse(heightController.text);
      var weight = double.parse(weightController.text);

      var bmi = weight / (height * height);

      result = bmiStatus(bmi);

       setState(() {});  // <- Here
    },
  ),
```

14. Now click the restart button, and type some values inside the text fields, then click the calculate button.

![screenshot](https://lh6.googleusercontent.com/drTTIZ6WgxSuH-vXIuAo4DlFk7BTJ7Ggb-f3FZss54K-NalYKOE_PVKkB0g6LBJEp-yQ5ihsygr5XG88CNuzJ7lgGwzn8_BLIiQeZzhYLBaHiBOwO7APfDwwq0W9YEZW2_-jrnpw)

15. Try to click the calculate button without writing any values inside the fields.

You will get an error,

![screenshot](https://lh3.googleusercontent.com/HraHbxJofcPzoUPCnzvtm7R8bYafVcktFUOAfsLBPujvQMcYNhmqtkXoLOT4HjuzkUrwbjMrcBu-4pS1WxsRyJgMkFWWFwG7qzp2fz3gfjrwZyBYwoCxDAg9_5QlxuLPp0lghqNF)

![screenshot](https://lh3.googleusercontent.com/dQ4xt15uHLNgCUUINNo-kJg67P7aksCuO7zA0lF2kUBEejJHBeTUz_TcKyBqs4Ra0tLh5AOi4hsaNt7bEsXOJadef2dpwZ-RdFM2Y0cbFv-Ssbdd8c1FzrrPV4EuVuvyWl6dn2uW)

To solve this issue, we will use the if condition, and check if the text field controllers are empty or not.

```dart
onPressed: () {
	// Here
  if (heightController.text.isNotEmpty ||
      weightController.text.isNotEmpty) {
    var height = double.parse(heightController.text);
    var weight = double.parse(weightController.text);

    var bmi = weight / (height * height);

    result = bmiStatus(bmi);

    setState(() {});
  }
}
```

> Here our logic for the bmi calculator will not work if the heightController.text and weightController.text are empty. So, with this solution, we protected our app from error ^\_^.

16. Now, we will add an image widget that depends on the bmi status.

17. Restart the app.

18. Add this widget above the **Text** result widget.

    ```dart
    Container(
                // 2
                padding: EdgeInsets.all(40),
                //3
                child: Image.asset(
                 // 3
                  'assets/$result.png',
     			// 4
                  height: 230,
                  width: 230,
                ),
              ),
    ```

        	1. We wrapped the Image widget with a **Container** to add padding for our Image widget.
        	2. Here, we used the **Image.asset** widget to show the images that are inside the **assets** folder.
        	3. Here, we typed the path for our image, but we used the **$result** variable to change the image depending on the result variable.
        	4. Specify the height and width of our image widget.

19. Note that we will get an error on our app because the **result** variable is an empty string when we restart the app so to resolve this issue we should write the if condition before the Image widget. This condition checks if the result is empty or not, So it will not draw the Image widget on the screen if the result value is empty.

![screenshot](https://lh5.googleusercontent.com/4sGJJL_POOgdmeYCHXiCL_aCkRKheX0yskOlyR3VBYWrVR5OyAmwhnt7lWNyMD7m7-6OR7mVMKvC-dJ5dDlDIAmQ_1Kn8xPD7XUQ27-cc5RZxCy07ksaF-tkrO8rf2tqZI_gwWs-)

To solve this issue, we will write if the condition above the Container Image widget

> **Very important:** when we use the if condition inside the widgets tree, we can not use **if else** and curly brackets, so we just write if( ), and inside the parentheses,Github we check if the result value is not empty, if so it will draw the image. If the result value is empty it will ignore drawing this **Container Image.asset** widget.

```dart
if (result != '')  // here
  Container(
    padding: EdgeInsets.all(40),
    child: Image.asset(
      'assets/$result.png',
      height: 230, // 4
      width: 230, // 5
    ),
  )
```

Our final result

![screenshot](https://lh3.googleusercontent.com/7zH8xw73kbxm4TcTe3qk6AGbO69uym22-shz8VDUPfJwk_jugi9o56FrN_t3p6FqUd0XK7uyJraIzLQq_BCrfLuxzAUZUHMewDrtKKMkmnJoWrOVem0glONkSMqaJOxJNIpxBcZ6)

![124383224-fc0f3f80-dcd3-11eb-9bf1-2ec513b90757](https://user-images.githubusercontent.com/24327781/142021150-c9fcaded-27b5-49c6-92ca-b427a4774f02.gif)
