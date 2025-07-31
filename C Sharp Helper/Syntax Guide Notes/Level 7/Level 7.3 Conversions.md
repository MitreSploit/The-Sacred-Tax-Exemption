# Revision

1. **Explicit Conversion** - Forced conversions. As a general rule, these are conversions made my a user. These conversions can be unsafe if they are **Narrowing Conversions**(Conversions that narrow the data limit. Example: Converting a `long` into a `byte`). However these are safe if performed as a **Widening Conversion**(Like converting a `byte` into a `long`).
2. **Implicit Conversions** - Are automatically performed conversions and as a general rule are performed in the back end and are safe conversions. 
3. **Forcing Explicit Conversions** - To force an Explicit Conversion, this is normal and easy as long as you are choosing a safe data type. However, you have to specify the data type & essentially specify that you accept the risk if you are choosing an unsafe type.

EXAMPLE:
```C#
// This should not throw any issues because long can support anything that an int can hold. 
int anInt = 33;
long newLong = anInt;

// You need to specify in brackets (byte) to perform this actions because it's dangerous.
// I know an int is an int but I accept the consequences of change.
long aLong = 3000000000000000000000000;
byte aByte = (byte)aLong;
```

# More Conversions
There are explicit conversions for all of the numeric int types in C#.
There is also implicit conversions from all eight integer types to the floating-point types, but not the other way around. 

```C#
internal class Program
{
    static void Main(string[] args)
    {
        float myFloat = 3.1415f;
        int myInt = (int)myFloat;

        Console.WriteLine(myInt);
    }
}
```

We cannot cast conversions like this though:
```C#
// Incorrect way to cast conversions. 
string myText = "0";
int myInt = (int)myTest
```

For the above, we have to reply on our `Convert` Methods. 

#### Short
Addition is not defined for the `short` data type. 
If we use addition between two shorts. like `a + b`, we will actually produce an int. 

```C#
static void Main(string[] args) // THE FOLLOWING WILL THROW ERRORS:
{
    short myShort = 3;
    short anotherShort = 5;

    short combined = (myShort + anotherShort);

	// Instead, you need to run something like this: 
	int combined = (myShort + anotherShort);

	// OR if you want it to be a short, you can explicitly ask for it to be converted back. 
	short combine = (short)(myShort + anotherShort);
}
```

Putting the type casting operator (short) in parenthesis is forcing this action to take place. 
The casting operator has precedence higher than most operators. 

#### Type Conversions with Floating Points

- Here is an interesting instance where we are trying to divide two integers and save the value as a floating point number. But, because of how we type casted, we just saw a division of integers and returned an integer value. 
```C#
static void Main(string[] args)
{
    int amountDone = 20;
    int amountToDo = 100;
    double fractionDone = amountDone / amountToDo; // This will return 0 - Which is probably not what we want.

    Console.WriteLine(fractionDone); // returns 0
}
```

- If instead we specify like this:
```C#
static void Main(string[] args)
{
    int amountDone = 20;
    int amountToDo = 100;
    double fractionDone = (double)amountDone / amountToDo; // This will return a more appropriate value of 0.2

    Console.WriteLine(fractionDone);
}
```
