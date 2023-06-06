# Factory Pattern

The Factory pattern is used to create objects without exposing the creation logic to the client. In .NET, the Factory pattern is implemented using a class or a method that creates objects based on a set of parameters. This pattern is useful when you want to create objects based on a particular set of conditions, and you want to hide the creation logic from the client.

```C#

public interface IAnimalFactory
{
    IAnimal Create();
}

public class DogFactory : IAnimalFactory
{
    public IAnimal Create()
    {
        return new Dog();
    }
}

public class CatFactory : IAnimalFactory
{
    public IAnimal Create()
    {
        return new Cat();
    }
}

public interface IAnimal
{
    string Speak();
}

public class Dog : IAnimal
{
    public string Speak()
    {
        return "Woof!";
    }
}

public class Cat : IAnimal
{
    public string Speak()
    {
        return "Meow!";
    }
}

```
