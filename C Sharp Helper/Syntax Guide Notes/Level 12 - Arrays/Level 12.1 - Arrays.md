# Creating Arrays
The following will create an array of int values.
The square brackets indicate that `scores` contains an array of many values. 
Each array contains only elements of a specific type.
```C#
static void Main(string[] args)
{
    int[] scores; // Declaring an array
}
```

We've declared an array, but we can also construct a new array to hold our 10 items like this: 
```C#
static void Main(string[] args)
{
    int[] scores = new int[10];
}
```

The `new` keyword is used to create new things in C#. 
We need it when working with more complex things like arrays. 

For our example above, we decided that `scores` holds a maximum of `10` values. 
Once we have declared this we cannot exceed it and we cannot shrink it. 

We can however create a brand new array, once again using `new` like this:
```C#
internal class Program
{
    static void Main(string[] args)
    {
        int[] scores = new int[10];
        scores = new int[20];
    }
}
```

We have not expanded on `scores`. Instead we have created another array with more capacity and also called it `scores`.
This uses new memory for it's contents. The variable switches to use the complete new memory instead of the memory it used previously. 

**Important:** Any data we have put in the initial array memory is still over there & if we want it in the new array, we have to carry it across. 

**Arrays** are important to know. But **`lists`** are probably going to take their place in the future. 

**Lists** are similar to arrays, but are super powerful & allow us to extend or reduce the size. 


# Getting and Setting Values in Arrays
Indexing arrays is simple. You can use the indexer operator to see the spot in the array like this. 
Indexing in arrays always starts at 0.
```C#
static void Main(string[] args)
{
    int[] scores = new int[10];
    scores[0] = 10;

    Console.WriteLine(scores[0]); // 0 represents the first spot in the array which we've made to be 10.
}
```

###### Default Values
When an array is first created, the computer will take the array's memory location and set every bit to 0. 
For numeric values (Regardless of floating point numbers or integers) this value is set to `0`. 
For bool, this means a `false` value.
For a character, this is `null`.
For a string, it is also `null` to represent a non existent string. Consider these uninitialized. 

In our example above when we declared `new int[10]`, this ensured 10 spots in memory were created with a value of `0`.

###### Crossing Array Bounds
If you attempt to access an array beyond it's size, this could be very bad! 
In C#, any attempt to reach beyond or before the limits of an array is handled. 
You will crash your program if you don't do any error handling and attempt to access out of bounds in the array. 

```C#
static void Main(string[] args)
{
    int[] scores = new int[10];
    scores[0] = 10;
    scores[1] = 12;

    Console.WriteLine(scores[3000]);
}
```

Thankfully, we are able to check the length of an array like this.
```C#
static void Main(string[] args)
{
    int[] scores = new int[10];
    scores[0] = 10;
    scores[1] = 12;

    Console.WriteLine(scores.Length); // Length is a built in property of our Array. 
}
```

# Indexing through an Array:
We can easily use a For loop to iterate through an array using the `array.Length` property like this:
```C#
static void Main(string[] args)
{
    int[] scores = new int[5];
    scores[0] = 10;
    scores[1] = 12;
    scores[2] = 4;
    scores[3] = 9;
    scores[4] = 54;

    for(int i = 0; i < scores.Length; i++)
    {
        Console.WriteLine($"Item at place {i} is: {scores[i]}");
    }
}
```

###### Accessing the back of an Array
Sometimes, we might want to start at the end of an array & we can do that with the following:
```C#
static void Main(string[] args)
{
    int[] scores = new int[5];
    scores[0] = 10;
    scores[1] = 12;
    scores[2] = 4;
    scores[3] = 9;
    scores[4] = 54;

    Console.WriteLine(scores[^1]);
}
```

# Ranges
If we wanted to grab only a section of an array, like between places 0 - 3, then we could use a `range` operator to achieve this, like this:
```C#
static void Main(string[] args)
{
    int[] scores = new int[5];
    scores[0] = 10;
    scores[1] = 12;
    scores[2] = 4;
    scores[3] = 9;
    scores[4] = 54;

    int[] newScores = scores[0..3];
    Console.WriteLine(newScores[0]);
}
```

Here we are actually making a copy of the first array, but only from places 0 to 3. This will not affect the values of `scores`.
This new array will contain values 0, 1, 2 and 3. 

We can also use `^1` in our copy. In that instance, we would be stating that we don't want our copy to contain the final value of the array.
We are also stating to not use the value at place 0. 
```C#
static void Main(string[] args)
{
    int[] scores = new int[5];
    scores[0] = 10; // Do not include this value
    scores[1] = 12;
    scores[2] = 4;
    scores[3] = 9;
    scores[4] = 54; // Do not include this value

    int[] newScores = scores[1..^1];
    Console.WriteLine(newScores[2]);
}
```

You don't always need to specify a start and end. 
You could simply specify to start at place 1 like this `int[] newScores = scores[1..];`


# Other Ways to Create Arrays

##### The Collection Initializer Syntax scheme:
If we already know the values we want to assign to our array, we can do this upon declaration like this:
```C#
static void Main(string[] args)
{
    int[] scores = new int[5] { 1, 2, 3, 4, 600 };
    Console.WriteLine(scores[0]);
}
```

If you have listed all the items you want to list from the start, you don't actually need to specify the length of the array. 
```C#
static void Main(string[] args)
{
    int[] scores = new int[] { 1, 2, 3, 4, 600 }; // No length was required for this to work. 
    Console.WriteLine(scores[0]);
}
```

If you are clear with the type of data you are putting into the array, you also don't need to specify type and can shorten it again. 
The compiler will figure this out. 
```C#
static void Main(string[] args)
{
    int[] scores = new [] { 1, 2, 3, 4, 600 };
    Console.WriteLine(scores[0]);
}
```


