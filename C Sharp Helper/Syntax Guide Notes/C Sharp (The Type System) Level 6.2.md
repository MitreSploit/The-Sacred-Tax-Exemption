# Reassigning variable values & conversion:

```C#
using System.ComponentModel;

namespace PracticeApps
{
    internal class Program
    {
        static void Main(string[] args)
        {
            // Initialising a variable
            int pracInt = 7;
            uint pracUing = 22;
            long pracLong = -22222222220;
            ulong pracUlong = 22222200000;
            byte pracByte = 100;
            sbyte pracSbyte = -100;
            float happyFloat = 2.21222f;
            decimal happyDecimal = 22.2222222222M;

            int newInt = Convert.ToInt32(happyFloat);

            pracInt = 44;
            pracUing = 299;
            pracLong = 4490;
        }
    }
}
```
