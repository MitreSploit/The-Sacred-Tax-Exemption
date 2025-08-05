# Alignment
```C#
    static void Main(string[] args)
    {
        string myName = "Matt";
        Int32 myAge = 32;
        string herName = "Susan Storm";

        // Alignment output examples: 

        Console.WriteLine($"Name#1  {myName, 20}");
        Console.WriteLine($"Name#2  {herName, 20}");
    }
}
```

The output of the above looks like:
```C#
Name#1                  Matt
Name#2           Susan Storm
```

#### Whitespace Before and After a variable
What this code is doing is reserving 20 characters for the name's display. If the length is less than 20, it adds whitespace before it to achieve the desired width. You can also do this with a negative number to have the whitespace before the word. Here is the difference:
```C#
    static void Main(string[] args)
    {
        string myName = "Matt";
        Int32 myAge = 32;
        string herName = "Susan Storm";

        // Alignment output examples: 

        Console.WriteLine($"Name#1 {myName, 20} whitespaceCheck");
        Console.WriteLine($"Name#2 {herName, 20} whitespaceCheck");

        // Whitespace after the word
        Console.WriteLine($"Name#1 {myName,-20} whitespaceCheck");
        Console.WriteLine($"Name#1 {herName,-20} whitespaceCheck");
    }
}
```

**Terminal Output:**
```C#
Name#1                 Matt whitespaceCheck // 20 characters before the word
Name#2          Susan Storm whitespaceCheck 
Name#1 Matt                 whitespaceCheck // 20 characters after the word
Name#1 Susan Storm          whitespaceCheck
```

**Limitations:**
There are two notable limitations with the alignment we are using:
1. There is no convenient way to center the text. 
2. If the text you are writing is longer than your preferred width, then it will mess up your columns. **(If I made one of the Names way too long, then `whitespaceCheck` is going to be way off)** - You could write code to achieve this, but there is no automatic fix. 

# Formatting
Use this with string interpolation. How do you want to display your data? 
Lets say that you are wanting to write out a number to the terminal, like Pi for example.
You don't always want to write Pi in it's entirety. Instead, you can use formatting to say only give three digits after the decimal place. 

**EXAMPLE:**
```C#
static void Main(string[] args)
{
    // Using the inbuilt PI, but only displaying the characters up to 3.14159
    Console.WriteLine($"{Math.PI:0.00000}");

	// If I instead chose to display 3.141 -- The result will actually round up.
	// Instead I will get 3.142 (Round up from 5).
	Console.WriteLine($"{Math.PI:0.000}");
}
```

In the above format I have specified with the 0's that I want a number to appear even if the number isn't strictly necessary. 

**EXAMPLE:**
```C#
static void Main(string[] args)
{
	// This will actually output 044.000
    int myNum = 44;
    Console.WriteLine($"{myNum:000.000}");
}
```

#### Using Hash
If you instead filled the spaces with `#`. The hash symbol can be used to leave a place for a number in the same way, but will only display a significant number:

**EXAMPLE:**
```C#
internal class Program
{
    static void Main(string[] args)
    {

		// EXAMPLE 1: 

		// The following outputs 44.0
		// I've specified that a single character is essential
		// but the others are not essential

        int myNum = 44;
        Console.WriteLine($"{myNum:###.0##}");


		// EXAMPLE 2: 

		// I am also able to do something like this: 
		Console.WriteLine($"{55.232:###.0##}"); // Variable not required


		// EXAMPLE 3:

		// Outputs 55.2
		Console.WriteLine($"{55.232:###.#}");
    }
}
```

#### Using Percentage
If we want to display a number as a percentage instead, this is also achievable. 

```C#
static void Main(string[] args)
{
    float playerHealth = 75.4f;
    float maxHealth = 200;

    // Output 37.7% -- Very very useful!
    Console.WriteLine($"{playerHealth/maxHealth:0.0%}"); 
    
    // I could also be able to use # instead of the 0's, same as before. 
}
```

