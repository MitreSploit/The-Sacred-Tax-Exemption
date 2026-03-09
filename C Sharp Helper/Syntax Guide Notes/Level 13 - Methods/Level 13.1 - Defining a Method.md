Time to start organizing our code better. 
C# has a some really good tools for code organization. The first one is called a **Method**.

We have already used a few of the build in Methods that C# has available like **`Console.WriteLine`** and **`Convert.ToInt32`**.
Every program we've made so far has a method called **`Main`**.

# Defining a Method
The following illustrates one way we can declare a method. 
```C#
static void Main(string[] args)
{
    Console.WriteLine("Here's a method");

    void CountToTen()
    {
        for (int i = 0; i <= 10; i++)
        {
            Console.WriteLine(i);
        }
    }
    CountToTen();
}
```

After specifying our method is called **`CountToTen`**, we are saying that everything inside of `{}` is part of it. 
###### Method Naming Conventions
Most C# programmers use **UpperCamelCase** to name methods. 
###### What is void? 
We specified `void` in the method as the return type. Void means that it won't produce a result. 
###### Every method contains `()`
This is where we could take in values to use in the method. In our case, the method doesn't require any values to continue. 

