# Finbourne.Sdk.Lusid.Model.BreakCodeSource

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DataTypeId** | [ResourceId](ResourceId.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BreakCodeSource(
    dataTypeId: new ResourceId(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BreakCodeSource>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

