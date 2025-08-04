#### String Literal
Any text contained within a `" "` will be a string literal. This is a chunk of code that defines a specific value. 

#### Identifiers 
Are things like `Console` and `WriteLine`. They are also casually known as names. These are existing code elements. We can also define the names. 

#### Hierarchical Organization
`Concole.WriteLine` - This is a hierarchy structure where WriteLine is a member or child of Console. A `.` is called the **Member Access Operator**. 
It's all about context. You cannot just use `WriteLine`, the computer needs to know where to find it. 

# Classes and Methods
As mentioned before `Console` is a class. `WriteLine` is a method inside the class of `Console`.
A Class can have a method as a member. A Method cannot have a Class as a member. 

Think about Classes as entities that solve a single problem or perform a specific job or role. Think about a team, where the workload is spread across multiple individuals to perform the job. The `Console` Class's job is to interact with the Console Window. It does this well, but don't ask it to interact with other things. 

**A Class is usually composed of two things:**
1. The data they need to perform their job. 
2. Tasks they can perform. 

These tasks come in the form of Methods. A Method is a reusable block of code that you can request to run. 
Some Methods require data in order to perform their task. Like with the `WriteLine("Hello, World!)` method. You need to give it data to display to the console. Some Methods can even `return` information when they are finished. This allows data to flow too and from the method. 

# Namespaces
All Methods live in containers like a Class, but even Classes have to live somewhere. Most Classes live inside of `Namespaces`.
These are code organizational tools. They are valuable if you're dealing with thousands of classes. The `Console` class lives in a `Namespace` called `System`. **`System.Console.WriteLine("Hello, World!");`**

We didn't need to account for the System Namespace like what I exampled above, but in older versions of C# we would have needed too. Another way to accomplish this would have been by using `using System;`. The `using` directive.
This tells the Compiler if you come across an identifier, look at this `Namespace` first. This allows us to use a Class name without having to stick it in front each time. With C# 10, the compiler will automatically search through a handful of extremely common namespaces without you needing to call it out. 

These are only a few examples of the code available in the **`BASE CLASS LIBRARY (BCL)`**.

#### Program and Main
The Compiler takes the code we write, places it inside a method called `Main` as seen below and then puts that inside a class called `Program`. 
`Main` is the programs entry point. 

The Entry Point or Main Method is the code that will automatically run when the computer runs your program. Other Methods created outside of Main will not run unless they are called within Main. Our `WriteLine` method is called within `Main` and so it will automatically run. 

```C#
namespace PracticeApps
{
    internal class Program
    {
        static void Main(string[] args)
        {
            // This is a comment
            Console.WriteLine("Hello, World!");
        }
    }
}
```


#### Statements
The entire `Console.WriteLine("Hello, World!");` line is called a **`Statement`**.
This is a single command for the computer to run. Most C# Statements end in a `;`.
Our statements instructs the computer to use the `Console` class, with the `WriteLine` method to print the text `Hello, World!`.
You need to be very specific when giving the computer directions. 

Instead of thinking that the computer didn't do what I told it too, you will be a better programmer if you think "Why did the computer do things that way instead of what I expected?".

C# ignores whitespace, as long as it can tell where one things begins and ends, it will run regardless of spaces and tabs. 

```C#
namespace PracticeApps
{
    internal class Program
    {
        static void Main(string[] args)
        {
            // This is a comment
            Console.WriteLine("Do you know what you're doing here?");
            // User input here: 
            Console.Read();
        }
    }
}
```

