# Facade Pattern

The Facade pattern is used to provide a simple interface to a complex system. In .NET, the Facade pattern is implemented using a separate class that provides a simplified interface to the existing system. This pattern is useful when you want to simplify the interaction with a complex system, and you want to hide its complexity from the client.

```C#

// Complex subsystem with many parts
public class Subsystem1
{
    public void Operation1()
    {
        Console.WriteLine("Subsystem1: Operation1");
    }

    public void Operation2()
    {
        Console.WriteLine("Subsystem1: Operation2");
    }
}

public class Subsystem2
{
    public void Operation3()
    {
        Console.WriteLine("Subsystem2: Operation3");
    }

    public void Operation4()
    {
        Console.WriteLine("Subsystem2: Operation4");
    }
}

public class Subsystem3
{
    public void Operation5()
    {
        Console.WriteLine("Subsystem3: Operation5");
    }

    public void Operation6()
    {
        Console.WriteLine("Subsystem3: Operation6");
    }
}

// Facade that simplifies the interface to the subsystem
public class Facade
{
    private readonly Subsystem1 _subsystem1;
    private readonly Subsystem2 _subsystem2;
    private readonly Subsystem3 _subsystem3;

    public Facade()
    {
        _subsystem1 = new Subsystem1();
        _subsystem2 = new Subsystem2();
        _subsystem3 = new Subsystem3();
    }

    public void Operation()
    {
        _subsystem1.Operation1();
        _subsystem2.Operation4();
        _subsystem3.Operation6();
    }
}

```
