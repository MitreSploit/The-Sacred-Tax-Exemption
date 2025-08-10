C# has a switch statement that isn't coincidentally named. 
It is named after the railroad switching analogy. 
Sometimes the paths of `if`, `else if` and `else` can become long and complicated. 
We can use **`switch`** statements for these exact reasons and split the track. 

We call these different pathways **`arms`** based on a single values properties. 
It really depends on the situation, because there are times where it may just be easier to write `if/else`. 

# Switch Statements
- Similar to the if/else/else if blocks from before, I was able to use a **`switch`** statement when the user made a choice.
- This achieves the same goal, but it's a lot cleaner.
- One thing I've found is that the switch will want to error as your writing it until you put in a `break`.
- I've also set a `default`, this will capture when someone enters an `int` value that doesn't match the case. 
- Use curly braces `{}` to denote the beginning and end of the `switch` block.
- Each **arm** of the switch starts with the word `case` followed by a value to check against. 
- **`break`** is used to stop the flow of execution.  
- `default` is a catch all if nothing else was a match. `default` can go anywhere in the list, but conventionally at the end. **`default` is optional, but very common.**
- Any data type can be used. We used `int` but it very easily could have been a `string` etc. 

```C#
static void Main(string[] args)
{
    //switch statements
    Console.WriteLine("Hello friend! which will you chose today?");
    Console.WriteLine("""
        1 - Rest
        2 - Party
        3 - Day Drinks
        4 - Couch Chills
        """);

    int userInput = int.Parse(Console.ReadLine());

    switch (userInput)
    {
    // If the user enters a value of '1' and so on...
        case 1:
            Console.WriteLine("Rest it is fella!");
            break;
        case 2:
            Console.WriteLine("Every night pal!");
            break;
        case 3:
            Console.WriteLine("Day drinks! You're a wild one!");
            break;
        case 4:
            Console.WriteLine("Go on, take it easy!");
            break;
        default:
            Console.WriteLine("Can't say I know that one?");
            break;
    }
}
```

# Multiple Cases for the Same Arm
In C# it is also fine to have multiple cases for the same arm. Like if I wanted the input `1` and `2` to have the same resulting output, I could do something like this
```C#
static void Main(string[] args)
{
    //switch statements
    Console.WriteLine("Hello friend! which will you chose today?");
    Console.WriteLine("""
        1 - Rest
        2 - Rest
        3 - Day Drinks
        """);

    int userInput = int.Parse(Console.ReadLine());

    switch (userInput)
    {
    // Case 1 and 2 will be the same and output "Rest it is fella!"
        case 1:
        case 2:
            Console.WriteLine("Rest it is fella!");
            break;
        case 3:
            Console.WriteLine("Day drinks! You're a wild one!");
            break;
        default:
            Console.WriteLine("Can't say I know that one?");
            break;
    }
}
```


#  Switch Expressions (VERY USEFUL)
Switches also come in an expression format. 
In expression form, each arm is an expression. This can simplify our output significantly for the above!

```C#
static void Main(string[] args)
{
    //switch statements
    Console.WriteLine("Hello friend! which will you chose today?");
    Console.WriteLine("""
        1 - Rest
        2 - Party
        3 - Day Drinks
        """);

    int userInput = int.Parse(Console.ReadLine());

    string playerResponse;
    playerResponse = userInput switch
    {
        1 => "Rest it up pal!",
        2 => "Party all the time!", // Separate each arm with a comma.
        3 => "WOOOOO! Day drinks!",
        _ => "Dunno what you mean?" // Underscore will represent our default.
    };
    Console.WriteLine(playerResponse);
}
```

- This has removed a lot of our clutter and made more streamlined code. 
- In this format, we use the `=>` operator to separate the arms condition from it's expression. 
- Breaks are gone in this case, but each arm can have only one expression. 
- Each arm is separated by a comma `,`
- **With a switch expression, you must have something to evaluate to, or the program will crash. Best practice is to just use the wildcard `_` to say default.**
- One version of switch or if/else is not universally better than others. Pick the one that works best and cleanest in your code. 