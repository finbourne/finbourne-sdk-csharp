# Finbourne.Sdk.Lusid.Model.RecActivityWindow

Base class for the activity windows that give the date range a rec definition's activity-based  reconciliations cover. Polymorphic by windowType; each supported type has a corresponding inherited class.

## oneOf Type

`RecActivityWindow` can be one of the following types:

* [ContiguousActivityWindow](./ContiguousActivityWindow.md)
* [FixedPeriodLookbackActivityWindow](./FixedPeriodLookbackActivityWindow.md)

## Usage

### Creating from a compatible type

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var inner = new ContiguousActivityWindow(...);
var instance = new RecActivityWindow(inner);
```

### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecActivityWindow>(json);
```

## Related Models

- [ContiguousActivityWindow](./ContiguousActivityWindow.md)
- [FixedPeriodLookbackActivityWindow](./FixedPeriodLookbackActivityWindow.md)

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

