1. In our BMI example, we will need to take two inputs from the user, the height and weight to calculate the BMI, so we will use a Textfield widget which will help us to take an input from the user.

2. Replace, `// TODO: #1 Add textfield` widget with

```dart
Container(
   // 1
   padding: EdgeInsets.only(left: 30, right: 30, top: 40),

   // 2
   child: TextField(
     // 3
     keyboardType: TextInputType.number,

     // 4
     decoration: InputDecoration(
       hintText: 'Height (m)',
// 5
       border: OutlineInputBorder(),
     ),
   ),
 ),
```

1. We wrap our **TextField** with a Container widget to add some padding for our **TextField**.
2. We declared a **TextField** that the widget will help us to get some input from the user.
3. We used **keyboardType** named argument to customize the phone keyboard, and this named argument takes a **TextInputType** object, and we have a lot of types such as a keyboard for email, number, etc.. But in our case, we will use **TextInputType.number** since the height is just a number.
   1. **decoration** named argument is used to add style for our textfield, and it takes an **InputDecoration()** object, so in our case, we add hint text that shows the user this field is for height. 1. We used the **border** named argument to add outline borders around the TextField widget.

![screenshot](https://lh4.googleusercontent.com/IqAMi0YPcMLR40Rf3YMa3Wqw1Me5qre8kqDoxgCBdaVVBZcawtLFJK0qtQpvB9hiiHpyYVlM3tk11VEUoLqwdE-eew3BpR928Zrdh5yn5mcd4f4nvTPuFmYq6eDcommu8AEf0UhK)

1. We will need another **`TextField`** widget for the weight, so duplicate the height TextField & its Container, and paste it under the height **`TextField`**, and change the hint text from “Height (m)” to “Weight (kg)”.

   Also, we changed the values for the padding,

   ```dart
    Container(
      padding: EdgeInsets.only(left: 30, right: 30, top: 40),
      child: TextField(
        keyboardType: TextInputType.number,
        decoration: InputDecoration(
          hintText: 'Weight (kg)',
          border: OutlineInputBorder(),
        ),
      ),
    ),
   ```

![screenshot](https://lh3.googleusercontent.com/SCprXCFro6__WInErJh-PCg89sWWRD6aMcN__E5RT2x0UjtizqIDLAW0YdpuElRtw9OqRLTm8MOf6lHiyBYVPDyEKJDthWxiDMEmhJH3mE9kWqT2fsPMWbBVh2ZiYGla_74jS_rM)

1. Now, we have already created two text field widgets that will help us to take the height and weight from the user. Now we will need a button widget that will help the user to calculate the BMI, so when the user clicks the button; it will calculate the BMI, and show the result.

![screenshot](https://lh6.googleusercontent.com/NXDIlsTSPCljcGZA0MIegbcxMrjQ2Fq8hx3DEdx2R9oVlcKypqtMIVvSTDvV_krwG7z2Vwy9f_vqmTDRDl7RiXClwYeMjX1QlsF6zvbFRgmxTqAx8fnQV8Sw3Wh6Ud8sXBvWDyuU)

```dart
//1
 Container(height: 30),
 //2
 Container(
   width: 150,
   height: 50,
   //3
   child: ElevatedButton.icon(
     // 4
     icon: Icon(Icons.sentiment_dissatisfied_outlined),
     //5
     label: Text(
       'Calculate',
       style: TextStyle(
         fontWeight: FontWeight.bold,
       ),
     ),
     // 6
     onPressed: () {},
   ),
 ),
```

1. We used **Container** to add some space between the button and the weight **TextField** widget.
2. We wrapped the **ElevatedButton** with a **Container** widget to specify the width and height for our button.
3. We used **ElevatedButton.icon** to add a text button with an icon inside it.
4. Add an icon inside the button, and we used the **Icon** widget to show sentiment Icon 🤩
5. Add a **Text** widget inside the button, and its label is “Calculate”.
6. We will use the **onPressed** function to calculate the BMI later.

7. Now, we also need a **Text** widget to show the result for the user. So, under the button widget add this widget.

```dart
 Text(
   '',
   style: TextStyle(
     fontWeight: FontWeight.bold,
     color: Colors.amber[700],
     fontSize: 40,
   ),
 ),
```

> Here, we have an empty **Text** widget, later we will declare a variable, and we will store the result inside the variable, then we will pass it inside this **Text** widget.

8. Now, we're kind of done with designing the User interface. From now we will add some logic for our app to calculate the BMI.
