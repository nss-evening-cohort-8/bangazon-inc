# Not Hello, World

## Setup

We're going to get your first C# console application setup and running so that we can review some basics of the language.

Open Visual Studio and create a new project.
Select `Console App (.NET Framework)`
Change the name of the project to `MyFirstConsoleApp`

This will create a new [Solution](https://docs.microsoft.com/en-us/visualstudio/extensibility/internals/solutions-overview) with a new [Project](https://docs.microsoft.com/en-us/visualstudio/extensibility/internals/projects) with a single file in it named `Program.cs`.
`Program.cs` is the file that holds your logic. Think of it as your `app.js` from Angular. It's where the logic of your application starts; the entry point.

Add this code into your Program.cs inside of the `Main` function, replacing everything there.

```cs
Console.WriteLine("Welcome to Bangazon!");
Console.ReadLine(); // What happens if you run the app without this line?
```

> ☞ Unike JavaScript, C# is a compiled language, meaning that you need a compiler to read the source code, parse all the logic, and then construct a new executable file.

Next, you compile the program. You can do this by a keyboard shortcut : <kbd>Ctrl</kbd>+<kbd>Shift<kbd>+<kbd>B</kbd> or by going to the `Build` menu and 
selecting the `Build Solution` option.

Now that you have verified that the program will compile without errors, you can execute it.  This can be done by hitting the green play button in the toolbar or by pressing the <kbd>F5</kbd> key. 

You should see `Welcome to Bangazon!` print out in your console application. Press the any key to continue.

## Strongly Typed Variables in C#

Now replace your `Main` function's code with the following.

```cs
// DateTime is the type of the purchaseData variable.
DateTime purchaseDate = DateTime.Now;

/*
    string is the type of the lastName variable. It
    tells the compiler that the lastName variable can
    ONLY hold a string value.
*/
string lastName = "Smith";

/*
    C# now supports implicitly typing of a variable. The
    type of the variable will be determined, by the
    compiler, at compile time.
*/
var firstName = "Bill";

/*
  The String.Format() function syntax allows you to
  build the final string, with placeholders, and
  then provide comma-delimited list of variables to
  use in the placeholders.
*/
Console.WriteLine($"{firstName} {lastName} purchased on {purchaseDate}");
Console.ReadLine();
```

# C# Collections

The C# language has many ways to store a collection of items. You'll quickly see that C# is much more verbose when you write your source code, because the developer needs to provide all of the instructions to the compiler, unlike JavaScript or other dynamically typed languages.

We'll look at a very simple type of collection first - an array of strings. Add the following code to your `Main` method.

```cs
/*
    Not only do you have to say what type the variable is, you also
    have to instantiate that exact same type of object on assignment.
    This may seem redundant, but it's part of the C# language compiler's
    type checking constraints.
*/
string[] products = new string[] {
    "Motorcycle",
    "Sofa",
    "Sandals",
    "Omega Watch",
    "iPhone"
};

/*
    This syntax should look very similar to what you did in an Angular
    partial's ng-repeat directive. However, once again you have to
    explicitly say what type of variable product is. Since the products
    array holds strings, then its type must be string.
*/
foreach (string product in products) {
    Console.WriteLine(product);
}
```

# C# Conditions

Luckily, the `if-then` syntax works exactly like it did in JavaScript. Let's put a condition around what products get displayed. Only products that have a length of 5, or greater.

```cs
foreach (string product in products) {
    if (product.Length > 5) {
        Console.WriteLine(product);
    }
}
```

# Resources

I strongly recommend that you bookmark this [C# Programming Guide](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/index)
