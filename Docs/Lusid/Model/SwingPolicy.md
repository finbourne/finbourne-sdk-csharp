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
| **ApprovalMode** | **string** | Optional | Who settles the swing decision a valuation point deals at. Automatic, the default, finalises the valuation point on the engine&#39;s proposal. Manual holds the proposal: the valuation point cannot be finalised until a manager has submitted a pricingMethodologyOverride on it, equal to the proposal to approve it or different to overrule it. Must be Automatic when defaultSpreadSource is omitted, because a price that never swings has no decision to approve. Available values: Automatic, Manual. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SwingPolicy(
    baseline: new SwingBaseline(...),  // required
    defaultSpreadSource: "...",  // optional — Where the swing comes from. Stored swings by the tiers in spreads. Market swings to the bid or offer, including notional dealing costs, that the valuation recipe of each active NAV type publishes, when the net cashflow passes inflowTrigger or outflowTrigger. Omit it for a fund that never swings and always deals at its baseline. Available values: Stored, Market.
    spreads: new SwingSpreads(...),  // optional
    inflowTrigger: new SwingTrigger(...),  // optional
    outflowTrigger: new SwingTrigger(...),  // optional
    approvalMode: "..."  // optional — Who settles the swing decision a valuation point deals at. Automatic, the default, finalises the valuation point on the engine&#39;s proposal. Manual holds the proposal: the valuation point cannot be finalised until a manager has submitted a pricingMethodologyOverride on it, equal to the proposal to approve it or different to overrule it. Must be Automatic when defaultSpreadSource is omitted, because a price that never swings has no decision to approve. Available values: Automatic, Manual.
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

