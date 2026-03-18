# Finbourne.Sdk.Lusid.Model.Strategy

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Keys** | [List&lt;PerpetualProperty&gt;](PerpetualProperty.md) | Required | *No description available.* |
| **ValueType** | **string** | Required | *No description available.* |
| **Value** | **decimal** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Strategy(
    keys: new List<PerpetualProperty>(),  // required
    valueType: "...",  // required
    value: 0.0d  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Strategy>(json);
```


## Related Models

- [PerpetualProperty](PerpetualProperty.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

