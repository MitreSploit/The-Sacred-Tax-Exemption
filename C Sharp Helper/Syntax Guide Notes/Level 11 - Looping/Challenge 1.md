Create a guessing game program where the user has to guess from a number between 1 & 100. 
I'll give them 10 guess attempts to achieve this or they will be killed by the hydra. 

This script uses the Random class to generate a random number between 1 and 100. 

```C#
static void Main(string[] args)
{
    int startingGuess = 1;

    var rand = new Random();
    int hydraLocation = rand.Next(1, 101);

    Console.WriteLine("Ahoy Matey! I need ye to guess a number between 1 and 100 for me. If we guess correctly, We'll kill the dreaed Hydra! \n");
    
    while(startingGuess <= 10)
    {
        Console.Write("Enter in your guess here matey! ");
        int playerGuess = Convert.ToInt32(Console.ReadLine());

        if (playerGuess == hydraLocation)
        {
            Console.WriteLine("\nYou did it Matey! You saved the world!");
            break;
        }
        else if (playerGuess < hydraLocation)
            Console.WriteLine("You're too Low matey!");
        else if (playerGuess > hydraLocation)
            Console.WriteLine("Too high matey! Yarrrrghhh!");

        startingGuess++;
    }

    if(startingGuess > 10)
        Console.WriteLine("\nYe Dammed us all matey!");
}
```