# Escape Sequences
Say we are using `Console.WriteLine("Hello, World!");`, but in our console output, we actually want to see ("") in the output. C# naturally won't accept that we just put those between our quotation marks. We can tell it to though, as long as we use an Escape Character `\`. **EXAMPLE:**
```C#
static void Main(string[] args)
{
    Console.WriteLine("\"Hello, World!\""); 
    // This will output "Hello, World!" with the quotation marks.
}
```

### There are other very useful escapes. Like the following:
```C#
static void Main(string[] args)
{
    Console.WriteLine("\"Hello, World!\"");
    Console.WriteLine("\tThis will peform a tab");
    Console.WriteLine("\nThis will perform a new line");
    Console.WriteLine("This will take \rus back to the start of the line and even overwrite the start of the sentence");
    Console.WriteLine("And this '\\' can be used for things like filepaths");
}
```

Sometimes we don't care to add a bunch of backslashes, especially with things like file paths. In that instance, we are also able to declare a **Literal String** using the following.
```C#
Console.WriteLine(@"C:\Windows\System32"); // Avoids a lot of //
```

# String Interpolation
In previous examples we have concatenated strings together by using the `+` symbol. This strategy can some get a little bit messy though, especially if we have to join a lot of strings and variables together. Instead, we are able to use a `$` and `{myVar}` to perform the same, but cleaner. 

- Important to be cautious about creating very long strings though. 
```C#
static void Main(string[] args)
{
    int myVariable = 5;
    Console.WriteLine($"My favorite number is {myVariable}");
}
```

### SUPER USEFUL!
Just because we use **String Interpolation** with `$`, doesn't mean we can't use a **Literal String** with `@`. As long as we do it in the order `$@`
```C#
static void Main(string[] args)
{
    string myFileName = "New.txt";
    Console.WriteLine($@"C:\Windows\System32\{myFileName}");
}
```


# Alignment
We can actually specify using a comma, how much space to put between, as width. 
This is super useful if we are structuring things like tables. We can achieve this by using a comma inside the curly braces. **EXAMPLE:**
```C#
static void Main(string[] args)
{
    string myName = "Matt";
	Console.WriteLine($"Howdy there! {myName, 20}");
	Console.WriteLine($"G'day! {myName, 20}");
	// Outputs: 
	// Howdy there!                 Matt
	// G'day!                 Matt
}
```

