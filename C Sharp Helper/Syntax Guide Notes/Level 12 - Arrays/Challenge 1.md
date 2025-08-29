In this challenge, we need to replicate the contents of one array into another. 

1. Make an array that can hold `5` values
2. Allow the user to select the values. 
3. Make a second array - Also with `5` values. 
4. Create a loop - Copy each value from array1 into array2. 
5. Display the contents of both arrays at the same time as a comparison. 

# Complete
```C#
static void Main(string[] args)
{
    int[] userSelection = new int[5];
    int[] secondArr = new int[5];

    Console.WriteLine("I need you to give me 5 whole numbers: ");
    for(int i = 1; i < 6; i++)
    {
        Console.Write($"Write value {i} here: ");
        userSelection[i-1] = int.Parse(Console.ReadLine());
    }

    Console.WriteLine("You have selected the values: ");
    for(int i = 0; i < userSelection.Length; i++)
    {
        Console.Write($"{userSelection[i]}\t");
    }

    Console.WriteLine("\n\nHere is a backup of those numbers: \n");
    Console.ForegroundColor = ConsoleColor.Green;
    for (int i = 0; i < userSelection.Length; i++)
    {
        secondArr[i] = userSelection[i];
        Console.Write($"{secondArr[i]}\t");
    }
    Console.ResetColor();
}
```