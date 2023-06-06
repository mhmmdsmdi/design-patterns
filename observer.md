# Observer Pattern

The Observer Pattern is a behavioral design pattern that allows an object, called the subject, to notify a list of observers when its state changes. The observers are then automatically notified and updated. A typical example of this pattern is a news agency that notifies its subscribers when a new article is published.

```C#

public interface IObserver
{
    void Update();
}

public interface ISubject
{
    void Attach(IObserver observer);
    void Detach(IObserver observer);
    void Notify();
}

public class ConcreteSubject : ISubject
{
    private List<IObserver> _observers = new List<IObserver>();
    private string _state;

    public string State
    {
        get { return _state; }
        set
        {
            _state = value;
            Notify();
        }
    }

    public void Attach(IObserver observer)
    {
        _observers.Add(observer);
    }

    public void Detach(IObserver observer)
    {
        _observers.Remove(observer);
    }

    public void Notify()
    {
        foreach (IObserver observer in _observers)
        {
            observer.Update();
        }
    }
}

public class ConcreteObserver : IObserver
{
    private string _name;
    private string _observerState;
    private ConcreteSubject _subject;

    public ConcreteObserver(ConcreteSubject subject, string name)
    {
        _subject = subject;
        _name = name;
    }

    public void Update()
    {
        _observerState = _subject.State;
        Console.WriteLine($"Observer {_name}'s new state is {_observerState}");
    }
}

public static void Main()
{
    ConcreteSubject subject = new ConcreteSubject();

    ConcreteObserver observerA = new ConcreteObserver(subject, "A");
    ConcreteObserver observerB = new ConcreteObserver(subject, "B");
    ConcreteObserver observerC = new ConcreteObserver(subject, "C");

    subject.Attach(observerA);
    subject.Attach(observerB);
    subject.Attach(observerC);

    subject.State = "New State";
}

```
