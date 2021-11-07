# Changing variables in Memory vs the changing the State



17. To understand the state first, we need to understand what happens when we create a new variable. 



In our case, we created the **randomNum1** variable, and its type is integer.

![img](https://lh6.googleusercontent.com/AaLsDlgcSDVGbbEYDM66CR4Uc1sZsJXicKhq6JR7qr5W-ixOEPjnawJo2tmPyMi0CwghhQf4-R1xdaAGUDQLW93G_iLilUU2AKFr4lPtTqCMYPaGNyOezYv4BebtpLQOdged8WNM)





![img](https://lh5.googleusercontent.com/__PXMqOBl4ZfUFsMicRXaCVfAEUSwXv0ZWAaoh-GxmKLBnsq0LblnyfNtNhlOIXzMs0NSPgAmlRxiJGDaTDxM9L75TxMjnvYmqsq9DLzUthM-VlAbei5euTFDXH2aXlskUhOc6ug)



First, we should know that in our devices we have **RAM** which is a form of computer memory, to keep things easy, just imagine the **RAM** is a collection of boxes. 

![img](https://lh5.googleusercontent.com/i366W_K7BL3ZAS08IzUXBTdap-bJegcukOMWmF5a4sw8UopFFrdKBnk19sN15PAKBSpTY9hYgoGFL9_S-yS7X3equtZDu-w35ZqJqDQJNkF8e0JBSQe_VAkIRJGapozRxhSmgS5S)



When you create a new variable you allocate one box inside the memory. For example, in our case we created the **randomNum1** variable and its type is int which means we tell flutter to allocate one box on the memory, and we named this box **randomNum1**, and its type is an integer. Also, inside the box, we put the value of **randomNum1**.

![img](https://lh3.googleusercontent.com/zrD-fRwCbGBjQJflzdwJGF3GuyqmO5ZtaksVWVr-OsiHU-dtlMRfUbAdtWSjk3xBxrez9udMqX7n3rBcFTa-gNCBcQtv0EYoYW1ljLG5jVq9DfxzXPlytTreGmKRaRDRiM1taafK)





18. Now, we understand that when we create a new variable we allocate a box in the memory. The reason that we don’t see the changes on the screen, is because we just changed the variable in the memory, we did not change the state. State is the data you see on the screen. So, when you change a value of a variable, and this variable is connected with a widget; you need to tell flutter to rebuild its state by calling the **setState** function. 

    > **Note:** The reason why the **print** function prints the new value of a variable on the console even though we did not change the state of our widget is because the print function reads the latest data on the memory. 





19. To use the **setState** function you need to change our widget from **Stateless** widget to **Stateful** widget because the **Stateless** widget doesn’t have the ability to change its state. On the other hand, **Stateful** can change its state.



Change **HomePage** to **Stateful** widget

>  To do this very quickly we can use the shortcut that is inside the VS Code. Hover **HomePage StatelessWidget**, and click 
>
> - Mac: **Command + .**
> - Windows: **Ctrl + .**
>
> ![img](https://lh6.googleusercontent.com/8EGAOrVnkv5CjdacaGE4DVpHZ5Xi8wc2kxJgX2Jqh8FY9RjIujeyCtPNhd6C_A0hEYH2qlBXx3jz5jvZ1uGaTOW72LYq6yzygs7TnHVZy3CzsW18ynqnNKeyId5Ze1Ba5ga0WR6j)
>
> Then click, Convert to **StatefulWidget**





















































