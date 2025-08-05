Decided which code to run based on conditional statements. 
```C#
static void Main(string[] args)
{
    int score = 100;
    if(score == 100)
    {
        Console.WriteLine("Perfect Score!"); // Conditions will only run if the above statement is true
    }
    else
    {
        Console.WriteLine("You might need more practice");
    }
}
```

#### Equality Operator
- Also of note sis the use of `==`, also known as an **Equality Operator**.
- Here we are asking if this is equal to as opposed to previously when we used `=` to declare that a value is this. 

#### Curly Brackets - Block Statements
- Are optional in C#, however it is easier to read where if/else starts and ends & is recommended to use `{}`.
- **If you choose not to use Block Statements, then only the following line is contained within the if statement. This could be hugely problematic!**

#### One Liners
- C# doesn't mind if you put everything on one line. It's up to the user for readability sake. 
```C#
static void Main(string[] args)
{
    int score = 100;
    if (score == 100) Console.WriteLine("You Win!");
}
```
#### Creating Variables within If/Else
if we create a variable within an if/else block, then it cannot be used outside of that block! 
```C#
static void Main(string[] args)
{
    int myScore = 100;
    if(myScore > 100)
    {
        char grade = 'A';
    }
    Console.WriteLine(grade); // COMPILER ERROR
}
```

- The variable `grade` no longer exists once you get to `Console.WriteLine`. 
- If you were to draw this out, you could visualize it like the following:
```PowerShell
Console Application (Executable)
|
├── Class: Program (internal class)
|   |
|   └── Method: Main(string[] args) [Entry Point]
|       |
|       ├── Variable: myScore 
|       |   - Declared in the method scope
|       |
|       └── if (myScore > 100)
|           |
|           └── Variable: grade 
|               - Declared in the if-block scope
|
└── Console.WriteLine(grade); 
    - COMPILER ERROR: grade is not accessible here
```

It's Important to note that we are able to use the variables outside of you `if/else` block within the block. 

# Scope
The code section where an identifier or name can be used is called it's `scope`. 
If we want to use `grade` outside of our `if/else` block, then we must declare it outside of our block like this:

```C#
static void Main(string[] args)
{
    int myScore = 100;
    char grade = '?';
    if(myScore == 100)
    {
        grade = 'A';
    }
    Console.WriteLine(grade); // GRADE IS DECLARED OUTSIDE OF THE IF/ELSE BLOCK -- AND NOW OUTPUTS 'A'
}
```

Because of **Scope**, two variables are allowed to reuse the same name for different variables.
Another important thing to remember is that you aren't able to create a variable inside of the if/else that has the same name as a variable from main

```C#
static void Main(string[] args)
{
    int myScore = 99;
    char grade = '?';
    if(myScore == 100)
    {
        grade = 'A';
    }
    else
    {
        grade = 'B';
        // I cannot create a variable called myScore within this block, as it already exists. 
    }
        Console.WriteLine(grade); // if/else and other if statements can use the same variable name `grade`
}
```

# Using ELSE
Our counterpart to the `if` statement. It is as simple as if this condition is not true, do not run the `if` condition and instead run the `else` condition.

# Using ELSE IF
If we have multiple conditional statements that could be true, we can use the `else if` statement. 
The conditional statements will check from top to bottom. If no statements are true, then the`else` condition will run. 
```C#
    static void Main(string[] args)
    {
        int myScore = 20;
        char grade = '?';
        if(myScore >= 85)
        {
            grade = 'A';
        }
        else if(myScore >= 60 && myScore < 85)
        {
            grade = 'B';
        }
        else if(myScore > 50 && myScore < 60)
        {
            grade = 'C';
        }
        else if(myScore < 50 && myScore > 40)
        {
            grade = 'D';
        }
        else
        {
            grade = 'F';
        }
            Console.WriteLine(grade); 
    }
}
```

# Decision making with BOOL
```C#
static void Main(string[] args)
{
    int levelProgress = 100;
    int neededToPass = 95;
    bool levelComplete;

    if (levelProgress >= neededToPass)
    {
        levelComplete = true;
    }
    else
    {
        levelComplete = false; // Important to assign both true and false or the code will not run. 
    }

    if (levelComplete)
    {
        Console.WriteLine("Congratulations!");
    }
}
```

We can even shorten this `bool` condition like this:
```C#
static void Main(string[] args)
{
    int levelProgress = 100;
    int neededToPass = 95;
    
    bool levelComplete = levelProgress >= neededToPass; // We provided our conditions here (Much cleaner)

    if (levelComplete)
    {
        Console.WriteLine("Congratulations");
    }
    else
    {
        Console.WriteLine("Please try again!");
    }
}
```


# Challenge
The clocktower of Consolas has been damaged by recent attacks. 
The pendulum is broken. The pendulum should tick to the left if the number is even & to the right if the number is odd.
- Take in a number from the user as input.
- Display any even numbers as `Tick`
- Display any odd numbers as `Tock`

```C#
static void Main(string[] args)
{
    Console.Write("Enter a number here. Even numbers will 'Tick', while Odd numbers will 'Tock': ");
    int userInput = Convert.ToInt32(Console.ReadLine());

    bool pendulumSwing = (userInput % 2 == 0); // The remainder when divided by 2 is 0 (Even)

    if (pendulumSwing)
    {
        Console.WriteLine("Tick");
    }
    else
    {
        Console.WriteLine("Tock"); // The remainder when divided by 2 was not 0 (Odd)
    }
}
```

# Nested IF Statements
It is generally recommended to keep nested if statements at a minimum. Sometimes you can go very deep with it. It might be easier to use `bool` to get around nesting too many if statements. 

**EXAMPLE:**
```C#
if(armor < 50)
{
	if(shield <50)
	{
		Console.WriteLine("In serious trouble!");
	}
}
```

