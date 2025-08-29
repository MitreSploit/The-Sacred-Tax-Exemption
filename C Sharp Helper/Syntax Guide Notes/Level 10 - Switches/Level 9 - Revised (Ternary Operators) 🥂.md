# If/Else/Else If statements
- They are based on conditional statements. 
- We can use `if` to specify a condition, `else if` to specify another and `else` if neither of those conditions are met.
- we can integrate `[bool]` into our conditions (true or false) like this:
```C#
bool levelComplete;

if (condition1 > condition2){
	levelComplete = true;
}
```
- We should use curly braces for if/else`{}`. Although sometimes C# will allow us to work without it, it's best practice. 
- We are able to nest these statements, but be careful when nesting too many if/else statements because things get messy and complicated. 
- Variables created within if/else are not usable outside of the if/else block, this is called **scope**.

# Ternary Operators (Insanely Useful)
These are comprised of three parts:
1. A `bool` expression.
2. A condition that should be evaluated if the condition is `true`.
3. And a condition that should be evaluated if the condition is `false`.

```C#
static void Main(string[] args)
{
    // Ternary Operators practice:
    int myGuess = 50;
    string rightWrong = myGuess < 40 ? "Close enough!" : "Naa well off";

    Console.WriteLine(rightWrong);
}
```

# Ternary Advanced
This is a much more interesting example where I was able to iterate through an array of Grades and if your Grade was in the array, then you will receive a pass mark.
```C#
static void Main(string[] args)
{
    // Ternary Operators practice:
    string myGrade = "F";
    string[] passingGrades = {"A", "B", "C"};
    string passingGrade = passingGrades.Contains(myGrade) ? "You Pass" : "You Fail!";
    Console.WriteLine(passingGrade);
}
```

