# Conditional Operator (VERY USEFUL)
Or sometimes referred to as the **`ternary operator`**. 
There are three parts to it. 
1. A `bool` expression.
2. A condition that should be evaluated if the condition is `true`.
3. And a condition that should be evaluated if the condition is `false`.

```C#
static void Main(string[] args)
{
    int score = 60;
    string textToDisplay = score > 85 ? "You Passed!" : "You Failed!"; // The condition - What happens if true - What happens if false

    Console.WriteLine(textToDisplay);
}
```

This is accomplished by placing the [`condition`], followed by `?`  then [`What happens if true`], followed by `:`, then [`What happens if false`]
- Be cautious using these to make sure your code is understandable.


# Challenge
There are watchtowers in the region around **Consolas** that can alert you when an enemy is spotted. With help from you they can tell you which direction the enemy is from the watchtower. 

**OBJECTIVE:**
1. Ask the user for an `x` and `y` value. These are coordinates of the enemy relative to the watchtowers location. 
2. Using their direction output either message
- "The enemy is here"
- "The enemy is to the [direction]"

**I'm very aware that a [switch] statement would have been more practical here, but we are not on that chapter.**

```C#
namespace Level9
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.ForegroundColor = ConsoleColor.White;
            Console.BackgroundColor = ConsoleColor.Magenta;
            string ascii = """
                           x < 0     x = 0     x > 0  |
                        +---------+---------+---------+
                y > 0   |   NW    |   N     |   NE    |
                        +---------+---------+---------+
                y = 0   |   W     |   !     |   E     |
                        +---------+---------+---------+
                y < 0   |   SW    |   S     |   SE    |
                        +---------+---------+---------+
                """;

            Console.WriteLine(ascii);
            Console.ResetColor();

            Console.Write("\nPlease enter a numerical value for x: ");
            int x = Convert.ToInt32(Console.ReadLine());

            Console.Write("Please enter a numerical value for y: ");
            int y = Convert.ToInt32(Console.ReadLine());

            string directionOutput = "?";

            if(x < 0 && y > 0) { directionOutput = "North West"; }
            else if (x < 0 && y == 0) { directionOutput = "West"; }
            else if (x < 0 && y < 0) { directionOutput = "South West"; }
            else if (x == 0 && y > 0) { directionOutput = "North"; }
            else if (x == 0 && y == 0) { directionOutput = "Here!"; }
            else if (x == 0 && y < 0) { directionOutput = "South"; }
            else if (x > 0 && y > 0) { directionOutput = "North East"; }
            else if (x > 0 && y == 0) { directionOutput = "East"; }
            else if (x > 0 && y < 0) { directionOutput = "South East"; }

            Console.WriteLine($"The Enemy is situated {directionOutput}");
        }
    }
}
```


