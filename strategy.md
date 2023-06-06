# Strategy Pattern

The Strategy Pattern is a behavioral design pattern that allows a client to choose from a family of algorithms at runtime. This pattern is useful when there are multiple algorithms that can be used to solve a problem, and the choice of algorithm depends on the context. A typical example of this pattern is a sorting algorithm that can be chosen based on the size of the input data.

```C#

public interface IStrategy
{
    void AlgorithmInterface();
}

public class ConcreteStrategyA : IStrategy
{
    public void AlgorithmInterface()
    {
        Console.WriteLine("ConcreteStrategyA.AlgorithmInterface()");
    }
}

public class ConcreteStrategyB : IStrategy
{
    public void AlgorithmInterface()
    {
        Console.WriteLine("ConcreteStrategyB.AlgorithmInterface()");
    }
}

public class Context
{
    private IStrategy _strategy;

    public Context(IStrategy strategy)
    {
        _strategy = strategy;
    }

    public void ContextInterface()
    {
        _strategy.AlgorithmInterface();
    }
}

public static void Main()
{
    Context context;

    context = new Context(new ConcreteStrategyA());
    context.ContextInterface();

    context = new Context(new ConcreteStrategyB());
    context.ContextInterface();
}

```
