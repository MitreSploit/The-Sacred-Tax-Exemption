The guard has created a cannon system that draws power from Fire and Electricity. 
Every third blast of the cannon, the cannon uses `Fire` power. 
and every fifth blast of the cannon it uses `Electric` power. 

At a number like `15` the two will line up and produce a super blast. 

- The fire output should be represented as a `Red` color 
- the electric output should represent as a `Yellow` color. 
- A combination of both should be represented as  a `Blue` color. 


# Working
The code works as intended & it outputs blue for every overlap between Red and Yellow values. 
I also put in a little console reset function which changes the color back to normal, otherwise the closing messages output to yellow. 

```C#
namespace Level11
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("We are about to fire the cannons now!\n");

            // Console.WriteLine(15 % 5);

            for (int i = 1; i <= 100; i++)
            {
                if(i % 3 == 0 && i % 5 == 0)
                {
                    Console.ForegroundColor = ConsoleColor.Blue;
                    Console.WriteLine($"{i}. Mega");
                    ResetConsole();
                }
                else if(i % 3 == 0)
                {
                    Console.ForegroundColor = ConsoleColor.Red;
                    Console.WriteLine($"{i}. Fire");
                    ResetConsole();
                }
                else if (i % 5 == 0)
                {
                    Console.ForegroundColor = ConsoleColor.Yellow;
                    Console.WriteLine($"{i}. Electric");
                    ResetConsole();
                }
                else
                {
                    Console.ResetColor();
                    Console.WriteLine($"{i}. Normal");
                }
            }
        }
        public static void ResetConsole() 
        {
            Console.ResetColor();
        }
    }
}

```