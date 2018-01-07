# User Defined Types

A [class](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/class) is a blueprint, or a template, for creating an object instance in memory. C# and the .Net Framework define many types, such as `int`, `decimal`, and `bool` ([value types](https://docs.microsoft.com/en-us/dotnet/visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types)), and `Array`, `string`, and `Object` ([reference types](https://docs.microsoft.com/en-us/dotnet/visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types)) in C#, you can also create your own types.

You create a new reference type with a class.

```cs
public class Writer
{
    public void write (string message)
    {
        Console.WriteLine(message);
    }
}

// The output variable's type is `string` -- a built in type
string output = "Nashville Software School";

// The author variable's type is Writer -- a custom type you defined
Writer author = new Writer();
author.write(output);
```
> [Native types](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/built-in-types-table) are special keywords built into C# like `int`, `bool`, `string`, etc that serve as aliases for .NET libraries like `System.Int32`, `System.Boolean`, `System.String`, etc.

# Properties and Fields

Class properties are the interface you provide to external code to get, and modify, the values of the private fields.

```cs
public class Customer
{
    /*
    Fields
    */
    private string firstName;
    private string lastName;
    public int age = 42;  // Don't EVER do this. This is a public field. Use properties.

    /*
    Properties
    */

    // Simple property that doesn't allow blank values for first name
    public string FirstName {
        get
        {
            return firstName;
        }
        set
        {
            if (value != "")
            {
                firstName = value;
            }
        }
    }

    // Simple property that doesn't allow blank values for last name
    public string LastName {
        get
        {
            return lastName;
        }
        set
        {
            if (value != "")
            {
                lastName = value;
            }
        }
    }

    // Calculated property that has no mutator (setter)
    public string FullName {
        get
        {
            return string.Format($"{firstName} {lastName}");
        }
    }
}
```

> **Resource:** [Properties (C# Programming Guide)](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/properties)

# Methods

Methods are the new name for functions. They are code blocks on a class that performs a series of logic. Think of them as the behaviors of your custom type.

```cs
public class Product
{
	/*
	  Fields
	*/
	private string title;
	private string description;
	private double price;
	private int quantity;

	/*
	  Properties
	*/
	public string Title { get; set; }
	public string Description { get; set; }
	public double Price { get; set; }
	public int Quantity { get; set; }

	/*
	  Methods
	*/
	public void ship (Customer customer, DeliveryService service)
	{
		if (!customer.isLocal)
		{
			service.deliver(this, customer);
		}
	}
}
```

> **Resources:** [Methods (C# Programming Guide)](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/methods)

# Accessibility Levels

In C#, there are five accessibility levels that can be applied to Classes, Methods, Properties and Data Members:

- public
- private
- protected
- internal
- protected internal
- private protected

> **Resource:** [Access Modifiers (C# Programming Guide)](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/access-modifiers)

| Members of | Default member accessibility | Allowed declared accessibility of the member |
|-------------|------------------------------|--------------------------------------------|
| `class` | `private` | All |
| `interface` | `public` | None |
| `enum` | `public` | None |
| `struct` | `private` | `public`, `internal`, & `private` |
