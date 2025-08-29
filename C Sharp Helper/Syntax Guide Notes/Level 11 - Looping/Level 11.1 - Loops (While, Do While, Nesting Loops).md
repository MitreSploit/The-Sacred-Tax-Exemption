C# has four loop types. Three will be discussed here.

# While Loops
A while loop continues to run code as long as the condition specified is true. 
It is structured similarly to an If statement. 
```C#
while (condition)
{
	// Do run my code
}
```

**EXAMPLE**
While loop runs until the variable `x` is greater than or equal to `10`. Then the condition becomes false and it breaks.
```C#
int x = 5;
while (x <= 10)
{
	Console.WriteLine(x);
	x++;
}
```

Infinite loops are sometimes created on purpose but are often the case of a bug. 

**EXAMPLE**
In the following example we initialize a variable for `playersNumber` before the loop that makes the while loop condition `true`.
Because of this, it forces the loop to begin. Without that, the loop will not commence. 
We need to guarantee the loop runs at least once. 
```C#
    static void Main(string[] args)
    {
        int playersNumber = -1;

        while (playersNumber <0 ||  playersNumber > 10)
        {
            Console.Write("Enter a number between 1 and 10 here: ");
            playersNumber = Convert.ToInt32(Console.ReadLine());
        }
    }
}
```


# Do While
If we want to ensure that our loop runs at least one time, then we could be better off using a Do/While loop.
This is because a Do/While loop evaluates it's condition at the end of the loop. 
This ensures you get the code to run at least one time. 
Code evaluates at the end & not at the beginning. 

Don't forget the semicolon at the end of the while condition at the end. 
In this case, unlike the While loop, we no longer need to declare `playersNum` as `-1`.
```C#
static void Main(string[] args)
{
    int playersNum;

    do // GUARANTEED TO RUN AT LEAST ONE TIME.
    {
        Console.Write("Pick a number between 1 and 10: ");
        playersNum = Convert.ToInt32(Console.ReadLine());
    }
    while (playersNum < 0 || playersNum > 10);
}
```


# For Loops
For when you need to pack loop management into a single line. 
```C#
for (initialization statement; condition to evaluate; updating action)
{
	// Do something here. 
}
```

Three statements separated by a semicolon are used to manage the loops conditions. 
The first statement - This almost always involves setting a variable `int i = 0;`
The second statement - Is a condition to evaluate every time through the loop. 
the final statement - defines how to change the variable used in the loops condition. 

Any of these loops can use single statements & block statements are not always required, but I prefer to use them.  

**EXAMPLE**
```C#
static void Main(string[] args)
{
    int playersNum = 0;

    for (int i = 0; i <= 5; i++)
    {
        playersNum++;
        Console.WriteLine(playersNum);
    }
}
```

Technically you can leave out any of the three statements if you don't need them & you could absolutely make a for loop that runs forever.
```C#
// No conditions and will run forever.
for (;;)
{
	Console.WriteLine("Stop this Loop!");
}
```


# Breaking AND Continue Out Of Loops
We can use `break` and `continue` statements to give us more control of how the loop is handled.

**`break`** forces the loop to terminate immediately. We can leave a loop even though the condition is still technically true. 

**`continue`** - Continue however will stop only the current passthrough of the loop, but will advance to the next pass, recheck the condition and keep looping if the condition holds.
Continue is like "skip the rest of this, pass through the loop and continue the next pass"


**EXAMPLE**
We can use break like in the following example. `break` is used to provide an option to the user to quit the loop. 
```C#
static void Main(string[] args)
{
    string myInput;
    int myOutput;

    do
    {
        Console.WriteLine("You can quit the loop by typing 'QUIT` or `EXIT`");
        Console.Write("Enter a number between 1 and 10: ");
        myInput = Console.ReadLine();

        if (myInput == "QUIT" || myInput == "EXIT")
            break;
        myOutput = Convert.ToInt32(myInput);
    }
    while (myOutput <= 0 || myOutput > 10);
}
```

**EXAMPLE**
We can use `continue` like in the following. 
```C#
static void Main(string[] args)
{
    string myInput;
    int myOutput;

    Console.WriteLine("You can quit the loop by typing 'QUIT` or `EXIT`");

    do
    {
        Console.Write("Enter a number between 1 and 10: ");
        myInput = Console.ReadLine();

        if (myInput == "QUIT" || myInput == "EXIT")
            break;
        myOutput = Convert.ToInt32(myInput);

        if (myOutput == 12)
        {
            Console.WriteLine("Please pick something else, I don't like that one...");
            continue;
        }
    }
    while (myOutput <= 0 || myOutput > 10);
}
```


# Nesting Loops
The following is a good example of nesting If statements. 
The code will run through numbers 1 to 10 as the `a` variable. 
Foreach number in `a` there will be a separate count from 1 to 10 which will be in the `b` value. 

Each `b` value will multiply by the `a` value and write out below. 

```C#
static void Main(string[] args)
{
    for (int a = 1; a <= 10; a++)
        for (int b = 1; b <= 10; b++)
            Console.WriteLine($"{a} * {b} = {a * b}");
}
```

```C#
1 * 1 = 1
1 * 2 = 2
1 * 3 = 3
1 * 4 = 4
1 * 5 = 5
1 * 6 = 6
1 * 7 = 7
1 * 8 = 8
1 * 9 = 9
1 * 10 = 10
2 * 1 = 2
2 * 2 = 4
2 * 3 = 6
2 * 4 = 8
2 * 5 = 10
2 * 6 = 12
2 * 7 = 14
2 * 8 = 16
2 * 9 = 18
2 * 10 = 20

<SNIP>
```



###### More on Nesting Loops
Another similar example below.
Here we are specifying a total number of rows and a total numbers of columns. 
We are again iterating through the total number of rows.
Nested within this, we are iterating through columns and displaying `*` to represent this number. 

```C#
static void Main(string[] args)
{
    int totalRows = 5;
    int totalColumns = 10;

    for (int currentRow = 1; currentRow <= totalRows; currentRow++)
    {
        for (int currentColumn = 1; currentColumn <= totalColumns; currentColumn++)
            Console.Write("*");

        Console.WriteLine();
    }
}
```

The out represents as 5 rows with 10 columns. 
```C#
// OUTPUT:

**********
**********
**********
**********
**********
```

