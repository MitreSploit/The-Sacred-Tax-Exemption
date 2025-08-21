In this challenge, we need to replicate the contents of one array into another. 

1. Make an array that can hold `5` values
2. Allow the user to select the values. 
3. Make a second array - Also with `5` values. 
4. Create a loop - Copy each value from array1 into array2. 
5. Display the contents of both arrays at the same time as a comparison. 

# In progress
```C#
static void Main(string[] args)
{
    // Array challange

    int[] firstArr = new int[5];
    int[] secondArr = new int[5];

    Console.WriteLine("You will now be asked to supply 5 values.");

    for (int i = 1; i < 6; i++)
    {
        Console.Write($"Supply the value for {i}: ");
        firstArr[(i -1)] = Convert.ToInt32(Console.ReadLine());
    }

    for(int index=0; index < firstArr.Length; index++)
        secondArr[index] = firstArr[index];

    Console.WriteLine("First Arry - Second Array");
    
    for(int i=0; i < firstArr.Length; i++)
    {
        Console.Write($"{secondArr[i]}");
    }
}
```