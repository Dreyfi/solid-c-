# SOLID Principles in C# Examples

This repository contains C# code examples illustrating the SOLID principles.

## Single Responsibility Principle (SRP)

A class should have only one reason to change.

### Code Sample

```csharp
public class Report
{
    public void GenerateReport()
    {
        // Generate report logic
    }

    public void SaveToFile(string report)
    {
        // Save to file logic
    }
}
```

Explanation: The Report class has separate methods for generating a report and saving it to a file.

## Open/Closed Principle (OCP):

Software entities should be open for extension but closed for modification.

### Code Sample

```csharp
public abstract class Shape
{
    public abstract double Area();
}

public class Rectangle : Shape
{
    public double Width { get; set; }
    public double Height { get; set; }

    public override double Area()
    {
        return Width * Height;
    }
}
```

Explanation: New shapes can be added by extending the Shape class without modifying existing code.

## Liskov Substitution Principle (LSP):

Subtypes must be substitutable for their base types.

### Code Sample

```csharp
public class Bird
{
    public virtual void Fly()
    {
        // Bird flying logic
    }
}

public class Sparrow : Bird
{
    public override void Fly()
    {
        // Sparrow flying logic
    }
}
```

Explanation: Sparrow is a subtype of Bird and can be used interchangeably.

## Interface Segregation Principle (ISP):

A class should not be forced to implement interfaces it does not use.

### Code Sample

```csharp
public interface IWorkable
{
    void Work();
}

public interface IEatable
{
    void Eat();
}

public class Worker : IWorkable, IEatable
{
    public void Work()
    {
        // Work logic
    }

    public void Eat()
    {
        // Eat logic
    }
}
```

Explanation: Worker implements only the interfaces it needs.

## Dependency Inversion Principle (DIP):

High-level modules should not depend on low-level modules.

### Code Sample

```csharp
public interface ISwitchable
{
    void TurnOn();
}

public class LightBulb : ISwitchable
{
    public void TurnOn()
    {
        // Turn on logic
    }
}

public class Switch
{
    private readonly ISwitchable _device;

    public Switch(ISwitchable device)
    {
        _device = device;
    }

    public void Operate()
    {
        // Switch operating logic
        _device.TurnOn();
    }
}
```

Explanation: The Switch class depends on the abstraction (ISwitchable).
