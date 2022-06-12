5. After declaring the two **TextField** widgets, we need to use them somehow, and to do that we have to declare a controller.

Replace ` // TODO: #2 Add textEditingController` with the code below:

```dart
  final heightController = TextEditingController();
  final weightController = TextEditingController();
```

Here, we created two **TextEditingController** variables: one for the height `TextField`, and the other for the weight `TextField`.

6. Now, you need to link them with the text fields using **controller** named argument, then pass the name of the controller variable to it:

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

7. Same thing goes with **weightController**, pass it to weight **TextField**'s controller.

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

8. Declare a new variable to store the result in.

Replace ` // TODO: #3 Add result variable` with the code below:

```dart
 String result = '';
```

> Here, we declared a new String variable; The name of the variable is **result**, and it has an empty value; later, we will store the result inside it when the user presses the calculate button.

9. Pass the result variable to the **Text** widget that has the empty value.

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

10. Now, let's add some logic to the BMI calculator to make the button calculate the BMI and show the result inside the **Text** widget when the user clicks it.

Inside the **onPressed** named argument in the **ElevatedButton**, declare two variables: one for the **height** and the other for the **weight**. To get the input from the TextField widget, use the **text** object inside the **TextEditingController**.

Save the result of the height that comes from the heightController. Since the **heightController.text** is a **String** type, we need to convert it to **double** type. To do this, use the **double.parse()** method, and wrap the **heightController.text** with it.

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

11. Repeat the same step for the weight.

```dart
var weight = double.parse(weightController.text);
```

> Note: this time we use **weightController** not the **heightController**

12. Use the following formula to calculate the BMI.

> bmi = weight / (height \* height)

Then, store it inside the **bmi** variable.

13. Create a function that takes the **bmi** variable, and converts it to a status such as Fat, Normal, or Thin based on some conditions.

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

> Here, we created a `bmiStatus` function that takes one double argument, and returns a String. In our case, it will take the bmi value. If it is less than or equal to 20, it will return ‘Thin’ String, if it is between 25 and 20, it will return ‘Normal’ String, otherwise it will return ‘Fat’ String.

14. Call the `bmiStatus` function inside the **onPressed** function, and reassign the return value to the result variable.

```dart
result = bmiStatus(bmi);
```

15. Save the `main.dart` file, try to click the button, and check if you can see the result.

16. You didn’t see any changes on the screen, right? That is because we need to tell Flutter to rebuild the widget tree. To do that, we need to convert the **HomePage StatelessWidget** to **HomePage statefulWidget**.

> In order to convert the stateless widget to stateful very quickly, you can use the shortcut inside the VS Code: Hover over **HomePage StatelessWidget**, and press
>
> - Mac: **Command + .**
>
> - Windows: **Ctrl + .** >
>
> ![screenshot](https://lh6.googleusercontent.com/8EGAOrVnkv5CjdacaGE4DVpHZ5Xi8wc2kxJgX2Jqh8FY9RjIujeyCtPNhd6C_A0hEYH2qlBXx3jz5jvZ1uGaTOW72LYq6yzygs7TnHVZy3CzsW18ynqnNKeyId5Ze1Ba5ga0WR6j)
>
> Then, click Convert to **StatefulWidget**

17. Later on, we will dig deeper into the difference between Stateless and Stateful widgets. Right now, just know that **StatefulWidget** can change its state, and rebuild its widgets tree inside the build method.

18. Use the **setState()** method, which comes with the **StatefulWidget**.

> When we type **setState()**, the HomePage widget will rebuild (repaint) the build method, but this time it will use the new stored value of the **result** variable.

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

19. Click the restart button, and type some values inside the text fields, then click the calculate button.

![screenshot](https://lh6.googleusercontent.com/drTTIZ6WgxSuH-vXIuAo4DlFk7BTJ7Ggb-f3FZss54K-NalYKOE_PVKkB0g6LBJEp-yQ5ihsygr5XG88CNuzJ7lgGwzn8_BLIiQeZzhYLBaHiBOwO7APfDwwq0W9YEZW2_-jrnpw)

20. Try to click the calculate button without writing any values inside the fields.

You will get an error message 🙂.

![screenshot](https://lh3.googleusercontent.com/HraHbxJofcPzoUPCnzvtm7R8bYafVcktFUOAfsLBPujvQMcYNhmqtkXoLOT4HjuzkUrwbjMrcBu-4pS1WxsRyJgMkFWWFwG7qzp2fz3gfjrwZyBYwoCxDAg9_5QlxuLPp0lghqNF)

![screenshot](https://lh3.googleusercontent.com/dQ4xt15uHLNgCUUINNo-kJg67P7aksCuO7zA0lF2kUBEejJHBeTUz_TcKyBqs4Ra0tLh5AOi4hsaNt7bEsXOJadef2dpwZ-RdFM2Y0cbFv-Ssbdd8c1FzrrPV4EuVuvyWl6dn2uW)

To solve this issue, we will use the `if condition`, and check if the text field controllers are empty.

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

> Here, the logic for the bmi calculator will not work if the `heightController.text` and `weightController.text` are empty. With this solution, we protected our app from crashing down.

21. Add an image widget that depends on the bmi status.

22. Restart the app.

23. Add the following widget above the **Text** result widget.

    ```dart
    Container(
            // a
            padding: EdgeInsets.all(40),
            //b
            child: Image.asset(
              // c
              'assets/$result.png',
              // d
              height: 230,
              width: 230,
            ),
          ),
    ```

    > > a. We wrapped the Image widget with a `Container` to add padding for our Image widget.
    > > b. We used the `Image.asset` widget to show the images that are inside the `assets` folder.
    > > c. We typed the path for our image, but we used the `$result` variable to change the image depending on the result variable.
    > > d. We specified the height and width of our image widget.

    > >

24. Note that we will get an error because the **result** variable is empty when we restart the app. To resolve this issue, we should add the `if condition` before the Image widget. This condition checks if the result is empty, if so, the Image widget will not show up on the screen.

![screenshot](https://lh5.googleusercontent.com/4sGJJL_POOgdmeYCHXiCL_aCkRKheX0yskOlyR3VBYWrVR5OyAmwhnt7lWNyMD7m7-6OR7mVMKvC-dJ5dDlDIAmQ_1Kn8xPD7XUQ27-cc5RZxCy07ksaF-tkrO8rf2tqZI_gwWs-)

To fix what happens, we will add the `if condition` above the Container Image widget.

> **Very important:** when we use the `if condition` inside the widgets tree, we cannot use **if else** and curly brackets, so we just write `if( )`, and inside the parentheses, we check if the result value is not empty. If so, it will draw the image. Otherwise, it will not draw the **Container Image.asset** widget.

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

Our final result:

![124383224-fc0f3f80-dcd3-11eb-9bf1-2ec513b90757](https://user-images.githubusercontent.com/24327781/142021150-c9fcaded-27b5-49c6-92ca-b427a4774f02.gif)
