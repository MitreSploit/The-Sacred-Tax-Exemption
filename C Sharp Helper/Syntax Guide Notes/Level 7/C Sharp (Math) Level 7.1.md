# Special Number Values
There are 11 numeric types in C#. 
8 of the types are integer types.
3 of the types are floating-point types.

```C#
int aBigNumber = int.MaxValue;
short aBigNegativeNumber = short.MinValue;
```

##### Max and Min Values (Integer Types):
if you want to know the maximum and minimum values that a data type can represent, you can use one of the special number values. These are methods, but maybe are really more like variables. 
```C#
internal class Program
{
    static void Main(string[] args)
    {
        int aBigNumber = int.MaxValue;
        short aBigNegativeNumber = short.MinValue;

        Console.WriteLine(aBigNumber);
        // OUTPUT: 2147483647
    }
}
```

##### Representing Infinity (doubles and floats):
- Available options for doubles and floats are `PositiveInfinity` and `NegativeInfinity`.

Some computers will represent infinity using a symbol. Depending on the OS, awkwardly, some computers will instead represent infinity as `8`. 
```C#
internal class Program
{
    static void Main(string[] args)
    {
        double infinity = double.PositiveInfinity;
        
        // Outputs the number 8.
        Console.WriteLine(infinity);
    }
}
```

Doubles and Floats also have a weird value called `NaN` or **Not a Number.**
This is used when a computational result is an impossible value, such as division by zero. 

```C#
internal class Program
{
    static void Main(string[] args)
    {
        double notAnyNumber = double.NaN;

		// Outputs NaN
        Console.WriteLine(notAnyNumber);
    }
}
```

##### Interesting Outputs:
- Something like the below will actually output 2. As in it will round down to despite the result really being 2.5. 
- However, If I made all of these values float instead, then the results would be 2.5.
```C#
static void Main(string[] args)
{
    int a = 5;
    int b = 2;
    int result = a / b;
    Console.WriteLine(result);
}
```

This is because when you divide numbers, using a type without a floating point, the fractional division is split at the point. This is not rounding up or down!

