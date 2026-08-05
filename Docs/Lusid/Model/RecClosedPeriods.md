# Finbourne.Sdk.Lusid.Model.RecClosedPeriods

References to the closed periods created on the left and right timelines when a Closed Period  instance is locked.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | [RecClosedPeriodReference](RecClosedPeriodReference.md) | Required | *No description available.* |
| **Right** | [RecClosedPeriodReference](RecClosedPeriodReference.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecClosedPeriods(
    left: new RecClosedPeriodReference(...),  // required
    right: new RecClosedPeriodReference(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecClosedPeriods>(json);
```


## Related Models

- [RecClosedPeriodReference](RecClosedPeriodReference.md)
- [RecClosedPeriodReference](RecClosedPeriodReference.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

