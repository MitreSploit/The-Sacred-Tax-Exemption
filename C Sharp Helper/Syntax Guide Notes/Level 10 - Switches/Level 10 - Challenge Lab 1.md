Challenge is to build something to report prices of various pieces of equipment based on the user selection. 

The following items are available
1 - Rope
2 - Torches
3 - Climbing Equipment
4 - Clean Water
5 - Machete
6 - Canoe
7 - Food Supplies

- Then ask to select a number & output the cost of that item.

| Item               | Cost in Gold |
| ------------------ | ------------ |
| Rope               | 10           |
| Torches            | 15           |
| Climbing Equipment | 25           |
| Clean Water        | 1            |
| Machete            | 20           |
| Canoe              | 200          |
| Food Supplies      | 1            |


# Solution 1: 
I learnt a bit from this one. C# Did not like my variables inside of the switch case. Originally I set them as unassigned & the build would not allow me to proceed if there was potential for an unassigned value in `item` and `value`.

In order to fix this, I was able to assign a value to `item` and `value` before the switch statement & everything was fine. 

I also added a `bool` check. If there was no value, then it would fail there too. 

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

            string item = "";
            int value = 0;
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
            if (valid)
            {
                Console.WriteLine($"{item} costs {value}");
            }           
        }
    }
}
```


# Solution 2
If I'm not assigning variables, this is the much cleaner result. Easier too: 
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

            string ownerResponse = userSelection switch
            {
                1 => "Rope costs 10 Gold",
                2 => "Torches costs 15 Gold",
                3 => "Climbing Equipment costs 25 Gold",
                4 => "Clean Water costs 1 Gold",
                5 => "Machete costs 20 Gold",
                6 => "Canoe costs 200 Gold",
                7 => "Food Supplies costs 1 Gold"
            };
            Console.WriteLine(ownerResponse);
        }
    }
}
```

