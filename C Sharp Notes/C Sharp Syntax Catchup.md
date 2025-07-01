#### String Literal
Any text contained within a `" "` will be a string literal. This is a chunk of code that defines a specific value. 

#### Identifiers 
Are things like `Console` and `WriteLine`. They are also casually known as names. These are existing code elements. We can also define the names. 

#### Hierarchical Organization
`Concole.WriteLine` - This is a hierarchy structure where WriteLine is a member or child of Console. A `.` is called the **Member Access Operator**. 
It's all about context. You cannot just use `WriteLine`, the computer needs to know where to find it. 

# Classes and Methods
As mentioned before `Console` is a class. `WriteLine` is a method inside the class of `Console`.
A Class can have a method as a member. A Method cannot have a Class as a member. 

Think about Classes as entities that solve a single problem or perform a specific job or role. Think about a team, where the workload is spread across multiple individuals to perform the job. The `Console` Class's job is to interact with the Console Window. It does this well, but don't ask it to interact with other things. 

**A Class is usually composed of two things:**
1. The data they need to perform their job. 
2. Tasks they can perform. 

These tasks come in the form of Methods. A Method is a reusable block of code that you can request to run. 
Some Methods require data in order to perform their task. Like with the `WriteLine("Hello, World!)` method. You need to give it data to display to the console. Some Methods can even `return` information when they are finished. This allows data to flow too and from the method. 

# Namespaces
All Methods live in containers like a Class, but even Classes have to live somewhere. Most Classes live inside of `Namespaces`.
These are code organizational tools. They are valuable if you're dealing with thousands of classes. The `Console` class lives in a `Namespace` called `System`. **`System.Console.WriteLine("Hello, World!");`**

We didn't need to account for the System Namespace like what I exampled above, but in older versions of C# we would have needed too. Another way to accomplish this would have been by using `using System;`. The `using` directive.
This tells the Compiler if you come across an identifier, look at this `Namespace` first. This allows us to use a Class name without having to stick it in front each time. With C# 10, the compiler will automatically search through a handful of extremely common namespaces without you needing to call it out. 

These are only a few examples of the code available in the **`BASE CLASS LIBRARY (BCL)`**.

