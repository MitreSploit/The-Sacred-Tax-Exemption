#### Comments in C Sharp
Comments have several uses, some of which are the following:
1. Adding descriptions to tricky bits of code. 
2. Leaving yourself TODO reminders for later. 
3. Describing how a thing could work or be used. You might describe how to use a method that you want to use later.
4. Or used to temporarily remove code from the compiler. 

For myself, I would like to put important comments above what I need & secondary comments only alongside. 

You can put a comment anywhere like the following:
```C#
// C Sharp uses forward slashes to indicate comments or annotations to the reader. 
Console.WriteLine("Hello, World!"); // Comment here!
```

#### Multiline Comments
Multiline Comments are encased in `/*  */`
```C#
/*
HERE IS A 
MULTI Line Comment in C#
*/
```

There are options to comment out sections of code using the above method. It is awkward, but it may have it's use cases:
```C#
// The middle section of code has been commented out:
Console.WriteLine("Hello, World!");/* Console.ReadLine();*/ Console.WriteLine("Another Thing");
```

#### Important
- Avoid making a TODO list around your code. 
- Avoid putting in comments that don't add any value to your code. Example: If at first glance it is obvious what your code does, avoid reexplaining it. 

# Challenge Code
- Concatenating strings together example:
```C#
namespace Testing
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("What kind of thing are we talking about?");
            string name = Console.ReadLine();
            Console.WriteLine("How would you descibe it?");
            string description = Console.ReadLine();
            string ofDoom = "of Doom";
            string model = "3000";

            Console.WriteLine("The " + name + " " + description + " " + ofDoom + " " + model + "!");
        }
```



