# Bridge Pattern

The Bridge pattern is used to decouple an abstraction from its implementation, allowing them to vary independently. It provides a way to create a family of related classes with different implementations. This pattern is particularly useful when we have multiple variations of a class that we want to use interchangeably.

```C#

public interface IImplementor
{
    void OperationImpl();
}

public class ConcreteImplementorA : IImplementor
{
    public void OperationImpl()
    {
        Console.WriteLine("Concrete Implementor A");
    }
}

public class ConcreteImplementorB : IImplementor
{
    public void OperationImpl()
    {
        Console.WriteLine("Concrete Implementor B");
    }
}

public abstract class Abstraction
{
    protected IImplementor _implementor;

    public Abstraction(IImplementor implementor)
    {
        _implementor = implementor;
    }

    public virtual void Operation()
    {
        _implementor.OperationImpl();
    }
}

public class RefinedAbstraction : Abstraction
{
    public RefinedAbstraction(IImplementor implementor) : base(implementor)
    {
    }

    public override void Operation()
    {
        _implementor.OperationImpl();
    }
}

```
