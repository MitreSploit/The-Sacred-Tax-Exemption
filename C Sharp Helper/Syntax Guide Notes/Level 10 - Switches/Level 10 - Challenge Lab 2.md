1. The same as Challenge 1, but you get a 50% discount on any sales. 
2. After Asking the user for a number, the program should also ask for a user name. 
3. If the name supplied is my name, the price is cut by 50%

**Both of our switch cases definitely have their sperate uses and this is a great example of that.**

##### Small changes made: 
- I needed to change `value` to be a float or the division wouldn't go great. 
- I added an `if` statement at the bottom. 

```C#
namespace _10_Challenge
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Select the item that you would like to know the price of: ");

            Console.WriteLine("""
                The following items are available:

                1 - Rope
                2 - Torches
                3 - Climbing Equipment
                4 - Clean Water
                5 - Machete
                6 - Canoe
                7 - Food Supplies

                """);
            Console.Write("What number do you want to see the price of? ");
            int userSelection = int.Parse(Console.ReadLine());

            Console.Write("May I ask who this order is for? ");
            string customerName = Console.ReadLine();

            string item = "";
            float value = 0;
            bool valid = true;

            switch (userSelection)
            {
                case 1:
                    item = "Rope";
                    value = 10;
                    break;
                case 2:
                    item = "Torches";
                    value = 15;
                    break;
                case 3:
                    item = "Climbing Equipment";
                    value = 25;
                    break;
                case 4:
                    item = "Clean Water";
                    value = 1;
                    break;
                case 5:
                    item = "Machete";
                    value = 20;
                    break;
                case 6:
                    item = "Canoe";
                    value = 200;
                    break;
                case 7:
                    item = "Food Supplies";
                    value = 1;
                    break;
                default:
                    Console.WriteLine("I don't know that one?!");
                    valid = false;
                    break;
            }

            if (customerName == "Matt")
            {
                value = (value/2);
            }

            if (valid)
            {
                Console.WriteLine($"{item} costs {value} Gold");
            }
        }
    }
}
```

# Alt Change
I can made this even cleaner without the `if` statement like this: 
```C#
float finalOutput = customerName == "Matt" ? (value / 2) : value;

if (valid)
{
    Console.WriteLine($"{item} costs {finalOutput} Gold");
}
```