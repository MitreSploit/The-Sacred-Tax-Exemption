Technically the `Console` Class has properties that we are able to use. 

#### Console.Write
Previously I've used `Console.WriteLine` to write text to the terminal. However we are also able to use `Console.Write`. This achieves the same goal but it allows you to write on the same line.  This has its uses, Like when you want to ask the user a question and allow them to answer on the same line. It's also useful if you want to put snippets of information on the same line. 

```C#
    static void Main(string[] args)
	{
    Console.WriteLine("Gday!");
    Console.Write("Hello stranger, what is your name? ");
    string userName = Console.ReadLine();

    // Output looks like this:
    // Hello stranger, what is your name? YourNameHere
	}
```

#### Console.ReadKey
You can use `ReadKey` method to accept user input. `ReadKey` accepts a single user input before it will continue. 
The issue with the below code is that it will display any user input to the terminal. 
```C#
internal class Program
{
    static void Main(string[] args)
    {
        Console.WriteLine("Press any key to continue. ");
        Console.ReadKey(); // This will display user input to the terminal
    }
}
```

To work around this issue, you can an `overload` - covered in level 13. We use a [bool] `true` value to say that the input should be intercepted & it will not be displayed to the console window.
```C#
static void Main(string[] args)
{
    Console.WriteLine("Press any key to continue. ");
    Console.ReadKey(true); // This stops user input from displaying to the terminal
}
```

#### Console Colours
We can use `Console.BackgroundColor` and `Console.ForegroundColor` (These are properties and not methods) to change the text colours in the terminal.
`ConsoleColor` however is an **Enumeration**. This will be covered later in Level 16. 
In short, an **Enumeration** is what we used to define a set of values in a set of values and gives each a name. `White` and `Magenta` are two names in  the **Enumeration** collection. 
```C#
static void Main(string[] args)
{
    Console.BackgroundColor = ConsoleColor.White;
    Console.ForegroundColor = ConsoleColor.Magenta;
    Console.WriteLine("This will change all text in the terminal");
}
```

One issue with the above code is that all the text on the screen will change colour, but there will still be a lot of black space from previous characters. If you run `Console.Clear()`, you will be able to wipe all the previous text and the whole terminal will change to the background colour. 
**The primary objecting for `Clear` is to clear all text on the terminal, which it will do.**
```C#
static void Main(string[] args)
{
    Console.BackgroundColor = ConsoleColor.White;
    Console.ForegroundColor = ConsoleColor.Magenta;
    Console.Clear();
    Console.WriteLine("This will change all text in the terminal");
}
```

#### Console.Title
`Console.Title` can be used to change the text displayed in the console window's title bar. 
```C#
Console.Title = "Hello, Universe!";
```


#### Console.Beep
The absolutely ridiculous `Console.Beep`. Simply makes the terminal make a noise. Super dumb. Takes in two pieces of information. The first is frequency and the second is duration. 
- The higher the frequency number, the higher the pitch. 440 is a nice middle pitch. 
- You can absolutely make songs out of this. 

