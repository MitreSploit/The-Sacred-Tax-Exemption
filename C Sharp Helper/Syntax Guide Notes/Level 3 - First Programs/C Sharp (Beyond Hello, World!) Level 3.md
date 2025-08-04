Now lets tell the computer to perform three tasks. Ones all statements in the program are completed, the console will end. 
```C#
namespace PracticeApps
{
    internal class Program
    {
        static void Main(string[] args)
        {
            // In this example:
            // We are asking the computer to perform three different tasks. 
            // The program runs one statement at a time. 
            Console.WriteLine("Hi there!");
            Console.WriteLine("I'm so glad you're here!");
            Console.WriteLine("Did you know you can use cw to call Console WriteLine?");

            string newVar = Console.ReadLine();
            Console.WriteLine("you answered " + newVar);
        }
    }
}
```

#### Expressions
Expressions are bits of code like `+` that your program must process or evaluate to determine their value. A computer can use an expression to compute the value of data. 
We can concatenate strings together with expressions like this `Console.WriteLine("Hello " + "Dear friend");`

"Hello " + "Dear friend" is an Expression rather than a single value. 
Expressions are powerful. You can build expressions out of smaller expressions. 
Every expression once evaluated, will result in a single new value, which can then be used in other parts of code. 

# Variables
Containers for data.
Their contents can change or vary as the program runs. 

In order to use a variable, you must first declare it's data type. Once a variable exists, we can place data in it.
By putting a value into a variable container, we are assigning a variable. 
`string name;`

```C#
namespace PracticeApps
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("What's your name?");
            string myName = Console.ReadLine();
            Console.WriteLine("I guess my name is " + myName);
        }
    }
}
```

**Our code map for the above now looks like this:**
![[Untitled Diagram.svg]]

When I enter the word `string` into the IDE, the word turns blue. This is because `string` is a keyword in C#.
There are over 100 keywords in C#. 

#### Reading Text From Console
In C# we can use `Console.ReadLine();` to ask for user input. This takes in all data entered into the console until the user hits `Enter`.
The `ReadLine` method is not a method that requires additional data, so the parentheses are empty. 
In a previous example, I stored the data back from this into a variable, like this: `string name = Console.ReadLine();`

```C#
namespace PracticeApps
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Bread is ready.");
            Console.WriteLine("Who is the bread for?");
            string name = Console.ReadLine();
            Console.WriteLine("Noted: " + name + " got bread.");
        }
    }
}
```

# Compiler Errors

#### Compiler Errors and Warning
Double click on a code error to take you to the problematic line. 
A compiler warning means that the compiler is able to make the code work, but it thinks the code is suspicious. 
An example of this might come with the following:

```C#
string name = Console.ReadLine(); 
```

We will likely receive a warning for the above for **"Converting null literal or possible null value to a non-nullable type"**. This is because `ReadLine` may not actually give a response and an error may occur with a null value. 

# Build Configurations
When the compiler takes your source code and uses it to produce software, there are two build configuration types and you rarely ever need more. These type by default are Debug configuration and Release configuration. The main difference between these two is that Release has optimizations turned on. This allows the compiler to make adjustments that will make your code run faster. 
An example of this is if you declare a variable and never use it, then the compiler when optimized will strip it out. If you always ran your code fully optimized, it can be significantly harder to track things like this down. 



