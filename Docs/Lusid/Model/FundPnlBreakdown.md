# Finbourne.Sdk.Lusid.Model.FundPnlBreakdown

The breakdown of PnL for a Fund on a specified date.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NonClassSpecificPnl** | [Dictionary&lt;string, FundAmount&gt;](FundAmount.md) | Required | Bucket of detail for PnL within the queried period that is not specific to any share class. |
| **AggregatedClassPnl** | [Dictionary&lt;string, FundAmount&gt;](FundAmount.md) | Required | Bucket of detail for the sum of class PnL across all share classes in a fund and within the queried period. |
| **AggregatedGroupPnl** | [Dictionary&lt;string, FundAmount&gt;](FundAmount.md) | Required | Bucket of detail for the sum, across all share classes, of PnL allocated to allocation groups and apportioned to their member share classes, within the queried period. |
| **TotalPnl** | [Dictionary&lt;string, FundAmount&gt;](FundAmount.md) | Required | Bucket of detail for the total PnL within the queried period: the sum of the class-specific, apportioned non-class-specific and allocation-group-apportioned PnL. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundPnlBreakdown(
    nonClassSpecificPnl: new FundAmount(...),  // required — Bucket of detail for PnL within the queried period that is not specific to any share class.
    aggregatedClassPnl: new FundAmount(...),  // required — Bucket of detail for the sum of class PnL across all share classes in a fund and within the queried period.
    aggregatedGroupPnl: new FundAmount(...),  // required — Bucket of detail for the sum, across all share classes, of PnL allocated to allocation groups and apportioned to their member share classes, within the queried period.
    totalPnl: new FundAmount(...)  // required — Bucket of detail for the total PnL within the queried period: the sum of the class-specific, apportioned non-class-specific and allocation-group-apportioned PnL.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundPnlBreakdown>(json);
```


## Related Models

- [FundAmount](FundAmount.md) — used in `NonClassSpecificPnl`
- [FundAmount](FundAmount.md) — used in `AggregatedClassPnl`
- [FundAmount](FundAmount.md) — used in `AggregatedGroupPnl`
- [FundAmount](FundAmount.md) — used in `TotalPnl`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