**Super Mario Bros theme:**
```C#
static void Main(string[] args)
{
    Console.Beep(659, 125); Console.Beep(659, 125); Thread.Sleep(125); Console.Beep(659, 125); Thread.Sleep(167); Console.Beep(523, 125); Console.Beep(659, 125); Thread.Sleep(125); Console.Beep(784, 125); Thread.Sleep(375); Console.Beep(392, 125); Thread.Sleep(375); Console.Beep(523, 125); Thread.Sleep(250); Console.Beep(392, 125); Thread.Sleep(250); Console.Beep(330, 125); Thread.Sleep(250); Console.Beep(440, 125); Thread.Sleep(125); Console.Beep(494, 125); Thread.Sleep(125); Console.Beep(466, 125); Thread.Sleep(42); Console.Beep(440, 125); Thread.Sleep(125); Console.Beep(392, 125); Thread.Sleep(125); Console.Beep(659, 125); Thread.Sleep(125); Console.Beep(784, 125); Thread.Sleep(125); Console.Beep(880, 125); Thread.Sleep(125); Console.Beep(698, 125); Console.Beep(784, 125); Thread.Sleep(125); Console.Beep(659, 125); Thread.Sleep(125); Console.Beep(523, 125); Thread.Sleep(125); Console.Beep(587, 125); Console.Beep(494, 125); Thread.Sleep(125); Console.Beep(523, 125); Thread.Sleep(250); Console.Beep(392, 125); Thread.Sleep(250); Console.Beep(330, 125); Thread.Sleep(250); Console.Beep(440, 125); Thread.Sleep(125); Console.Beep(494, 125); Thread.Sleep(125); Console.Beep(466, 125); Thread.Sleep(42); Console.Beep(440, 125); Thread.Sleep(125); Console.Beep(392, 125); Thread.Sleep(125); Console.Beep(659, 125); Thread.Sleep(125); Console.Beep(784, 125); Thread.Sleep(125); Console.Beep(880, 125); Thread.Sleep(125); Console.Beep(698, 125); Console.Beep(784, 125); Thread.Sleep(125); Console.Beep(659, 125); Thread.Sleep(125); Console.Beep(523, 125); Thread.Sleep(125); Console.Beep(587, 125); Console.Beep(494, 125); Thread.Sleep(375); Console.Beep(784, 125); Console.Beep(740, 125); Console.Beep(698, 125); Thread.Sleep(42); Console.Beep(622, 125); Thread.Sleep(125); Console.Beep(659, 125); Thread.Sleep(167); Console.Beep(415, 125); Console.Beep(440, 125); Console.Beep(523, 125); Thread.Sleep(125); Console.Beep(440, 125); Console.Beep(523, 125); Console.Beep(587, 125); Thread.Sleep(250); Console.Beep(784, 125); Console.Beep(740, 125); Console.Beep(698, 125); Thread.Sleep(42); Console.Beep(622, 125); Thread.Sleep(125); Console.Beep(659, 125); Thread.Sleep(167); Console.Beep(698, 125); Thread.Sleep(125); Console.Beep(698, 125); Console.Beep(698, 125); Thread.Sleep(625); Console.Beep(784, 125); Console.Beep(740, 125); Console.Beep(698, 125); Thread.Sleep(42); Console.Beep(622, 125); Thread.Sleep(125); Console.Beep(659, 125); Thread.Sleep(167); Console.Beep(415, 125); Console.Beep(440, 125); Console.Beep(523, 125); Thread.Sleep(125); Console.Beep(440, 125); Console.Beep(523, 125); Console.Beep(587, 125); Thread.Sleep(250); Console.Beep(622, 125); Thread.Sleep(250); Console.Beep(587, 125); Thread.Sleep(250); Console.Beep(523, 125); Thread.Sleep(1125); Console.Beep(784, 125); Console.Beep(740, 125); Console.Beep(698, 125); Thread.Sleep(42); Console.Beep(622, 125); Thread.Sleep(125); Console.Beep(659, 125); Thread.Sleep(167); Console.Beep(415, 125); Console.Beep(440, 125); Console.Beep(523, 125); Thread.Sleep(125); Console.Beep(440, 125); Console.Beep(523, 125); Console.Beep(587, 125); Thread.Sleep(250); Console.Beep(784, 125); Console.Beep(740, 125); Console.Beep(698, 125); Thread.Sleep(42); Console.Beep(622, 125); Thread.Sleep(125); Console.Beep(659, 125); Thread.Sleep(167); Console.Beep(698, 125); Thread.Sleep(125); Console.Beep(698, 125); Console.Beep(698, 125); Thread.Sleep(625); Console.Beep(784, 125); Console.Beep(740, 125); Console.Beep(698, 125); Thread.Sleep(42); Console.Beep(622, 125); Thread.Sleep(125); Console.Beep(659, 125); Thread.Sleep(167); Console.Beep(415, 125); Console.Beep(440, 125); Console.Beep(523, 125); Thread.Sleep(125); Console.Beep(440, 125); Console.Beep(523, 125); Console.Beep(587, 125); Thread.Sleep(250); Console.Beep(622, 125); Thread.Sleep(250); Console.Beep(587, 125); Thread.Sleep(250); Console.Beep(523, 125);
}
```