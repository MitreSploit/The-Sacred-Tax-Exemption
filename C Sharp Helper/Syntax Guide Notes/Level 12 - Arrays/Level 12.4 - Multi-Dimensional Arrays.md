There are no limits to what we can do with arrays.
In some cases, we might want to make arrays within arrays.
these are called **`Multi-Dimensional Arrays`** and have been crazy useful to me in the past. 

```C#
static void Main(string[] args)
{
    int[][] matrix = new int[3][];
    matrix[0] = new int[] { 1, 2 };
    matrix[1] = new int[] { 3, 4 };
    matrix[2] = new int[] { 5, 6 };

    Console.WriteLine(matrix[0][1]); // Outputs 2 because it moves to index 1 - Then the second object in index 1.
}
```

Arrays of Arrays are used most often when each array inside of the array needs to be different sizes. which is why it's sometimes instead referred to as a **`Jagged Array`**.

**Important** - We used a jagged array above. In this example we would not be stuck with a predetermined set of numbers that each index can hold. We cannot do this with the next multidimensional array example. 

# Multi-Dimensional
You are able to specify all the values from the declaration like this.

**Note** 
- We used `[,]` in declaration which specifying more than one index. 
- We also could not use `[3][]` this time. 
```C#
static void Main(string[] args)
{
    int[,] matrix = new int[3, 2] { { 1, 2 }, { 4, 6 }, { 70, 2 } };
}
```

- More on the same. 
```C#
static void Main(string[] args)
{
    int[,] matrix = new int[3, 2] { { 1, 2 }, { 4, 6 }, { 70, 2 } };
    Console.WriteLine(matrix[2,1]); // Outputs 2.

    // at index 2 is {70, 2} ... at position 1 is the number 2
}
```

With multidimensional arrays, we indicate that it is multidimensional by placing a comma inside. 
You can have multidimensional arrays of many dimensions. 
These can quickly become difficult to understand. 
###### We are able to have a multidimensional array of regular arrays or a regular array of multidimensional arrays.

**EXAMPLE:**

```C#
static void Main(string[] args)
{
    int[,] matrix = new int[4, 4] { {22, 34, 50, 78}, {99, 22, 94, 87}, {20, 22, 87, 52}, {12, 55, 69, 90} };

    for(int row = 0; row < matrix.GetLength(0); row++)
    {
        for (int column = 0; column < matrix.GetLength(1); column++)
            Console.Write(matrix[row, column] + " ");

        Console.WriteLine();
    }
}

// OUTPUT:
22 34 50 78
99 22 94 87
20 22 87 52
12 55 69 90
```

