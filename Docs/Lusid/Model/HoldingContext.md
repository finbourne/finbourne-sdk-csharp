# Finbourne.Sdk.Lusid.Model.HoldingContext

Holding context node.  Contains settings that control how LUSID handles holdings within portfolios.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TaxLotLevelHoldings** | **bool** | Optional | Whether or not to expand the holdings to return the underlying tax-lots. Defaults to True. |
| **AggregateCashCommitments** | **bool** | Optional | When true, cash commitment holdings sharing a SubHoldingKey are folded into a single aggregated  row per portfolio, mirroring how cash balances are already aggregated. Defaults to false to  preserve existing behaviour. Ignored when TaxLotLevelHoldings is true — tax-lot granularity  takes precedence. Aggregation is per-portfolio: cross-portfolio rows in portfolio-group / fund  responses stay separate, matching the behaviour of positions and cash balances. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new HoldingContext(
    taxLotLevelHoldings: true,  // optional — Whether or not to expand the holdings to return the underlying tax-lots. Defaults to True.
    aggregateCashCommitments: true  // optional — When true, cash commitment holdings sharing a SubHoldingKey are folded into a single aggregated  row per portfolio, mirroring how cash balances are already aggregated. Defaults to false to  preserve existing behaviour. Ignored when TaxLotLevelHoldings is true — tax-lot granularity  takes precedence. Aggregation is per-portfolio: cross-portfolio rows in portfolio-group / fund  responses stay separate, matching the behaviour of positions and cash balances.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<HoldingContext>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

