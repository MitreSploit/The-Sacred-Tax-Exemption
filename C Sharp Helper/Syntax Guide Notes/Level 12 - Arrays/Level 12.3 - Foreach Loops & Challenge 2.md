Arrays and loops go hand in hand together. 
A lot of the time, we need to do something with every item in an array. 

# Foreach
The final loop in C# is the foreach loop. 
Foreach is designed for this scenario. Simpler syntax than for. 

Super straight forward. Foreach item in a list of items. Print the item to console. 
```C#
static void Main(string[] args)
{
    int[] scores = new int[] { 22, 33, 44, 5, -1, 599 };

    foreach (int score in scores)
    {
        Console.WriteLine(score);
    }
}
```

The biggest downside to the **`foreach`** loop is that you can lose knowledge of which index you are at, so sometimes a for loop is better. 
So if you wanted to do something special with **`score[3]`** it would be best to use a `for` loop.

**`foreach`** runs slightly slower than a `for` loop. 
If performance is a problem, consider trying a `for` loop instead. 


# Challenge 2
Create a simple array - Allow users to input the numbers.
Compute the smallest values & the average of all values. 
Use a **`foreach`** loop to accomplish this. 

```C#
static void Main(string[] args)
{
    float[] userArr = new float[10];
    float smallestNum = float.MaxValue;
    float totalCombined = 0;

    Console.WriteLine("Please provide 10 values here: ");
    for(int i = 1; i < 11; i++)
    {
        Console.Write($"Enter the value for {i} here: ");
        userArr[i-1] = float.Parse(Console.ReadLine());
    }

    foreach(float num in userArr)
    {
        if (num < smallestNum)
            smallestNum = num;

        totalCombined += num;
        // totalCombined * 100 / userArr.Length for the average.
    }

    float averageValue = (totalCombined / userArr.Length);

    Console.WriteLine($"The smallest number in the set is {smallestNum}");
    Console.WriteLine($"The average number of all the numbers in the set is {averageValue}");
}
```