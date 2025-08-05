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


