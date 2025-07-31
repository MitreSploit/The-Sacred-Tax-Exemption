
## The Remainder Operator

Previous revision & using the remainder operator. The following returns 0 because 20 divided by 2 has no remainder & thus it is an equal number. 
```C#
static void Main(string[] args)
{
    int n = 20;
    int remainder = n % 2;
    Console.WriteLine(remainder);
}
```

# Challenge - The Four Sisters and the Duckbear

- 4 Sisters want to divide their daily eggs & the Duckbear gets to eat the remainder.

**Good to remember**
```C#
static void Main(string[] args)
{
    Console.WriteLine("How many eggs did you have today?");
    int eggsTotal = Convert.ToInt32(Console.ReadLine());
    int sisters = 4;

    int eggsPerSister = eggsTotal / sisters;
    int eggsForDuckbear = eggsTotal % sisters;

    Console.WriteLine("Each sister will receive " + eggsPerSister + " eggs.");
    Console.WriteLine("The Duckbear will receive " + eggsForDuckbear + " eggs.");
}
```


In C# `a = a +1` is fine. If `a = 5;` then we now have a value of 6. 
However in the mathematical world this is an absurdity. No number exists that is equal to 1 number greater than itself. 

More examples of this: 
```C#
static void Main(string[] args)
{
// Different ways to add 5 to this value
    int myVar = 0;
    myVar += 5;
    Console.WriteLine(myVar);

// More: 

	a = a -= 4;
	a = a *= 2;
	a = a /= 4;
	a = a %= 2;

// Increment the variable like this:
a++;

// Decrement the variable like this: 
a--;
}
```



# Challenge - The Domination of Kings
- Three kings Melik, Casik and Balik are sitting around a table. They've agreed to a point system to judge whose kingdom is the greatest. 
- An estate is worth `1`, a duchy is worth `3`, and a providence is worth `6`

Created a C# program that sorts through an array of 

```C#
using System.Collections;
using System.Security.Cryptography.X509Certificates;
using System.Threading.Channels;

namespace TestingTime
{
    internal class Program
    {
        static void Main(string[] args)
        {
            string[] brothers = { "Melik", "Casik", "Balik" };
            Hashtable scoreTable = new Hashtable();

            foreach (string brother in brothers)
            {
                Console.WriteLine(brother + ", How many estates do you own? ");
                int brothersEstate = Convert.ToInt32(Console.ReadLine());

                Console.WriteLine(brother + ", How many duchy do you own? ");
                int brothersDuchy = Convert.ToInt32(Console.ReadLine());
                int brothersConvertedDuchy = Duchy(brothersDuchy);

                Console.WriteLine(brother + ", How many Providence do you own? ");
                int brothersProvidence = Convert.ToInt32(Console.ReadLine());
                int brothersConvertedProvidence = Providence(brothersProvidence);

                int totalScore = brothersEstate + brothersConvertedDuchy + brothersConvertedProvidence;
                scoreTable.Add(brother, totalScore);

                string returnMessage = Return(brother, brothersEstate, brothersConvertedDuchy, brothersConvertedProvidence);
                Console.WriteLine(returnMessage);
                Console.WriteLine("");
            }

            foreach(DictionaryEntry entry in scoreTable)
            {
                Console.WriteLine(entry.Key + " has a score of " + entry.Value);
            }
        
        }
        public static int Duchy(int num1)
        {
            int duchySum = num1 * 3;
            return duchySum;
        }
        public static int Providence(int num1)
        {
            int providenceSum = num1 * 6;
            return providenceSum;
        }
        public static string Return(string name, int num1, int num2, int num3)
        {
            int totalScore = num1 + num2 + num3;
            string returnMessage = ("The Total score for " + name + " is " + totalScore);
            return returnMessage;
        }
    }
}

```

If `x = 5;` you are able to increment the value of `x` using either of the following: 
`x++` OR `++x`. Either will work. 


# Prefix and Postfix Increment and Decrement Operators
```C#
    static void Main(string[] args)
    {
        int x = 5;
        int y = ++x;

        Console.WriteLine(y); // evaluates to x + 1. Returns 6.

        x = 5;
        y = x++;

        Console.WriteLine(y); // Evaluate to the original value of x. Returns 5.
    }
}
```


# Working with Different types and Casting
Intermixing with different numeric types can be problematic. 
Addition is fine as long as it's between two integers OR two doubles. However, it becomes problematic when you try and perform additions between an int and a double. 
Luckily C# has a system of conversions between these data types. This allows one data type to be converted into another. 

### There are two types of broad categories of conversions. 
1. **Narrowing Conversion** - This type risks loosing data in the conversion process. For example: If you convert a `long` into a `byte` we could loose data if the number is longer than `byte` can support. 
2. **Widening Conversion** - This type does not risk loosing data in the conversion process. For example: if you go the other way and convert a `byte` to a `long`, there will be no issues because `long` can support everything that a `byte` can. 

### Implicit and Explicit Conversions
Conversions can happen whether the programmer has stated them or not. If the conversion is stated, than this is an `explicit`.
If these conversions happen automatically, then the conversion is `implicit`.
As a general rule, narrowing conversions are almost always `explicit` and forced by the programmer. 
While `widening` conversions that happen automatically are almost always `implicit`.

A conversion like this is fine - This is a safe widening conversion. We know that `int` can support anything that a `byte` can store:
```C#
static void Main(string[] args)
{
    byte aByte = 3;
    int anInt = aByte;

    Console.WriteLine(aByte);
}
```

### Forcing Explicit Conversion
Because the conversion from a data type like `long` to `byte` is an unsafe conversion, C# does not want us to make the conversion and presents an error.
We have to explicitly state that we are fine with the conversion. To state this, we can do the following: 
```C#
// In this case, we are going to loose data because byte cannot support this. 

static void Main(string[] args)
{
    long aByte = 3000000000000000000000000;
    byte anInt = (byte)aByte;

    Console.WriteLine(aByte);
}
```

