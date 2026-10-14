# Finbourne.Sdk.Lusid.Model.SwingPolicy

The baseline a Single fund's dealing price starts from, the spreads it swings by and, for a Market swing, the  triggers that say when it swings.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Baseline** | [SwingBaseline](SwingBaseline.md) | Required | *No description available.* |
| **DefaultSpreadSource** | **string** | Optional | Where the swing comes from. Stored swings by the tiers in spreads. Market swings to the bid or offer, including notional dealing costs, that the valuation recipe of each active NAV type publishes, when the net cashflow passes inflowTrigger or outflowTrigger. Omit it for a fund that never swings and always deals at its baseline. Available values: Stored, Market. |
| **Spreads** | [SwingSpreads](SwingSpreads.md) | Optional | *No description available.* |
| **InflowTrigger** | [SwingTrigger](SwingTrigger.md) | Optional | *No description available.* |
| **OutflowTrigger** | [SwingTrigger](SwingTrigger.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SwingPolicy(
    baseline: new SwingBaseline(...),  // required
    defaultSpreadSource: "...",  // optional — Where the swing comes from. Stored swings by the tiers in spreads. Market swings to the bid or offer, including notional dealing costs, that the valuation recipe of each active NAV type publishes, when the net cashflow passes inflowTrigger or outflowTrigger. Omit it for a fund that never swings and always deals at its baseline. Available values: Stored, Market.
    spreads: new SwingSpreads(...),  // optional
    inflowTrigger: new SwingTrigger(...),  // optional
    outflowTrigger: new SwingTrigger(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SwingPolicy>(json);
```


## Related Models

- [SwingBaseline](SwingBaseline.md)
- [SwingSpreads](SwingSpreads.md)
- [SwingTrigger](SwingTrigger.md)
- [SwingTrigger](SwingTrigger.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

