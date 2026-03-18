# Finbourne.Sdk.Workflow.Model.TimeOfDay

A time of the day

## oneOf Type

`TimeOfDay` can be one of the following types:

* [CutLabelReference](./CutLabelReference.md)
* [SpecifiedTime](./SpecifiedTime.md)

## Usage

### Creating from a compatible type

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var inner = new CutLabelReference(...);
var instance = new TimeOfDay(inner);
```

### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TimeOfDay>(json);
```

## Related Models

- [CutLabelReference](./CutLabelReference.md)
- [SpecifiedTime](./SpecifiedTime.md)

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

