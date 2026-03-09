Just some more light revision of some previous chapters. Mainly getting used to the different ways I can use switch statements & conversions. 

```C#
namespace Level11
{
    internal class Program
    {
        static void Main(string[] args)
        {
            //switch again
            Console.Write("Give me a number between 1 & 3 and I'll give you a response: ");

            int yourNum = int.Parse(Console.ReadLine());
            string resp1;

            switch (--yourNum)
            {
                case 0:
                    resp1 = "Hello there";
                    break;
                case 1:
                    resp1 = "goodbye";
                    break;
                case 2:
                    resp1 = "Okay";
                    break;
                default:
                    resp1 = "deep";
                    break;
            }
            Console.WriteLine(resp1);


            Console.WriteLine("Lets do this once more");
            Console.Write("Another number between 1 - 3: ");

            int userInp2 = Convert.ToInt32(Console.ReadLine());
            string myReturn = --userInp2 switch
            {
                0 => "Wattup",
                1 => "Yeah Man",
                2 => "Oh word!",
                _ => "So Deep"
            };
            Console.WriteLine(myReturn);
        }
    }
}

```