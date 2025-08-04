# Key note points:

- Division by 0 is always asking for trouble. 
- We can take in user input as an integer with `int.Parse(Console.ReadLine());`
- For a numeric value, we are able to see the minimum and maximum number for each data type using the `MaxValue` and `MinValue` methods. **EXAMPLE:** `int aBigNumber = int.MaxValue;`
- We can get a representation for infinity using a double with `double.PositiveInfinity;`
- Sometimes when there is a non computational number, we get this represented as `NaN`. We can also display this as `double.Nan;`
- if you have an `int` like `5 / 2;` this will return `2`. This is because we are not using a floating point number & the number will simply cut off the decimal place. 
- The remainder operator is `%`. We can use this to get the remainder of a division. **EXAMPLE:** `20 % 3;`
- We need to be careful when we are positively or negatively incrementing a number. **EXAMPLE:**

What is actually happening here is that you're saying x is equal to 5, but add 1 to x also. 
```C#
int x = 5;
int y = x++; // Will just return 5 --> But x will equal 6
int y = ++x; // Will return 6
```

- Be especially careful when **`Narrowing`** conversions, but **`Windening`** conversions should never be a problem. 
- We can use an **Explicit** conversion (We tell the program to do the conversion), but if it's an unsafe conversion, the program will expect us to explicitly force the conversion like this, **EXAMPLE:**
```C#
long aByte = 3000000000000000000000000;
byte anInt = (byte)aByte;
```
