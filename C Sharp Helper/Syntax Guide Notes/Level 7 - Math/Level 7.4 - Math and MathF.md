# Math and MathF Classes
C# has two classes with the job of helping you to do common math operations called `Math` and `MathF`.
`Math` works with `double`.
The following are some features but not all of them:

#### ***Operator:*** `π` AND `e`
***Description:*** e and Pi have a defined value in mathematics so that you do not need to always define them. These can be called using the following.
***Example:***
```C#
double area = Math.PI * radius * radius;
```

#### ***Operator:*** Square root/Power of
***Description:*** C# does not have a to the square root of operator or square root of operator. We can accomplish these with Math though. We need to pass two values in this example. We are assigning a value to `x` and a second value to say **Power of** `2`. `Math.Pow` is the same as x to the power of 2. 
***Example:***
```C#
double x = 3.0;
double xSquared = Math.Pow(x, 2);
```

***Description:*** To accomplish the Square root. We can use the `Sqrt` method:
***Example:*** 
```C#
double y = Math.Sqrt(xSquared);
```

#### ***Operator:*** Absolute Value
***Description:*** The absolute value is merely the positive version of a number. The absolute value of `3` is `3`. The absolute value of `-4` is `4`. We can use the `Abs` method to compute absolute values.
***Example:***
```C#
int x = Math.Abs(-2); // This will be 2. 
```

#### ***Operator:*** Trigonometric Function 
***Description:*** Math also has functions for sine, cosine and tangent. 
***Example:*** Some examples are as follow, but they are not limited to only these: 
```C#
double y1 = Math.Sin(0);
double y2 = Math.Cos(0);
```

#### ***Operator:*** Min, Max and Clamp
***Description:*** We can use the `Min` and `Max` methods return the minimum and maximum of two numbers.
***Example:*** 
```C#
int smaller = Math.Min(2, 10); // Smaller will contain 2
int larger = Math.Max(2, 10); // Larger will contain 10
```

***Description:*** We can also use the `Clamp` method in an interesting way. 
***Example:*** We can provide `Clamp` with a range like 0 - 5. If the value we are checking (in this case `health`) is between the range, then the value will remain. 
So, If `health = 3;` we can use Clamp to check if it's between 0 and 5, and because it is, `health` will remain the value of `3`.
However, if `health = 20;` and we are checking if `health` is between 0 and 5, then `health` will become the highest value, because it is higher than the top of the range. If it was less than 0, then `health` would become equal to `0`.
```C#
internal class Program
{
    static void Main(string[] args)
    {
        int health = 0;
        health += -20;

		// Health will equal 0 because it is lower than the range, so It becomes the bottom of the range. 
        health = Math.Clamp(health, 0, 5); 
        Console.WriteLine(health);
    }
}
```


### MathF
Using `MathF` is very similar to `Math`, however instead of using `double`, `Math` uses `float`.

***Description:*** The same as to the Power of for `Math`, but using `MathF` 
***Example:*** 
```C#
float x = 3;
float xSquared = MathF.Pow(x, 2);
```