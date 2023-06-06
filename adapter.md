# Adapter Pattern

The Adapter pattern is used to convert the interface of a class into another interface that clients expect. In .NET, the Adapter pattern is implemented using a separate class that acts as a bridge between two incompatible interfaces. This pattern is useful when you want to use a class that is not compatible with the existing codebase, and you want to convert its interface to make it compatible.

```C#

public interface ITarget
{
    void Request();
}

public class Adaptee
{
    public void SpecificRequest()
    {
        Console.WriteLine("Specific request");
    }
}

public class Adapter : ITarget
{
    private readonly Adaptee _adaptee;

    public Adapter(Adaptee adaptee)
    {
        _adaptee = adaptee;
    }

    public void Request()
    {
        _adaptee.SpecificRequest();
    }
}

```
