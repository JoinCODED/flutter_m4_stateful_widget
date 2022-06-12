1. To calculate the BMI, you need the user to fill two inputs: height and weight. To do that, use a `TextField` widget which helps you to get inputs from the user.
   >
2. Replace, `// TODO: #1 Add textfield widget` with the code below:

```dart
Container(
   // a
   padding: EdgeInsets.only(left: 30, right: 30, top: 40),

   // b
   child: TextField(
     // C
     keyboardType: TextInputType.number,

     // d
     decoration: InputDecoration(
       hintText: 'Height (m)',
       border: OutlineInputBorder(),
     ),
   ),
 ),
```

> > a. We wrapped our **TextField** in a `Container` widget to add some padding to the field.
> > b. We declared a **TextField** to get an input from the user.
> > c. We used the **keyboardType** named argument to customize the phone keyboard. This named argument takes a **TextInputType** object, which has a lot of types inside such as a keyboard for email, number, etc. However, in our case, we used **TextInputType.number** since height is just a number.
> > d. The **decoration** named argument is used to add style to the **TextField**. And this named argument takes an **InputDecoration()** object, which helped us to add:
> >
> > - A **hintText** that displays the label of the field to the user.
> > - A **border** named argument to add outline borders around the TextField widget.

![screenshot](https://lh4.googleusercontent.com/IqAMi0YPcMLR40Rf3YMa3Wqw1Me5qre8kqDoxgCBdaVVBZcawtLFJK0qtQpvB9hiiHpyYVlM3tk11VEUoLqwdE-eew3BpR928Zrdh5yn5mcd4f4nvTPuFmYq6eDcommu8AEf0UhK)

3. Duplicate the whole **`TextField`**'s Container of the height to add another **`TextField`** widget for the weight, paste it under the height widget directly, change the **hintText** from “Height (m)” to “Weight (kg)”, and change the padding value to `EdgeInsets.only(left: 30, right: 30, top: 40)`:
   > >
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

4. Add an `ElevatedButton` widget which helps the user to calculate the BMI, and shows the result when clicked.

![screenshot](https://lh6.googleusercontent.com/NXDIlsTSPCljcGZA0MIegbcxMrjQ2Fq8hx3DEdx2R9oVlcKypqtMIVvSTDvV_krwG7z2Vwy9f_vqmTDRDl7RiXClwYeMjX1QlsF6zvbFRgmxTqAx8fnQV8Sw3Wh6Ud8sXBvWDyuU)

```dart
//a
 Container(height: 30),
 //b
 Container(
   width: 150,
   height: 50,
   //c
   child: ElevatedButton.icon(
     // d
     icon: Icon(Icons.sentiment_dissatisfied_outlined),
     //e
     label: Text(
       'Calculate',
       style: TextStyle(
         fontWeight: FontWeight.bold,
       ),
     ),
     // f
     onPressed: () {},
   ),
 ),
```

> > a. We used **Container** to add some space between the button and the weight **TextField** widget.
> > b. We wrapped the **ElevatedButton** in a **Container** widget to specify the width and height of the button.
> > c. We used **ElevatedButton.icon** to add an icon inside.
> > d. We used the **Icon** widget to show a sentiment Icon 🤩.
> > e. We passed a **Text** widget to the button's label and passed “Calculate” to it.
> > f. We used the **onPressed** function to calculate the BMI later.

Now, you need a **Text** widget to show the result to the user. To do that, under the button widget, add the following:

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

> Here, you have an empty **Text** widget, later you will declare a variable, and will store the result inside it, then you will pass it to this **Text** widget.

Last but not least, you are almost done with designing the user interface. From now on, you will be adding some logic to the app to calculate the BMI.
