# Data Types
1. Built-in Types OR Primitive Types
- These are the building blocks for more complex data types.

# Of Note
- When we store data, it is stored in either bits (a 1 or a 0) or bytes (a group of 8 bits and the standard grouping size of bits) to represent the range of possible numbers we want to store. 
- Every data type that we want to store requires a scheme for expressing it into binary. 
- Each data type has it's own rules for how the data is represented in binary. Different types are not interchangeable. 
- Different data types cannot be used interchangeably, but we can run conversion on data types, but this also comes with rules. 
- C Sharp uses two bytes for each character as a representation. `A` is `01000001`.

# Integers
When working with integers there are eight different types. 
These are called **integer types** or **integral types** and each uses a different number of bytes which allow you to store bigger numbers & using more memory or smaller numbers. 

Of these data types, we have **Signed** and **Unsigned** types. If we need the use of both positive and negative numbers, we might choose a signed type like `short` or `int`. If we did not require negatives, we might choose to double our positives by choosing to use and unsigned type like `ushort` or `uint`.

| Name   | Byte | Allow Negatives | Minimum      | Maximum      |
| ------ | ---- | --------------- | ------------ | ------------ |
| Byte   | 1    | No              | 0            | 255          |
| Short  | 2    | Yes             | -32k         | 32k          |
| int    | 4    | Yes             | -2 bil       | 2 bil        |
| long   | 8    | Yes             | Quintillions | Quintillions |
| sbyte  | 1    | Yes             | -128         | 127          |
| ushort | 2    | No              | 0            | 65K          |
| uint   | 4    | No              | 0            | 6 bil        |
| ulong  | 8    | No              | 0            | Quintillions |

- Declaring these data types is the same as any other
```C#
sbyte age = 29;
```

# Important
1. If you use a value that is too big for `sbyte`,`short` or `ushort`, then the compiler will error out. 
2. if your literal value is too big for an int, then it will automatically become `uint`, a `long` literal or a `ulong` literal (Whichever one is first capable of representing the number you chose). 
3. You will error if you chose a number too big to be represented by the compiler. 
4. You can force a smaller number to be one of the larger literal types by putting either a `U` or `L` or both at the end of the literal value like this:
- `U` - Represents unassigned and must be either `uint` or `ulong`. 
- `L` - Indicates that it must be `long` or a `ulong` depending on the size of it. 
- `UL` - indicates that it must be a `ulong`, the letters can be uppercase or lowercase and in any order. (Better to use uppercase to avoid L looking like 1)
```C#
ulong aVeryBigNumber = 100000000000U;
aVeryBigNumber = 100000000000L;
aVeryBigNumber = 100000000000UL;
```

5. If we want to make a large value more readable, we are able to use and `_` character like this:
   - The normal convention is to group numbers by 3's, but the compiler doesn't care. 
```C#
// Commas however are not allowed:
int bigNumber = 1_000_000_000;
```

6. When deciding on an integer type, it is important to consider possible value ranges you might want & to consider choosing the smaller type to conserve on memory usage. 
7. If you're trying to keep track of a player score and it will likely run into the billions then it will not work to chose just `int`.
8. **Computers do not have the capability to compute less than int anyway. The computer just upgrades them to ints. So the `int` type is more convenient than using `byte`, `sbyte`, `short` and `ushort`**
9. 


