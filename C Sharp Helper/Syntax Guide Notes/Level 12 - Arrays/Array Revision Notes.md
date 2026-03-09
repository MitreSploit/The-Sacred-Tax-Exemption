# Simple Revision Cheat sheet
Simple cheat sheets for quick reference: 
###### 1. Declaring an array & simple cloning an array using a range here: 
```C#
static void Main(string[] args)
{
    int[] secondArr = new int[4]; // The same but specifying this contains 3 numbers.

    secondArr[0] = 22;
    secondArr[1] = 26;
    secondArr[2] = 99;
    secondArr[3] = 33;

    // Setting a range: 
    int[] cloneArr = secondArr[0..2]; // This is pulling from index 0 to index 2... Not including 2. 
    Console.WriteLine(cloneArr[1]);
}
```

###### 2. Simple iteration through an array
You can also use the `^` character to indicate the end of the array
```C#
int[] cloneArr = secondArr[0..2]; // This is pulling from index 0 to index 2... Not including 2. 

for(int i = 0; i <secondArr.Length; i++)
{
    Console.WriteLine(secondArr[i]);
}

Console.WriteLine(secondArr[^1]); // Show me the final number in the array.

```

###### 3. Declare the values in the same line for readability:
The compiler is smart & would work even if we don't say [4]. If we provide 4 values, it will assume the array length. 
```C#
static void Main(string[] args)
{
    int[] secretArray = new int[4] { 22, 45, 66, 77 }; 
    Console.WriteLine(secretArray[0]);
}
```


###### 4. Complex Array
The Logic is this: 
1. We create our array. 
2. We create a variable for the **`currentSmallest`**, but we assign it the largest possible value that it can hold. 
3. We iterate through each item in the array. 
4. We check each item, one by one, and if it's less that the value of **`currentSmallest`** then we specify that **`currentSmallest`** new value is that number. 

```C#
static void Main(string[] args)
{
    int[] array = new int[] { 22, 44, -30, 5, -200, 66 };
    int currentSmallest = int.MaxValue;

    for(int i = 0; i < array.Length; i++)
    {
        if (array[i] < currentSmallest)
        {
            currentSmallest = array[i];
        }
    }
    Console.WriteLine(currentSmallest); 
}
```

