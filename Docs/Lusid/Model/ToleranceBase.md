# Finbourne.Sdk.Lusid.Model.ToleranceBase

Base class for the tolerances that relax how strictly a matching rule compares its two sides. Polymorphic  by ToleranceType; each supported type has a corresponding inherited class.

## oneOf Type

`ToleranceBase` can be one of the following types:

* [AggregateNumericTolerance](./AggregateNumericTolerance.md)
* [CoreAttributeOptionalityTolerance](./CoreAttributeOptionalityTolerance.md)
* [CoreDateTolerance](./CoreDateTolerance.md)
* [CoreStringCrossTolerance](./CoreStringCrossTolerance.md)

## Usage

### Creating from a compatible type

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var inner = new AggregateNumericTolerance(...);
var instance = new ToleranceBase(inner);
```

### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ToleranceBase>(json);
```

## Related Models

- [AggregateNumericTolerance](./AggregateNumericTolerance.md)
- [CoreAttributeOptionalityTolerance](./CoreAttributeOptionalityTolerance.md)
- [CoreDateTolerance](./CoreDateTolerance.md)
- [CoreStringCrossTolerance](./CoreStringCrossTolerance.md)

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

