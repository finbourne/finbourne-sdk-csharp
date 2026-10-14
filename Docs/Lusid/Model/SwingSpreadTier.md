# Finbourne.Sdk.Lusid.Model.SwingSpreadTier

One tier of spread: the band of net cashflow it covers and the spread applied when the flow falls in it.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LowerBoundExclusive** | **decimal** | Required | The size of net cashflow, as a magnitude, above which the tier applies. Zero or more; zero on the first tier swings on any net flow. |
| **UpperBoundInclusive** | **decimal?** | Optional | The size of net cashflow, as a magnitude, up to and including which the tier applies. Omit it on the last tier, which covers every larger flow. |
| **Bps** | **decimal** | Required | The spread, in basis points of the baseline price, applied when the net cashflow falls in the tier. Zero or more. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SwingSpreadTier(
    lowerBoundExclusive: 0.0d,  // required — The size of net cashflow, as a magnitude, above which the tier applies. Zero or more; zero on the first tier swings on any net flow.
    upperBoundInclusive: 0.0d,  // optional — The size of net cashflow, as a magnitude, up to and including which the tier applies. Omit it on the last tier, which covers every larger flow.
    bps: 0.0d  // required — The spread, in basis points of the baseline price, applied when the net cashflow falls in the tier. Zero or more.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SwingSpreadTier>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

