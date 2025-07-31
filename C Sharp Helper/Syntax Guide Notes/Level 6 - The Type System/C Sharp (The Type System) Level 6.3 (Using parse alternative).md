# Parse
Some programmers prefer to us an alternative to the `Convert` Class. 
Some programmers will chose to use the `parse` method instead:
```C#
internal class Program
{
    static void Main(string[] args)
    {
    // Converting a string of 9000 into an int:
        int number = int.Parse("9000");
    }
}
```

# Signed an Unsigned Data types: 
##### Revise: 
1. **A Signed Type** - Can store both positive and negative numbers: `sbyte`, `short`, `int` and `long`.
2. **An Unsigned Type** - Can only store positive numbers, but has a greater range of positive numbers: `byte`, `ushort`, `uint` and `ulong`.

# Floating point types:
1. Float - 4 bytes
2. Double - 8 bytes
3. Decimal - 16 bytes

