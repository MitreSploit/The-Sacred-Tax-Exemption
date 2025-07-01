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






