# Conditional Operator (VERY USEFUL)
Or sometimes referred to as the **`ternary operator`**. 
There are three parts to it. 
1. A `bool` expression.
2. A condition that should be evaluated if the condition is `true`.
3. And a condition that should be evaluated if the condition is `false`.

```C#
static void Main(string[] args)
{
    int score = 60;
    string textToDisplay = score > 85 ? "You Passed!" : "You Failed!"; // The condition - What happens if true - What happens if false

    Console.WriteLine(textToDisplay);
}
```

This is accomplished by placing the [`condition`], followed by `?`  then [`What happens if true`], followed by `:`, then [`What happens if false`]
- Be cautious using these to make sure your code is understandable.


# Challenge
