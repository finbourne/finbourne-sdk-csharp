# Finbourne.Sdk.Lusid.Model.SwingSpreadTierBounds

The bounds of the spread tier a net cashflow fell in.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LowerBoundExclusive** | **decimal** | Required | The tier&#39;s lower bound, which the net cashflow was above. |
| **UpperBoundInclusive** | **decimal?** | Optional | The tier&#39;s upper bound, which the net cashflow was at or below. Absent for the unbounded last tier. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SwingSpreadTierBounds(
    lowerBoundExclusive: 0.0d,  // required — The tier&#39;s lower bound, which the net cashflow was above.
    upperBoundInclusive: 0.0d  // optional — The tier&#39;s upper bound, which the net cashflow was at or below. Absent for the unbounded last tier.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SwingSpreadTierBounds>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

