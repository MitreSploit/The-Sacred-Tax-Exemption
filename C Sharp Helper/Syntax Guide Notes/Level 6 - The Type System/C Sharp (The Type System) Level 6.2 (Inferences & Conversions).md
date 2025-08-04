- This section has very useful type information for conversions and understanding the data types broken down into bits and bytes.
# Revision Practice:

```C#
using System.ComponentModel;

namespace PracticeApps
{
    internal class Program
    {
        static void Main(string[] args)
        {
            // Initialising a variable
            int pracInt = 7;
            uint pracUing = 22;
            long pracLong = -22222222220;
            ulong pracUlong = 22222200000;
            byte pracByte = 100;
            sbyte pracSbyte = -100;
            float happyFloat = 2.21222f;
            decimal happyDecimal = 22.2222222222M;

            int newInt = Convert.ToInt32(happyFloat);

            pracInt = 44;
            pracUing = 299;
            pracLong = 4490;
        }
    }
}
```

# Type inference
The compiler is smart, it can look at your code and make inferences about a variable without us needing to specify the exact type. 
In the following, we use the `var` keyword as an ambiguous type. 

- This only works if you initialise the variable on the same line that you are assigning the value.
```C#
using System.ComponentModel;

namespace PracticeApps
{
    internal class Program
    {
        static void Main(string[] args)
        {
            var newInt = 22;
            var message = "Hello";

            Console.WriteLine(newInt);
        }
    }
}
```

- `var` can often be shorter and cleaner & can often be more preferred when it is possible to use it. A computer is faster at making type inferences than a human, but there can be problems. 
- consider the following:
```C#
// The computer in this case will assume that var wants a [string]

var userInput = Console.ReadLine();

// In the case above, the compiler has determined that userInput is a string.
// You CANNOT then assign an int to that variable if you do this.
// This WILL NOT work: 

userInput = 3;
```
- Because of this, it can be wise to avoid using `var` in certain cases. 
- Recommended at least in the beginning, do not use `var`.


# Converting Values:
Sometimes, like in the case above. We will want to make a value conversion. If we ask a user for input, it will be taken by the compiler as a [string]. This isn't always ideal. We can however run type conversations like this: 
```C#
static void Main(string[] args)
{
    string something = "7";
    int somethingElse = Convert.ToInt32(something);

    Console.Write("My number is " + somethingElse);
}
```

- Sidenote `Console.Write` & `Console.WriteLine` differences:
```C#
    static void Main(string[] args)
    {
        string something = "7";
        int somethingElse = Convert.ToInt32(something);

        Console.Write("My number is " + somethingElse);
        Console.WriteLine("My number is " + somethingElse); // WriteLine will continue the message on the same line as the message above.
    }
}
```

# Conversion Tables
- If you need to make conversions, there are methods you are able to call that associate to the data type. The following are methods we can use and their targets. 
[^1]

| **Method Name** | **Target Type** | **Method Name** | **Target Type** |
| --------------- | --------------- | --------------- | --------------- |
| ToByte          | byte            | ToSByte         | sbyte           |
| ToInt16         | short           | ToUInt16        | ushort          |
| toInt32         | int             | ToUInt32        | uint            |
| toInt64         | long            | ToUInt64        | ulong           |
| ToChar          | char            | ToString        | string          |
| ToSingle        | float           | ToDouble        | double          |
| ToDecimal       | decimal         | ToBoolean       | bool            |

[^1]: Revision Note: 
	1 byte is equal to 8 bits.
	
	When we see int16, this is saying that a short [Int16] is made up of 16 bits, which is the equivalent to 2 bytes. Meaning that an int [Int32] is made up of 32 bits with 4 bytes in total. 

##### Additional:
- No two languages use the same name for things like int and double. 
- `short`, `int` and `long` all use the the word **`int`** and the number of bits they use.
- The other surprising thing is that in order to convert to a **`float`**, you use the `ToSingle` method. This is because a float is considered a **Single Precision**.
- **`double`** however is `ToDouble`. This is because a double is considered a **Double Precision**.




