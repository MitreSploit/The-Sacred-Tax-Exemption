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
```
- Because of this, it can be wise to avoid using `var` in certain cases. 
- Recommended at least in the beginning, do not use `var`.



