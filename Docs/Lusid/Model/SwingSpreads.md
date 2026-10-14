# Finbourne.Sdk.Lusid.Model.SwingSpreads

The stored spreads a Single fund swings by, one set for each direction of net cashflow.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Inflow** | [DirectionSpreads](DirectionSpreads.md) | Optional | *No description available.* |
| **Outflow** | [DirectionSpreads](DirectionSpreads.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SwingSpreads(
    inflow: new DirectionSpreads(...),  // optional
    outflow: new DirectionSpreads(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SwingSpreads>(json);
```


## Related Models

- [DirectionSpreads](DirectionSpreads.md)
- [DirectionSpreads](DirectionSpreads.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