**Shortcuts for the above**
```C#
static void Main(string[] args)
{
    float playerHealth = 75.4f;
    float maxHealth = 200;

    Console.WriteLine($"{playerHealth/maxHealth:P}"); // Is the equivilant to 00.00%
    Console.WriteLine($"{playerHealth / maxHealth:P1}"); // Is the equivilant to 0.0%

    Console.WriteLine($"{playerHealth / maxHealth:F}"); // Is the same as 0.00
    Console.WriteLine($"{playerHealth / maxHealth:F5}"); // Is the same as 0.00000 and outputs 0.37700
}
```


# Challenge Lab
The scenario is that there is a city arranged like a grid. The city is being attacked with bombs and they can protect a section of the grid at a time. 
The grid is arranged like this:

```PowerShell
8  W B W B W B W B
7  B W B W B W B W
6  W B W B W B W B
5  B W B W B W B W
4  W B W B W B W B
3  B W B W B W B W
2  W B W B W B W B 
1  B W B W B W B W
   1 2 3 4 5 6 7 8 
```

**EXAMPLE:**
If the enemy is targeting Row 6, Column 5:
Deploy to the following:
- (6, 4)
- (5, 5)
- (6, 6)
- (7, 5)

**Logic Problem:**
Lets say the attack happens at 2/2.

- Deployment instructions must be in a different color.
- Compute the neighboring rows and columns.
- Play a `Console.Beep` when the results are displayed.

- Left axis can be `x`
- Right axis can be `y`

1. directly above `x + 1` & `y`
2. directly right  `x` & `y + 1`
3. directly below is `x - 1` & `y`
4. directly left is `x` & `y - 1`

Neither `x` nor `y` can be less than 0. 


# Solution
Works - However error handling is required for outside of 0 & 8.

```C#
    static void Main(string[] args)
    {
        Console.Title = "Defense of Consolas";

        Console.Write("Target Row? ");
        int x = Convert.ToInt32(Console.ReadLine()); // without error handling, Conver.ToInt32 handles null values greater than int.Parse

        Console.Write("Target Column? ");
        int y = Convert.ToInt32(Console.ReadLine());

        Console.Beep(100, 10);
        Console.ForegroundColor = ConsoleColor.Red;
        Console.WriteLine("\nDeploy to: ");
        Console.WriteLine($"{x + 1}, {y}");
        Console.WriteLine($"{x}, {y + 1}");
        Console.WriteLine($"{x - 1}, {y}");
        Console.WriteLine($"{x}, {y - 1}");

    }
}
```


# Final Solution
**Note:** 
Will not perform error handling for users who enter something that isn't a number.
Also not handling any set up to catch user input that is greater than 8, It will simply present the standby message. 

```C#
using System.Collections;
using System.ComponentModel;
using System.ComponentModel.DataAnnotations;
using System.Security.Cryptography.X509Certificates;
using System.Threading.Channels;

namespace TestingTime
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.Title = "Defense of Consolas";
            Console.Clear();

            Console.Write("Target Row? ");
            int x = Convert.ToInt32(Console.ReadLine()); // without error handling, Conver.ToInt32 handles null values greater than int.Parse

            Console.Write("Target Column? ");
            int y = Convert.ToInt32(Console.ReadLine());

            Console.Beep(100, 10);
            Console.ForegroundColor = ConsoleColor.Red;
            Console.BackgroundColor = ConsoleColor.White;
            Console.WriteLine("\nDeploy to: ");

            string personA = ($"{x + 1}, {y}");
            string personB = ($"{x}, {y + 1}");
            string personC = ($"{x - 1}, {y}");
            string personD = ($"{x}, {y - 1}");

            string[] positionArr = {personA, personB, personC, personD}; // Contains our actual positions.  

            


            string[] names = { "Person A", "Person B", "Person C", "Person D" };

            // Our true false error handling idea: 
            bool printA = (x + 1 < 8);
            bool printB = (y + 1 < 8);
            bool printC = (x - 1 > 0);
            bool printD = (y - 1 > 0);

            bool[] handlingChecks = {printA, printB, printC, printD };

            int n = 0;



            foreach (string name in names)
            {
                if (handlingChecks[n])
                {
                    Console.WriteLine($"{names[n]} move to position: {positionArr[n]}");
                    n++;
                }
                else
                {
                    Console.WriteLine($"Remain on standby {names[n]}");
                    n++;
                }
            }
        }
    }
}

```