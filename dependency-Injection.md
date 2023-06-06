# Dependency Injection Pattern

The Dependency Injection pattern is a creational pattern that provides a way to create objects without having to know the details of how they are constructed. This is useful when you need to create objects that have complex dependencies or are difficult to instantiate.

```C#

public interface IDataAccessLayer
{
    void SaveData(string data);
}

public class SqlDataAccessLayer : IDataAccessLayer
{
    public void SaveData(string data)
    {
        // Implementation of saving data in SQL Server
    }
}

public class BusinessLogicLayer
{
    private readonly IDataAccessLayer _dataAccessLayer;

    public BusinessLogicLayer(IDataAccessLayer dataAccessLayer)
    {
        _dataAccessLayer = dataAccessLayer;
    }

    public void SaveData(string data)
    {
        _dataAccessLayer.SaveData(data);
    }
}

```
