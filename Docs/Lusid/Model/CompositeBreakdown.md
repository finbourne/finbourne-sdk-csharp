# Finbourne.Sdk.Lusid.Model.CompositeBreakdown

A list of Composite Breakdowns.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EffectiveAt** | **DateTimeOffset** | Required | The effectiveAt for the calculation. |
| **Composite** | [PortfolioReturnBreakdown](PortfolioReturnBreakdown.md) | Optional | *No description available.* |
| **Constituents** | [List&lt;PortfolioReturnBreakdown&gt;](PortfolioReturnBreakdown.md) | Optional | The constituents with their information which are part of the composite. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CompositeBreakdown(
    effectiveAt: DateTimeOffset.Now,  // required — The effectiveAt for the calculation.
    composite: new PortfolioReturnBreakdown(...),  // optional
    constituents: new List<PortfolioReturnBreakdown>()  // optional — The constituents with their information which are part of the composite.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CompositeBreakdown>(json);
```

- [PortfolioReturnBreakdown](PortfolioReturnBreakdown.md)
- [PortfolioReturnBreakdown](PortfolioReturnBreakdown.md) — used in `Constituents`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

