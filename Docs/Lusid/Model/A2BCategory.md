# Finbourne.Sdk.Lusid.Model.A2BCategory

A2B Category - one of the five major categories in the A2BDataRecord
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **HoldingCurrency** | [A2BBreakdown](A2BBreakdown.md) | Optional | *No description available.* |
| **PortfolioCurrency** | [A2BBreakdown](A2BBreakdown.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new A2BCategory(
    holdingCurrency: new A2BBreakdown(...),  // optional
    portfolioCurrency: new A2BBreakdown(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<A2BCategory>(json);
```


## Related Models

- [A2BBreakdown](A2BBreakdown.md)
- [A2BBreakdown](A2BBreakdown.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

