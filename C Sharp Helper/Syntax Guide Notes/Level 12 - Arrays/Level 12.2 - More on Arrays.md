# A Complex Array
The following is a much more complex array example. 
Here we start by setting the max value that is has to be larger than the array. We guarantee this by picking the largest number possibly available in `int`

In this case we have a value for `currentSmallest` that we will use to compare.
If our number is less than this number, than it becomes the new `currentSmallest`.

We iterate through a for loop checking each value. We ensure we check every value in the array by using `array.Length`.

```C#
static void Main(string[] args)
{
    // Complex Arrays
    int[] array = new int[] { 4, 55, -20, 89, 90, 2, -5 };
    int currentSmallest = int.MaxValue;

    for (int i = 0; i < array.Length; i++)
    {
        if (array[i] < currentSmallest) 
            currentSmallest = array[i];
    }
    Console.WriteLine($"The smallest item in the array is {currentSmallest}");
}
```

# Calculate the Average Array Value
Slightly more complex in this example. 
We are finding the average value of an array by adding all the values into a variable and dividing that number by the length of the array.
We also made it more interesting by explicitly converting the output for `myAverage` as a float.

```C#
static void Main(string[] args)
{
    // Complex Arrays -- average value
    int[] array = new int[] { 4, 55, -20, 89, 90, 202, -5 };

    int myTotal = 0;
    

    for (int i = 0; i < array.Length; i++)
    {
        myTotal += array[i];
    }
    float myAverage = (float)myTotal / array.Length;

    Console.WriteLine($"The average value in this array is: {myAverage}");
}
```

