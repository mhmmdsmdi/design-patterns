# Command Pattern

The Command Pattern is a behavioral design pattern that encapsulates a request as an object, thereby allowing for the parameterization of clients with different requests, queues, and log requests, and supports undoable operations. A typical example of this pattern is a remote control for a TV, where each button press corresponds to a different command.

```C#

public interface ICommand
{
    void Execute();
}

public class Receiver
{
    public void Action()
    {
        Console.WriteLine("Receiver does some action");
    }
}

public class ConcreteCommand : ICommand
{
    private Receiver _receiver;

    public ConcreteCommand(Receiver receiver)
    {
        _receiver = receiver;
    }

    public void Execute()
    {
        _receiver.Action();
    }
}

public class Invoker
{
    private ICommand _command;

    public void SetCommand(ICommand command)
    {
        _command = command;
    }

    public void ExecuteCommand()
    {
        _command.Execute();
    }
}

public static void Main()
{
    Invoker invoker = new Invoker();
    Receiver receiver = new Receiver();
    ConcreteCommand command = new ConcreteCommand(receiver);

    invoker.SetCommand(command);
    invoker.ExecuteCommand();
}

```
