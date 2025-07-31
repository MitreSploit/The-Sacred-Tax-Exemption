# Variables
- Variables are named locations where data is stored in memory.
- Variable type is important because it lets the compiler know how much space to allocate in memory for the data and also makes sure the compiler knows how to use this data correctly.
- Each variable has 3 parts; A name, A type and a Value. 
- The first time you assign a value to a variable, you are initialising a variable. 
- You can only declare a variable once, but you can assign values to it over time. 
- Variables tend to gravitate towards the top of the code (Declaration).
```C#
namespace PracticeApps
{
    internal class Program
    {
        static void Main(string[] args)
        {
            // Initialising a variable - Assign a type
            string username;
            int number;

            // Assign a value
            username = Console.ReadLine();

            // Call the value
            Console.WriteLine("Hello " + username);

			// This will compile fine
			number = 20;

			// This will not - Cannot assign incorret data types
			number = "20"; // Treated as a string because of ""
        }
    }
}
```

# Handy tips
1. We can declare and initialise on the same line, like in previous example `int number = 5;`
2. We can declare variables back to back `int number1, number2, number3;`
3. You can assign the same thing to many variables at once like this:
```C#
// The value is assigned to c, then b becomes the value of c, then a becomes the value of b. 
// This is not very common, but it can have it's uses. 

int a, b, c;
a = b = c = 10;
``` 
4. Start a variable name with either a letter or an underscore. Don't use a number or symbol.
5. Don't use white spaces or symbols like (-) because C# assumes you're trying to subtract values. 
6. You cannot use a keyword like `int` as a variable name.
7. Don't abbreviate or remove letters - you spend more time reading code than writing it. It's not going to kill your memory to call the variable `playerScore` instead of `ps`. Common acronyms are the exception, like: `html`.
8. You can use longer names. Most IDE's have autocomplete functionality. 
9. Avoid names ending in numbers. They typically don't distinguish variables. 


