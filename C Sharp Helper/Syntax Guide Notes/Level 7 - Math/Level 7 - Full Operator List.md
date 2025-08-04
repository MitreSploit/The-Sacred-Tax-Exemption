# Operands and Operators
In this example: `int calculated = 1 + 2;`. This statement has both Operands and Operators. 
1. **Operand** - The Operand is the values being operated on `1` and `2`.
2. **Operator** - The Operator is the symbol that tells the program what to do `+`.

##### Basic Multiplication: 
- Basic multiplication can be performed like this: 
```C#
internal class Program
{
    static void Main(string[] args)
    {
        float newNum = 5.77f;
        float anotherVal = 22.9f;
        float calculate = newNum * anotherVal;
        Console.WriteLine(calculate);

		// We can perform devisions with a forward slash
		float divide = newNum / anotherVal;
    }
}
```

Things can get significantly more complicated when performing calculations with the smaller data types like `byte`, `sbyte`, `short` and `ushort`.

##### Understanding the order of operation
There is a set of rules called the Order of Operations which govern which order things function. 
```C#
int newValue = 2 + 4 * 4;
```
There are two parts:
1. Operator Preference - Like Multiplication before addition. 
2. Operator Associativity - Tells you whether two operators of the same precedence should be evaluated from left to right or right to left. 

C# Uses the standard mathematical order of operations. So it will be natural to normal mathematics. 

# Complete C# Operators list:
https://csharpplayersguide.com/articles/operators-table.html
**General Rules:** 
- Multiplication and division come first. 
- Addition and Subtraction are done last.

We are also able to use parenthesis to say calculate this first:
```C#
int newCalc = (44 - 10) * 10;

// You can also use more parenthesis for more powerful statements. 

int result = ((2+1) * 8 - (2 * 3) / 4);
```

# Basic Triangle Calculation
```C#
internal class Program
{
    static void Main(string[] args)
    {
        Console.WriteLine("Input the int value for a triangles Base Size here: ");
        int baseSize = int.Parse(Console.ReadLine());

        Console.WriteLine("Input the int value for a triangles Height here: ");
        int height = int.Parse(Console.ReadLine());

        int triangleCalc = (baseSize * height) / 2;
        Console.WriteLine("The area of your triangle is: " + triangleCalc);
    }
}
```


