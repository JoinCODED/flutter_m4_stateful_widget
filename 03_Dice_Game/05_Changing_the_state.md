To understand the state, we need to understand what happens when we create a new variable.

In our case, we created the **randomNum1** variable of type integer.

![screenshot](https://lh6.googleusercontent.com/AaLsDlgcSDVGbbEYDM66CR4Uc1sZsJXicKhq6JR7qr5W-ixOEPjnawJo2tmPyMi0CwghhQf4-R1xdaAGUDQLW93G_iLilUU2AKFr4lPtTqCMYPaGNyOezYv4BebtpLQOdged8WNM)

![screenshot](https://lh5.googleusercontent.com/__PXMqOBl4ZfUFsMicRXaCVfAEUSwXv0ZWAaoh-GxmKLBnsq0LblnyfNtNhlOIXzMs0NSPgAmlRxiJGDaTDxM9L75TxMjnvYmqsq9DLzUthM-VlAbei5euTFDXH2aXlskUhOc6ug)

In our device, we have **RAM** which is a form of computer memory. To keep things easy, just imagine the **RAM** as a collection of boxes.

![screenshot](https://lh5.googleusercontent.com/i366W_K7BL3ZAS08IzUXBTdap-bJegcukOMWmF5a4sw8UopFFrdKBnk19sN15PAKBSpTY9hYgoGFL9_S-yS7X3equtZDu-w35ZqJqDQJNkF8e0JBSQe_VAkIRJGapozRxhSmgS5S)

When you create a new variable, you allocate one box inside the memory. In our case, we have created the **randomNum1** variable of type int, which means that we are telling flutter to allocate one box on the memory. We named this box **randomNum1**, and gave it a type of integer. Inside the box, we add the value of **randomNum1**.

![screenshot](https://lh3.googleusercontent.com/zrD-fRwCbGBjQJflzdwJGF3GuyqmO5ZtaksVWVr-OsiHU-dtlMRfUbAdtWSjk3xBxrez9udMqX7n3rBcFTa-gNCBcQtv0EYoYW1ljLG5jVq9DfxzXPlytTreGmKRaRDRiM1taafK)

The reason that we do not see the changes on the screen is because we just changed the variable in the memory, we did not change the state. State is the dynamic data you see on the screen. When you change a value of a variable, and this variable is connected to a widget, you need to tell flutter to rebuild the state of the widget by calling the **setState** function.

> **Note:** The reason why the **print** function prints the new value of the variable in the console even though we did not change the state of our widget is because the print function reads the latest data on the memory.

To use the **setState** function, you need to change the **Stateless** widget to **Stateful** widget because the **Stateless** widget does not have the ability to change its state, but the **Stateful** widget does.

17. Convert **HomePage** to **Stateful** widget

> To do this very quickly, you can use the shortcut that is inside VS Code. Hover over **HomePage StatelessWidget**, and click:
>
> - Mac: **Command + .**
> - Windows: **Ctrl + .** > ![screenshot](https://lh6.googleusercontent.com/8EGAOrVnkv5CjdacaGE4DVpHZ5Xi8wc2kxJgX2Jqh8FY9RjIujeyCtPNhd6C_A0hEYH2qlBXx3jz5jvZ1uGaTOW72LYq6yzygs7TnHVZy3CzsW18ynqnNKeyId5Ze1Ba5ga0WR6j)
>
> Then click: **Convert to StatefulWidget**
