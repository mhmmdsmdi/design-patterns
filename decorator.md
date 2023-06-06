# Decorator Pattern

The Decorator pattern is used to add functionality to an object dynamically. In .NET, the Decorator pattern is implemented using a separate class that wraps the original object and provides additional functionality. This pattern is useful when you want to add functionality to an object without changing its interface.

```C#

public interface ICoffee
{
    string GetDescription();
    double GetCost();
}

public class SimpleCoffee : ICoffee
{
    public string GetDescription()
    {
        return "Simple Coffee";
    }

    public double GetCost()
    {
        return 1.0;
    }
}

public class CoffeeWithMilk : ICoffee
{
    private readonly ICoffee _coffee;

    public CoffeeWithMilk(ICoffee coffee)
    {
        _coffee = coffee;
    }

    public string GetDescription()
    {
        return _coffee.GetDescription() + ", with milk";
    }

    public double GetCost()
    {
        return _coffee.GetCost() + 0.5;
    }
}

```
