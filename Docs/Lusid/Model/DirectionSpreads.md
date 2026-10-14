# Finbourne.Sdk.Lusid.Model.DirectionSpreads

The tiers of spread for one direction of net cashflow and what their bounds measure.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Basis** | **string** | Required | What the tier bounds measure: Amount, the size of the net cashflow in the fund currency, or PctOfNav, the net cashflow as a percentage of the previous valuation point&#39;s NAV. Available values: Amount, PctOfNav. |
| **Tiers** | [List&lt;SwingSpreadTier&gt;](SwingSpreadTier.md) | Required | The tiers, in ascending order. Each starts where the previous one ends, and only the last is unbounded above. The first tier&#39;s lower bound is the threshold: a flow at or below it does not swing. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DirectionSpreads(
    basis: "...",  // required — What the tier bounds measure: Amount, the size of the net cashflow in the fund currency, or PctOfNav, the net cashflow as a percentage of the previous valuation point&#39;s NAV. Available values: Amount, PctOfNav.
    tiers: new List<SwingSpreadTier>()  // required — The tiers, in ascending order. Each starts where the previous one ends, and only the last is unbounded above. The first tier&#39;s lower bound is the threshold: a flow at or below it does not swing.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DirectionSpreads>(json);
```

- [SwingSpreadTier](SwingSpreadTier.md) — used in `Tiers`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

